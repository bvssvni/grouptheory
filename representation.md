A group can usually be represented as a matrix.
One kind of groups swaps items around like this:

    1 -> 2
    2 -> 1
    3 -> 3
    
##Generators

A type of changing something from one state to another is called a "generator".
We can represent generators in matrix form.

##Matrix Representation

To write this a matrix, you need to fill inn zeroes.
Read the matrix as input goes into the top and output goes to left in each row.

    0 1 0
    1 0 0
    0 0 1

A matrix product of square matrices is written in my calculator syntax as a triple multiplication.
You can find the calculator here: http://www.cutoutpro.com/calc/

    A *** B

    A *** A
    [0,1,0, 1,0,0, 0,0,1] *** [0,1,0, 1,0,0, 0,0,1]
    [1,0,0, 0,1,0, 0,0,1]
    
This is the identity matrix:

    1 0 0
    0 1 0
    0 0 1

##Binary Representation

When finding generators with a computer, one can compare and sort matrices by using binary numbers.
Modern CPU's handle 64 bit numbers very easily.
If one entry is represented by a bit, then you can have an 8x8 generator in a single 64 bit number.

However, using one bit per entry is a waste of space, because there is only 1 positive bit per row.
If we represent the position of the 1 per row in binary form,
we can calculate the size of matrix supported:

     1  bit -> 1 column     -> 1 row    -> 1 bit total  -> 1x1
     2  bit -> 4 columns    -> 4 rows   -> 2*4 = 8 bit total  -> 4x4
     3  bit -> 8 columns    -> 8 rows   -> 3*8 = 24 bit total -> 8x8

By using the second representation we can reduce the size for 8x8 from 64 to 24 bits.

##Rubik's Cube

In calculator notion, using one number per row becomes a simple list of numbers.
Rubik's cube got 20 movable cubes.

    [0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19] e   identity   0:19
    [6,7,0,1,2,3,4,5,8,9,10,11,12,13,14,15,16,17,18,19]	y1  yellow clock-wise
    [2,9,14,3,4,5,6,7,1,13,10,11,0,8,12,15,16,17,18,19]	r1  red clock-wise
    [0,1,4,10,16,5,6,7,8,3,15,11,12,13,2,9,14,17,18,19]	b1  blue clock-wise
    [0,1,2,3,4,5,6,7,8,9,10,11,18,19,12,13,14,15,16,17]	w-1 white counter-clock-wise
    [0,1,2,3,16,10,4,7,8,9,17,5,12,13,14,15,18,11,6,19]	o-1 orange counter-clock-wise
    [6,1,2,3,4,5,18,11,7,9,10,19,0,13,14,15,16,17,12,8]	g-1 green counter-clock-wise

If you rotate Rubik's cube clock-wise around yellow and then clock-wise blue, we can write the following:

    x=y1
    y=b1
    y\\x
    
The '\\' operation is an index lookup.
It is important to start the indices at 0 to get the same indices out.


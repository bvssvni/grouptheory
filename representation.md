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



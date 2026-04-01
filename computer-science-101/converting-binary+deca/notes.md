## Binary and Deca conversions
Computers only understand binary code. (zeros and ones)
We are taught deca. (numerical prefix meaning 10)

- In order to convert binary to deca we use the positions of binary code to add together all of the values in a 0 and 1 string to solve for the binary number to deca. 

- in order to convert deca to binary we take the highest 1 value in the binary position and use the table below to subtract the next highest number until we have no remainder.

Deca and binary positions: 
| 512 | 256 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | 0 | 0 | 0 | 0 | 0 | 0| 0 | 0 |


### Examples
*B to D:*  0 0 1 0 1 1 0 0 1 1 => 128 + 32 + 16 + 2 + 4 = 179 

*D to B:* 296 => 256 - 32 - 8 = 0 => 1 0 0 1 0 1 0 0 0 
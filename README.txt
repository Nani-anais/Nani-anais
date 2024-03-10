README.txt

this code contains the implimantation of the data encryption stadard (DES) algorithm in 
C++. DES is a symmetric key block cipher that uses a 56 bit key to encrypt a 64 bit block. 

Here is an overview of what each function does:

hex2bin() 
this function converts a hexadicimal string to a binary string by mapping each hex character 
to its 4 bit binary representaion and concatenating them.

bin2hex()
this function converts a binary string to a hexadecimal string by mapping each 4 bit binary
sequence to its corresponfing hexadecimal character.

bin2dec()
this function converts a binary string to a decimal integer by shifting and adding the bits
from left to right.

xorOperation()
this function preforms a bitwise XOR operation on two binary strings 'a' and 'b' of the same
length.

generatRoundKeys()
this function generates the 16 round keys used in the DES algorithm fromm the 56 bit key.
It first applies the permutation choice 1 to the key, then splits it into two halves, 
applies the left and right shifts amounts specifed in the shift_table, and then combines
the halves and applies the permutaion choice 2 for each round key. The resulting keys are 
stored in tho roundKeys array.

initialPermutaion()
this function performs the initial permutaion on the 64 bit plaintext using the initial_perm
array.

substitution()
this function applies the sboxes to the right half of the data after expanding it using the 
exp_tab array. It first extracts 8 sub blocks of 6 bits each from 'input', then uses the corresponding
sbox to substitute each sub block with a 4 bit output. The 32 bit output is returned as a binary string.

desEncrypt()
this function preforms the full DES encryption on the 64 bit plaintext using the 56 bit key. It first
applies the inital permutaion, then the 16 rounds of substitution, permutaion, and the XOR with the 
round keys. The resulting ciphertext is then subjected to the final permutaion using final_perm array.

main()
This main fucntion is the entry point of the program. It prompts the useer to enter a 16 character hexadecimal
string for the plain text and the key, then calls the desEncrypt() function resulting in the ciphertext!

example of plaintext: 123456ABCD132536
example of key: AABB09182736CCDD
example of what ciphertext should output: 9C3B672064616050
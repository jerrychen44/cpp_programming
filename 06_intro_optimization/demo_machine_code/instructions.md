### C++ versus Machine Code

C++ is a high level language that makes it easier for us humans to write computer programs. But, a computer cannot understand C++ directly. Your compiler converts your C++ code into machine code, which is a language that the CPU (central processing unit) understands. Machine code is a series of zeros and ones, which is how your computer communicates.

You can actually see what machine code looks like. In the workspace below, open a terminal window and type the following three lines. Make sure to hit enter after typing each line:

```
cd demo_machine_code
g++ -c machine_code.cpp
xxd -b machine_code.o
```
The -c flag in g++ tells the compiler to output an object file, which is machine code.

The xxd command ouputs the .o file in its binary representation. Looking at the output, the first column is just a row number written in [hexadecimal](https://simple.wikipedia.org/wiki/Hexadecimal_numeral_system). Then each of the following six columns contains one byte of information. And the last column shows you the text representation that is in the file.

You'll see there are over 1200 lines of machine code just to represent a program that assigns an integer value to a variable.
//log
xxd -b machine_code.o
00000000: 11001111 11111010 11101101 11111110 00000111 00000000  ......
00000006: 00000000 00000001 00000011 00000000 00000000 00000000  ......
0000000c: 00000001 00000000 00000000 00000000 00000100 00000000  ......
00000012: 00000000 00000000 10110000 00000001 00000000 00000000  ......
00000018: 00000000 00100000 00000000 00000000 00000000 00000000  . ....
0000001e: 00000000 00000000 00011001 00000000 00000000 00000000  ......
00000024: 00111000 00000001 00000000 00000000 00000000 00000000  8.....
0000002a: 00000000 00000000 00000000 00000000 00000000 00000000  ......
00000030: 00000000 00000000 00000000 00000000 00000000 00000000  ......
00000036: 00000000 00000000 00000000 00000000 00000000 00000000  ......
0000003c: 00000000 00000000 00000000 00000000 01111000 00000000  ....x.
00000042: 00000000 00000000 00000000 00000000 00000000 00000000  ......
00000048: 11010000 00000001 00000000 00000000 00000000 00000000  ......
0000004e: 00000000 00000000 01111000 00000000 00000000 00000000  ..x...
00000054: 00000000 00000000 00000000 00000000 00000111 00000000  ......
0000005a: 00000000 00000000 00000111 00000000 00000000 00000000  ......
00000060: 00000011 00000000 00000000 00000000 00000000 00000000  ......
00000066: 00000000 00000000 01011111 01011111 01110100 01100101  ..__te
0000006c: 01111000 01110100 00000000 00000000 00000000 00000000  xt....
00000072: 00000000 00000000 00000000 00000000 00000000 00000000  ......
00000078: 01011111 01011111 01010100 01000101 01011000 01010100  __TEXT
0000007e: 00000000 00000000 00000000 00000000 00000000 00000000  ......
00000084: 00000000 00000000 00000000 00000000 00000000 00000000  ......
0000008a: 00000000 00000000 00000000 00000000 00000000 00000000  ......
00000090: 00010110 00000000 00000000 00000000 00000000 00000000  ......
00000096: 00000000 00000000 11010000 00000001 00000000 00000000  ......
0000009c: 00000100 00000000 00000000 00000000 00000000 00000000  ......
000000a2: 00000000 00000000 00000000 00000000 00000000 00000000  ......
000000a8: 00000000 00000100 00000000 10000000 00000000 00000000  ......
000000ae: 00000000 00000000 00000000 00000000 00000000 00000000  ......
000000b4: 00000000 00000000 00000000 00000000 01011111 01011111  ....__
000000ba: 01100011 01101111 01101101 01110000 01100001 01100011  compac
000000c0: 01110100 01011111 01110101 01101110 01110111 01101001  t_unwi
000000c6: 01101110 01100100 01011111 01011111 01001100 01000100  nd__LD
000000cc: 00000000 00000000 00000000 00000000 00000000 00000000  ......
000000d2: 00000000 00000000 00000000 00000000 00000000 00000000  ......
000000d8: 00011000 00000000 00000000 00000000 00000000 00000000  ......
000000de: 00000000 00000000 00100000 00000000 00000000 00000000  .. ...
000000e4: 00000000 00000000 00000000 00000000 11101000 00000001  ......
000000ea: 00000000 00000000 00000011 00000000 00000000 00000000  ......
000000f0: 01001000 00000010 00000000 00000000 00000001 00000000  H.....
000000f6: 00000000 00000000 00000000 00000000 00000000 00000010  ......
000000fc: 00000000 00000000 00000000 00000000 00000000 00000000  ......
00000102: 00000000 00000000 00000000 00000000 00000000 00000000  ......
00000108: 01011111 01011111 01100101 01101000 01011111 01100110  __eh_f
0000010e: 01110010 01100001 01101101 01100101 00000000 00000000  rame..
00000114: 00000000 00000000 00000000 00000000 01011111 01011111  ....__
0000011a: 01010100 01000101 01011000 01010100 00000000 00000000  TEXT..
00000120: 00000000 00000000 00000000 00000000 00000000 00000000  ......
00000126: 00000000 00000000 00111000 00000000 00000000 00000000  ..8...
0000012c: 00000000 00000000 00000000 00000000 01000000 00000000  ....@.
00000132: 00000000 00000000 00000000 00000000 00000000 00000000  ......
00000138: 00001000 00000010 00000000 00000000 00000011 00000000  ......
0000013e: 00000000 00000000 00000000 00000000 00000000 00000000  ......
00000144: 00000000 00000000 00000000 00000000 00001011 00000000  ......
0000014a: 00000000 01101000 00000000 00000000 00000000 00000000  .h....
00000150: 00000000 00000000 00000000 00000000 00000000 00000000  ......
00000156: 00000000 00000000 00100100 00000000 00000000 00000000  ..$...
0000015c: 00010000 00000000 00000000 00000000 00000000 00001101  ......
00000162: 00001010 00000000 00000000 00000000 00000000 00000000  ......
00000168: 00000010 00000000 00000000 00000000 00011000 00000000  ......
0000016e: 00000000 00000000 01010000 00000010 00000000 00000000  ..P...
00000174: 00000001 00000000 00000000 00000000 01100000 00000010  ....`.
0000017a: 00000000 00000000 00001000 00000000 00000000 00000000  ......
00000180: 00001011 00000000 00000000 00000000 01010000 00000000  ....P.
00000186: 00000000 00000000 00000000 00000000 00000000 00000000  ......
0000018c: 00000000 00000000 00000000 00000000 00000000 00000000  ......
00000192: 00000000 00000000 00000001 00000000 00000000 00000000  ......
00000198: 00000001 00000000 00000000 00000000 00000000 00000000  ......
0000019e: 00000000 00000000 00000000 00000000 00000000 00000000  ......
000001a4: 00000000 00000000 00000000 00000000 00000000 00000000  ......
000001aa: 00000000 00000000 00000000 00000000 00000000 00000000  ......
000001b0: 00000000 00000000 00000000 00000000 00000000 00000000  ......
000001b6: 00000000 00000000 00000000 00000000 00000000 00000000  ......
000001bc: 00000000 00000000 00000000 00000000 00000000 00000000  ......
000001c2: 00000000 00000000 00000000 00000000 00000000 00000000  ......
000001c8: 00000000 00000000 00000000 00000000 00000000 00000000  ......
000001ce: 00000000 00000000 01010101 01001000 10001001 11100101  ..UH..
000001d4: 00110001 11000000 11000111 01000101 11111100 00000000  1..E..
000001da: 00000000 00000000 00000000 11000111 01000101 11111000  ....E.
000001e0: 00000101 00000000 00000000 00000000 01011101 11000011  ....].
000001e6: 00000000 00000000 00000000 00000000 00000000 00000000  ......
000001ec: 00000000 00000000 00000000 00000000 00010110 00000000  ......
000001f2: 00000000 00000000 00000000 00000000 00000000 00000001  ......
000001f8: 00000000 00000000 00000000 00000000 00000000 00000000  ......
000001fe: 00000000 00000000 00000000 00000000 00000000 00000000  ......
00000204: 00000000 00000000 00000000 00000000 00010100 00000000  ......
0000020a: 00000000 00000000 00000000 00000000 00000000 00000000  ......
00000210: 00000001 01111010 01010010 00000000 00000001 01111000  .zR..x
00000216: 00010000 00000001 00010000 00001100 00000111 00001000  ......
0000021c: 10010000 00000001 00000000 00000000 00100100 00000000  ....$.
00000222: 00000000 00000000 00011100 00000000 00000000 00000000  ......
00000228: 10101000 11111111 11111111 11111111 11111111 11111111  ......
0000022e: 11111111 11111111 00010110 00000000 00000000 00000000  ......
00000234: 00000000 00000000 00000000 00000000 00000000 01000001  .....A
0000023a: 00001110 00010000 10000110 00000010 01000011 00001101  ....C.
00000240: 00000110 00000000 00000000 00000000 00000000 00000000  ......
00000246: 00000000 00000000 00000000 00000000 00000000 00000000  ......
0000024c: 00000001 00000000 00000000 00000110 00000001 00000000  ......
00000252: 00000000 00000000 00001111 00000001 00000000 00000000  ......
00000258: 00000000 00000000 00000000 00000000 00000000 00000000  ......
0000025e: 00000000 00000000 00000000 01011111 01101101 01100001  ..._ma
00000264: 01101001 01101110 00000000 00000000                    in..
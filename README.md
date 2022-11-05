# Stream-Cipher

The file attack.py contains Python functions that implement the Init and Next functions of the stream cipher and the Enc and Dec functions of the pseudo one-time pad based on this stream cipher.

The stream cipher is somewhat similar to RC4. The state passed between calls of the stream cipher consists of list of 256 bytes (i.e., 256 numbers, each between 0 and 255), plus one additional number between 0 and 255, which can be viewed as a pointer into the list. (This is a difference from RC4, which has 2 pointers.). Another difference is that this stream cipher takes an initial value, which must be in the form of a list of 256 bytes.

The Enc function takes as input IV (which is supposed to be chosen randomly at the time of encryption), a key k, and a message m (which is given as a list of bytes) and outputs ciphertext c, which begins with the IV and then follows with mj + xj mod 256 for all j, where mj is the jth message byte and xj is the jth byte output from the stream cipher with the IV and k. Dec just inverts this given key k and ciphertext c.

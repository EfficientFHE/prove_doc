# Data Representation

## High-precision integer representation
Native JAX does not support arbitrary high precision data type, hence we need to manually use a vector of available low-precision data type to represent a given high-preicions value.

In PROVE, any given high-precision unsigned integer will be decomposed into a vector of unsigned 16-bit integer (u16).

For example, a 128-bit unsigned integer will be represented as 8 chunks as following

[ 0, 1, 2, 3, 4, 5, 6, 7]
0 indicates the value from the bit range [0, 15] of the original 128-bit unsigned integer.

The index of chunk is increasing with the actual bit range of the chunk within the original high-precision unsigned integer, such that the above chunk with value as 0 is called chunk 9.

Each high-precision data is being represented as a vector of low-precision chunk

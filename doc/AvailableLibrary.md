# Available Library

## MSM (Multi Sclalar Multiplication)
The most popular primitive in SNARKs (usually sizes 2^15-2^27) [link](https://github.com/ingonyama-zk/icicle/blob/main/icicle/include/icicle/msm.h#L94)

## NTT (Number theoretic transform)
The most popular primitive in STARKs (usually sizes 2^10-2^27) [link](https://github.com/ingonyama-zk/icicle/blob/main/icicle/include/icicle/ntt.h#L125)

## Vector operations:
These are the most popular operations on vectors of scalars.
They include operation that work element wise between two vectors, a vector and a single scalar or a single vector.
- https://github.com/ingonyama-zk/icicle/blob/main/icicle/include/icicle/vec_ops.h#L77
- https://github.com/ingonyama-zk/icicle/blob/main/icicle/include/icicle/vec_ops.h#L96
- https://github.com/ingonyama-zk/icicle/blob/main/icicle/include/icicle/vec_ops.h#L116
- https://github.com/ingonyama-zk/icicle/blob/main/icicle/include/icicle/vec_ops.h#L136
- https://github.com/ingonyama-zk/icicle/blob/main/icicle/include/icicle/vec_ops.h#L176
- https://github.com/ingonyama-zk/icicle/blob/main/icicle/include/icicle/vec_ops.h#L196
- https://github.com/ingonyama-zk/icicle/blob/main/icicle/include/icicle/vec_ops.h#L214
- https://github.com/ingonyama-zk/icicle/blob/main/icicle/include/icicle/vec_ops.h#L235
- https://github.com/ingonyama-zk/icicle/blob/main/icicle/include/icicle/vec_ops.h#L254
- https://github.com/ingonyama-zk/icicle/blob/main/icicle/include/icicle/vec_ops.h#L272
Implementing the vector operations does not neccesarily accelerate the actual calculation but it is important to keep the data on the device. Most of the applications use the recoups in-between the demanding primitives a.k.a MSM, NTT...

Additionally we support the following hash functions:
- Blake2s
- Keccak
- Poseidon
- Poseidon2
- Sha

All derive and implement the following function [link](
https://github.com/ingonyama-zk/icicle/blob/main/icicle/include/icicle/hash/hash.h#L38)

And a very popular primitive that takes advantage of those hashes is the Merkle tree
[link](https://github.com/ingonyama-zk/icicle/blob/main/icicle/include/icicle/merkle/merkle_tree.h)
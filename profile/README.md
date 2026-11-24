# Proof of Seed

Ethereum, Bitcoin and Solana authenticate their users with elliptic-curve signatures, and a quantum computer able to break elliptic-curve cryptography, or a classical cryptanalytic advance to the same effect, would expose the accounts these signatures protect.
The mitigations under discussion replace the signature scheme at the protocol level, and need a hard fork, or on Bitcoin a soft fork, and a long period of coordination that an emergency would not allow.

A Proof of Seed is a graceful emergency fallback: zero-knowledge proof of the seed phrase, master entropy, or some secret derived from it by hashing, from which a hierarchical deterministic wallet ultimately derived the account authority.
Its soundness depends on hash functions and on the proof system rather than on the discrete-logarithm problem, so it remains meaningful even after elliptic-curve signatures have been completely broken.

This work makes a proof of seed run where seeds are held: in the secure elements of hardware wallets, and on phones and low-power computers, which may be unable to run modern succinct proof systems, or unsuited to them.
A streamed ZKBoo prover, an MPC-in-the-Head proof whose memory does not depend on the length of the computation or of the proof, runs inside the secure element and streams its proof out, so that the seed never leaves the device.
An untrusted, more powerful machine then lifts that proof: it verifies it inside a succinct proof system and produces a short proof that it has done so, learning nothing secret and unable to have a false statement accepted.

- Visit our [website](https://proofofseed.org/).
- Read our [whitepaper](https://github.com/ProofofSeed/whitepaper).
- Read about our [HW wallet implementation](https://github.com/ProofofSeed/boo-in-a-box)
- Check out our [Rust ecosystem for ZK proofs on HW wallets](https://github.com/zkboo)

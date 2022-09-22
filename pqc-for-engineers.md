# Post-Quantum Cryptography for Engineers

(Some editorship info goes here)

## Introduction

This document is meant to give general guidance on the structure and use of post-quantum cryptographic (PQC) algorithms for engineers who are using PQC algorithms in their software.
Topics include which PQC algorithms to use, how PQC key exchange mechanisms (KEMs) differ from classical KEMs, expected size and processing time differences between PQC algorithms and classical algorithms, and so on.

The reader of this document is expected to understand coding and data structures using established cryptographic libraries. They are also expected to understand classical cryptographic basics.
It does not cover such topics as when classical algorithms might become vulnerable (for that, see documents such as [Quantum Computing and the DNS](https://www.icann.org/octo-031-en.pdf) and others.) 

### Contributing to This Document

The guide was inspired by a thread in September 2022 on the <mailto:pqc@ietf.org> mailing list.
The document is being collaborated on through a [GitHub repository] (https://github.com/paulehoffman/post-quantum-for-engineers).

The editors actively encourage contributions to this document.
Please consider writing a section on a topic that you think is missing.
Short of that, writing a paragraph or two on an issue you found when writing code that uses PQC would make this document more useful to other coders.
Opening issues that suggest new material is fine too, but relying on others to write the first draft of such material is much less likely to happen than if you take a stab at it yourself.

## Classical Cryptographic Primitives that Could Be Replaced by PQC

(KEMs)

(Signatures)

## Popular PQC Algorithms

(Describe the NIST algorithms as they stand today)

(Describe non-NIST algorithms that have some support)

## KEMs in PQC

(Which are used where)

(Replacing DH algorithms with PQ KEMs)

(“Key Transport API (aka RSA)”, the “Key Agreement API (aka (EC)DH)”, and how the “KEM API” is neither of those.)

## POC Signatures

(HBS vs Lattice signatures: when each is appropriate.)

(Guidance for managing state of XMSS / LMS. Tree-splitting at keygen time, synchronous state management, any other tricks that are worth documenting. Including when it’s just too complicated to even attempt, like a 30 year signing key where you don’t know at keygen time how many backup copies you’ll need over its lifetime and flips to backup may happen without warning.)

## Recommendations for Security / Performance Tradeoffs

(For example if full-strength Kyber1024 just won’t fit. Under what circumstances can you go down to level1 lattice strength (or less)?)

## Details of FALCON and Dilithium Relevant to Coding

(A layman’s explanation of the gaussian-vs-uniform sampling difference between FALCON and Dilithium. Why access to a robust floating point stack matters. What type of devices you should / should not implement FALCON on.)

## Hash-then-Sign Versus Sign-then-Hash

(...and the security weaknesses of each)

## Further Reading

(A reading list. [Serious Cryptography](https://nostarch.com/seriouscrypto). Pointers to PQC sites with good explanations. List of reasonable Wikipedia pages.)



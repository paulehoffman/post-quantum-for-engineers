# Post-Quantum Cryptography for Engineers

This work is part of public domain.
[See this page for more information.](https://creativecommons.org/publicdomain/zero/1.0/)

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

The National Institute of Standards and Technology (NIST) started a process to solicit, evaluate, and standardize one or more quantum-resistant public-key cryptographic algorithms, as seen [here](https://csrc.nist.gov/projects/post-quantum-cryptography).
Said process has reached its [first announcement](https://csrc.nist.gov/publications/detail/nistir/8413/final) in July 5, 2022, which stated which candidates to be standardized for two types of algorithms:

* Key Encapsulation Mechanisms (KEMs)
* Digital Signatures

NIST announced as well that they will be [opening a fourth round](https://csrc.nist.gov/csrc/media/Projects/post-quantum-cryptography/documents/round-4/guidelines-for-submitting-tweaks-fourth-round.pdf) to standardize an alternative KEM, and a [call](https://csrc.nist.gov/csrc/media/Projects/pqc-dig-sig/documents/call-for-proposals-dig-sig-sept-2022.pdf) for new candidates for a post-quantum signature algorithm.

### Announced to be standardized NIST algorithms

#### PQC KEMs

* [CRYSTALS-Kyber](https://pq-crystals.org/kyber/): Kyber is a module learning with errors (MLWE)-based key encapsulation mechanism.

#### PQC Signatures

* [CRYSTALS-Dilithium](https://pq-crystals.org/dilithium/)
* [Falcon](https://falcon-sign.info/)
* [SPHINCS+](https://sphincs.org/)

### Candidates advancing to the fourth-round for standardization at NIST

The fourth-round of the NIST process only concerns with KEMs.
The candidates still advancing for standardization are:

* [Classic McEliece](https://classic.mceliece.org/)
* [BIKE](https://bikesuite.org/)
* [HQC](http://pqc-hqc.org/)
* [SIKE](https://sike.org/): Supersingular Isogeny Key Encapsulation (SIKE) is a specific realization of the SIDH (Supersingular Isogeny Diffie-Hellman) protocol. Recently, a [mathematical attack](https://eprint.iacr.org/2022/975.pdf) based on the "glue-and-split" theorem from 1997 from Ernst Kani was found against the underlying chosen starting curve and torsion information. In practical terms, this attack allows for the efficient recovery of the private key. NIST has to yet comment if the scheme will be still considered and there is still debate around if the scheme can be changed so that the attack can be prevented.

### Algorithms not-to-be standardized by NIST that have some support

#### KEMs

* [NTRU](https://ntru.org/)
* [NTRU-Prime](https://ntruprime.cr.yp.to/)

## KEMs

### What is a KEM

### What security properties do they provide

* IND-CPA
* IND-CCA

### Where can a KEM be used

To note:
* KEMs vs Diffie-Hellman (DH): they can be a replacement but they are not a one-to-one replacement. KEMs do not provide non-interactivity, for example, that DH does provide.
* Replacing DH algorithms with PQ KEMs.
* Which are used where.
* “Key Transport API (aka RSA)”, the “Key Agreement API (aka (EC)DH)”, and how the “KEM API” is neither of those.

## POC Signatures

### What is a Post-quantum Signature

### What security properties do they provide

### Where can different types of PQC signatures be used

(HBS vs Lattice signatures: when each is appropriate.)

(Guidance for managing state of XMSS / LMS. Tree-splitting at keygen time, synchronous state management, any other tricks that are worth documenting. Including when it’s just too complicated to even attempt, like a 30 year signing key where you don’t know at keygen time how many backup copies you’ll need over its lifetime and flips to backup may happen without warning.)

## Recommendations for Security / Performance Tradeoffs

(For example if full-strength Kyber1024 just won’t fit. Under what circumstances can you go down to level1 lattice strength (or less)?)

## Details of FALCON and Dilithium Relevant to Coding

(A layman’s explanation of the gaussian-vs-uniform sampling difference between FALCON and Dilithium. Why access to a robust floating point stack matters. What type of devices you should / should not implement FALCON on.)

## Hash-then-Sign Versus Sign-then-Hash

(...and the security weaknesses of each)

## Further Reading & Resources

### Reading List
(A reading list. [Serious Cryptography](https://nostarch.com/seriouscrypto). Pointers to PQC sites with good explanations. List of reasonable Wikipedia pages.)

### Developer Resources

- [Open Quantum Safe](https://openquantumsafe.org/) and corresponding [github](https://github.com/open-quantum-safe)


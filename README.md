This repository holds a very early version of what is meant to later be a guide for post-quantum cryptography (PQC) aimed at the engineers who need to implement PQC.
The guide was inspired by a thread in September 2022 on the <mailto:pqc@ietf.org> mailing list.

## Specifications

### PQUIP collection

The IETF PQUIP WG put up a [collection of PQ related specifications](https://github.com/ietf-wg-pquip/state-of-protocols-and-pqc).
 
## Software

### liboqs

[liboqs](https://github.com/open-quantum-safe/liboqs) contains all algorithms standardized or still in the process of standardization by [NIST](https://csrc.nist.gov/projects/post-quantum-cryptography). It is a C library with wrappers for many programming languages such as Go, Perl, Java, Python, etc. The project's main page is at https://www.openquantumsafe.org.

## Integrations

### oqs-demos

[oqs-demos](https://github.com/open-quantum-safe/oqs-demos) contains integrations of PQC into many standard crypto packages with build documentation, e.g., for openssl, curl, nginx, etc. Resultant, ready-to-run docker images for quick trialing are accessible at [docker hub](https://hub.docker.com/?namespace=openquantumsafe). Minimum required knowledge for use is the names of PQ algorithms as [documented e.g., here](https://github.com/open-quantum-safe/oqs-provider#algorithms). For knowing more, reading through material at https://openquantumsafe.org is strongly recommended.

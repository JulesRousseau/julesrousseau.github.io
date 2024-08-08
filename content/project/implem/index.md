---
title: Implementations
date: 2023-11-01
external_link: 
tags:
  - AES
  - DSA
  - MIDORI
---
## [AES (Advanced Encryption Standard)](https://nvlpubs.nist.gov/nistpubs/fips/nist.fips.197.pdf)

## [DSA (Digital Signature Algorithm)](https://csrc.nist.gov/files/pubs/fips/186-3/final/docs/fips_186-3.pdf)

## [Midori-64](https://eprint.iacr.org/2015/1142.pdf)

This SageMath implementation of Midori-64 is a simplified version of the standard. Specifically, some round constants are omitted. The primary objective was to conduct differential cryptanalysis on this cipher as part of a Symmetric Cryptanalysis course. Omitting the additional constants made it easier to understand and identify differential trails.

<!--more-->

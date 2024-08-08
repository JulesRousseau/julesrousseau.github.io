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

**Project Type:** <span style="font-size: 2em;">{{< icon name="hero/user" >}}</span>

**Programming:** <span style="font-size: 2em;">{{< icon name="devicon/c" >}}</span>


As part of my cryptography project, I developed a complete implementation of the AES in the C programming language following the FIPS 197 standard. This project includes the creation of a program capable of encrypting and decrypting files using both ECB and CBC modes.

My program runs from a terminal and supports several options, such as selecting the encryption key, choosing the encryption mode (ECB by default, CBC optional), and displaying the results in hexadecimal format. An integrated user manual allows users to view the available commands.

For the AES implementation, I used tables generated via SageMath for the S-boxes and polynomial-exponentiation transformations. I also developed specific procedures to handle conversions as for instance : hexadecimal (within a string) to int.

## [DSA (Digital Signature Algorithm)](https://csrc.nist.gov/files/pubs/fips/186-3/final/docs/fips_186-3.pdf)

**Project Type:** <span style="font-size: 2em;">{{< icon name="hero/user" >}}</span>

**Programming:** <span style="font-size: 2em;">{{< icon name="devicon/java" >}}</span>


In my project on implementing the DSA as specified by the FIPS 186-3 standard, I focused on leveraging existing functions from the BigInteger module (multiprecision library) to streamline the development process.

The signature needs a hash function, thus I used the **SHA-1 hash function**.

This project was a holiday assignment to prepare for my Master’s 2 studies and to gain some experience with Java. I learned how to handle classes to manage private and public keys (x, y) and the signature parameters (r, s). This setup facilitates the generation of new key pairs and signatures using the "new" command and allows for updates as needed.This project was a Holiday project to prepare the Master 2 back, and try to learn a bit of Java. I learnt how to handle classes to manage private and public keys (x, y) and the signature parameters (r, s). This setup facilitates the generation of new key pairs and signatures using the "new" command and allows for updates as needed.

## [Midori-64](https://eprint.iacr.org/2015/1142.pdf) 

**Project Type:** <span style="font-size: 2em;">{{< icon name="hero/user" >}}</span>

**Programming:** <span style="font-size: 2em;">{{< icon name="devicon/python" >}}</span>


Midori-64 is actually a cryptographic algorithm, specifically a lightweight block cipher. 

This cipher encrypts 64-bit blocks using a 128-bit key. The algorithm performs 16 rounds of encryption, where each round involves several key components: **SubCells** for nonlinear substitution (adding confusion), **MixColumn** for linear transformation (ensuring diffusion), **ShiftRows** for rearranging bits across rows, and **AddRoundKey**, which applies a XOR with a round key to the data.

My Python implementation of Midori-64 is a simplified version of the standard. Specifically, some round constants are omitted. The primary objective was to conduct differential cryptanalysis on this cipher as part of a Symmetric Cryptanalysis course. Omitting the additional constants made it easier to understand and identify differential trails.
<!--more-->

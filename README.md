# ran-rs

**A 5G radio access network, written from scratch in Rust.**

Every open 5G stack today is written in C or C++, and the bugs that follow from that
are the bugs their developers spend their time on. ran-rs is a complete RAN written
from the 3GPP specifications in Rust: physical layer, MAC, RLC, PDCP, SDAP and RRC,
with nFAPI, F1 and O-RAN fronthaul interfaces, on both the gNB and the UE side.

The work starts where the real-time budget is spent: LDPC and polar channel coding
and the FFT. Each kernel is verified against the implementations the industry runs
today, OpenAirInterface, ocudu and FFTW, bit-exact where the result is a bit or an
integer, by block error rate where it is a decoder, and by throughput and latency on
a dedicated real-time machine. One `std::simd` source targets x86 AVX2 and AVX-512,
ARM NEON and RISC-V RVV.

> **Status: proposal.** Code lands here as it is completed.

## Licence

Copyright 2026 Sunnyside Software j.d.o.o.

[GNU Affero General Public License v3.0](LICENSE).

## Author

Bartosz Podrygajlo, `bartosz.podrygajlo@gmail.com`

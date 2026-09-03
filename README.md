# Lyra Releases

This public repository contains signed Windows x64 installers, updater artifacts, `latest.json`, and sanitized release notes for the private [OrionAISystems/Lyra](https://github.com/OrionAISystems/Lyra) application.

No application source code is published here.

Release history is maintained in the public [CHANGELOG.md](CHANGELOG.md).

## System requirements

Lyra's default local transcription uses [Parakeet TDT 0.6B v3](https://huggingface.co/nvidia/parakeet-tdt-0.6b-v3) through [NeMo-Speech.cpp](https://github.com/NVIDIA/NeMo-Speech.cpp).

For a usable local experience, plan on:

- Windows x64
- 8 GB of system RAM
- A modern 4-core CPU
- Approximately 2 GB of free disk space during setup

A dedicated GPU and CUDA Toolkit are not required; Lyra can use the CPU runtime. Systems with 4 GB of RAM may load the model for short utterances, but are not a supported performance baseline. The Parakeet model itself is approximately 714 MB, and longer recordings or other running applications require additional memory.

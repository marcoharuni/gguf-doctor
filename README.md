# GGUF Doctor

Inspect, validate, and explore `.gguf` model files — in your terminal or entirely in your browser, with nothing ever uploaded to a server.

## What it does
- Validates a GGUF file's header, metadata, tensor descriptors, alignment, and tensor byte ranges
- Reports every quantization type actually present in the file (not just what the filename claims)
- Full tensor inventory: name, type, shape, storage size, offset

## Build (CLI)
    cmake -B build -DCMAKE_BUILD_TYPE=Release
    cmake --build build
    ./build/gguf-doctor model.gguf

## Status
Core GGUF parser forked from the [LMc](https://github.com/nile-agi/LMc) inference engine project at NileAGI. This repo is scoped specifically to parsing/validation — no dequantization, no inference.
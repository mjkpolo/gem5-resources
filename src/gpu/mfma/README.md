---
title: MFMA Test
tags:
    - x86
    - amdgpu
layout: default
permalink: resources/mfma
shortdoc: >
    Resources to run the MFMA Tests.
---

## Getting Tests From amd-lab-notes

```
git clone --no-checkout --depth 1 https://github.com/amd/amd-lab-notes.git
cd amd-lab-notes
git sparse-checkout init
git sparse-checkout set matrix-cores
```

## Compiling MFMA

```
cd src/gpu/mfma/amd-lab-notes/matrix-cores
make -j
```

## Running MFMA test on VEGA_X86/gem5.opt

Example: fp64_16x16x4fp64
```
build/VEGA_X86/gem5.opt configs/example/gpufs/mi200.py -a amd-lab-notes/matrix-cores/mfma_fp64_16x16x4fp64 --kernel gem5-resources/src/x86-ubuntu-gpu-ml/vmlinux-gpu-ml --disk-image gem5-resources/src/x86-ubuntu-gpu-ml/disk-image/x86-ubuntu-gpu-ml
```

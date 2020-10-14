# Hybrid CPU/GPU stencil code (CUDA version)

This directory contains the following versions of the stencil code:
* CPU-only (OpenMP): [`src/stencil2d_cpu.cpp`](src/stencil2d_cpu.cpp) calling [`src/update_halo.cpp`](src/update_halo.cpp) and [`src/apply_stencil_cpu.cpp`](src/apply_stencil_cpu.cpp).
* GPU-only (CUDA): [`src/stencil2d_gpu.cu`](src/stencil2d_gpu.cu) calling [`src/apply_stencil.cu`](src/apply_stencil.cu) which includes the halo update.
* Hybrid (OpenMP+CUDA): [`src/stencil2d_hybrid.cu`](src/stencil2d_hybrid.cu) combining the above.

## Compiling on Piz Daint
```bash
source modules.sh
./compile.sh
```

## Running on Piz Daint
```bash
sbatch stencil2d_cpu.slurm
sbatch stencil2d_gpu.slurm
sbatch stencil2d_hybrid.slurm
```

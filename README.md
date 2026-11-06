# OpenLB CHPC PBS Scripts

PBS job submission scripts for running OpenLB fluid-structure interaction (FSI) simulations on the CHPC cluster.

---

## About

These scripts automate the compilation and execution of the `deformableParticleInShearFlow3d` example from the OpenLB library — a 3D simulation of a deformable particle suspended in a shear flow, using the Lattice Boltzmann Method (LBM).

---

## Requirements

- OpenLB installed on your Lustre directory
- MPI module: `chpc/compmech/openmpi/4.1.2-gcc-12.1.0`

---

## Scripts

### `compile.pbs`
Compiles the OpenLB `deformableParticleInShearFlow3d` example on a single node (1 node, 24 cores) using the SMP queue. Output and errors are saved to `compile.out` and `compile.err`.

### `run.pbs`
Submits the simulation on 2 nodes (48 MPI processes) using the normal queue with a 4-hour walltime. Output and errors are saved to `run.out` and `run.err`.

---

## Usage

### Step 1 — Update the paths

Before submitting, open each script and update the paths to match your Lustre directory.

### Step 2 — Compile

```bash
qsub compile.pbs
```

### Step 3 — Run

```bash
qsub run.pbs
```

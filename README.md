# true8b

Lightweight residual / integer coder.

- **Path A**: Order-1/2 context + XOR residual → true8b residual codes
- **Path B**: Pure delta (postings/keys) → true8b
- Multi-block + OpenMP parallel encode
- Frame v2 container

## Build
```bash
gcc -O3 -fopenmp -o true8b true8b.c
```

## Usage
```bash
./true8b c text     input.bin   out.true8b
./true8b c postings ids.txt     out.true8b
./true8b d          out.true8b  restored.bin
./true8b bench
```

## Notes
Path A is a residual specialist. It does not claim to beat xz/bzip2 on general text.
Calgary / Canterbury numbers are in `true8b_public_bench.json` (honest ratios).

Private / commercial use: residual coefficients and production engines stay closed (IP Guard).

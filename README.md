# CP2K benchmark

To aid with standardisation across UK HPC systems, our CP2K benchmark is identical to the one used by ARCHER, the UK national HPC service.

Details of how to build and run the benchmark may be found in the ARCHER repository here: https://github.com/hpc-uk/archer-benchmarks/tree/master/apps/CP2K

For the purposes of scoring procurements, the important line is the maximum time taken by CP2K, so as per the example given by the ARCHER team:

```
grep "CP2K      " outputfile
CP2K                                 1  1.0    0.178    0.295  200.814  200.816
```

the time taken would be 200.816 - and this is the value which should be reported.

Scaling runs to the proposed island size would be useful for this benchmark.

We currently have CP2K version 4.1, 6.1 and 7.1 deployed in ARC.  It is up to the vendor which version they use.

# Results

The benchmarks were run on a recent ARC cluster, using CP2K 6.1, built with GCC 8.3.0, OpenMPI 4.0.4 and Intel MKL.

## Setup benchmark

Setup part of the benchmark (input_bulk_B88_3.inp):

4 nodes (192 cores) 1 OMP thread per MPI task (48 tasks)
```
CP2K                                 1  1.0    0.027    0.037  127.073  127.073

```

Result: `Total time: 127.073`

8 nodes (384 cores) 4 OMP threads per MPI task (12 tasks) 
```
CP2K                                 1  1.0    0.033    0.039   64.485   64.485
```

Result: `Total time: 64.485`

## LiH-HFX benchmark

On 24 nodes (1152 cores) 1 OMP thread per MPI task (48 tasks):

```
CP2K                                 1  1.0    0.922    2.819  821.129  821.131
```

Result: `Total time: 825.445`





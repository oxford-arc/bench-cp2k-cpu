# CP2K benchmark

To aid with standardisation across UK HPC systems, our CP2K benchmark is identical to the one used by ARCHER, the UK national HPC service.

Details of how to build and run the benchmark may be found in the ARCHER repository here: https://github.com/hpc-uk/archer-benchmarks/tree/master/apps/CP2K

For the purposes of scoring procurements, the important line is the maximum time taken by CP2K, so as per the example given by the ARCHER team:

```
grep "CP2K      " outputfile
CP2K                                 1  1.0    0.178    0.295  200.814  200.816
```

the time taken would be 200.816 - and this is the value which should be reported.

Scaling runs to the size of a proposed island would be useful for this benchmark.

We currently have CP2K version 4.1, 6.1 and 7.1 deployed in ARC.  It is up to the vendor which version they use.

# Results

## Setup Results

The setup part of the benchmark (input_bulk_B88_3.inp) was run on a recent ARC cluster. Using CP2K 6.1, built with GCC 8.3.0 and OpenMPI 3.1.4 

Three Nodes (144 cores)
```
CP2K                                 1  1.0    0.042    0.048  122.936  122.941

```

Result: `Total time: 122.941`

## Performance of the LiH-HFX Benchmark

On 24 Nodes (1152 cores) 1 OMP thread per MPI task:

```
CP2K                                 1  1.0    1.186    3.113  825.443  825.445
```

Result: `Total time: 825.445`





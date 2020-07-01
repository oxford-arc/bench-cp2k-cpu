# CP2K benchmark

To aid with standardisation across UK HPC systems, our CP2K benchmark is identical to the one used by ARCHER, the UK national HPC service.

Details of how to build and run the benchmark may be found in the ARCHER repository here: https://github.com/hpc-uk/archer-benchmarks/tree/master/apps/CP2K

For the purposes of scoring procurements, the important line is the maximum time taken by CP2K, so as per the example given by the ARCHER team:

```
grep "CP2K      " outputfile
CP2K                                 1  1.0    0.178    0.295  200.814  200.816
```

the time taken would be 200.816.

Because of the way benchmarks are scored, and because this is a *time* where smaller is better, then for scoring purposes this becomes the number of these that fit in an hour, so with the example above the score would be:

```
            3600
 score = ------- = 17.927
         200.816
```

**Clarification** - the Archer repository warns that this benchmark should be run on 128 nodes or otherwise it will run out of memory.  This is true for the HFX part of the benchmark which is for a much larger system than we are procuring for the Grace procurement.

For the procurement it is sufficient to run the first (setup) part of the benchmark (input_bulk_B88_3.inp).  

We currently have CP2K version 4.1, 6.1 and 7.1 deployed in ARC.  It is up to the vendor which version they use.

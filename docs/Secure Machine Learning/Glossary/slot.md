Slot is similar to [[batch]], except we can identify each slot in all samples. If one sample is divided into two batches, and we have 1000 samples, then there are 2000 slots in total.

The maximum number of slots is directly related to [[logN|N]].

`slot` is calculated as:

> $pow(2, sdimBits + batchBits)$
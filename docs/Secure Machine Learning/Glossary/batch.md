If there are many features(columns) in the training data, each sample is divided into multiple batches, and each batch corresponds to one slot.

Batch number is calculated as:

> $pow(2, min(log_2N - 1 - sdimBits, fdimBits))$ 

---------------
This basically says

> If there are many samples (sdimBits is large enough), batch would be $pow(2, log_2N-1-sdimBits)$ . Otherwise, using the [[featureCount]] as batch number
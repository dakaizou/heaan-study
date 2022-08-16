| Argument    | Description |
| ----------- | ----------- |
| trainfile   | Training data file path.       |
| isYfirst    | Whether the labels are in the first column in the trainfile. If `0`, the last column will be used as labels. |
| numIter     | Number of iteration to train the model. |
| [[kdeg]] | The degree of the function approximating sigmoid function, the higher the degree is, the more accurate the result will be. It will also consume more noise budget. Possible options are `3`, `5`, `7` |
| gammaUp | Learning rate parameter |
| gammaDown | Learning rate parameter |
| isInitZero |  Whether to initialize the weight vector to zero. If `0`, the weight will be initialized as the average of each column |
| fold | Divide the training data into this many folds for k-fold cross validation |
| isEncrypted | Wheter to encrypt the data using the HEAAN (CKKS) scheme. If `0`, the calculation will be done without encryption |
| testfile | Filepath to the test data. If provided, instead of k-fold cross validation, this data will be used as validation set |

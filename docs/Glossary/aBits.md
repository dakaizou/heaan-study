`aBits` is used in the function `CipherGD::encSigmoid`. 

There are two places aBits are used: `scheme.addConstAndEqual` and `scheme.multByConst`.

> scheme.addConstAndEqual(encIP2, degree3[1] / degree3[2], wBits - 2 * aBits)
> ...
> scheme.multByConst(encGrad[i], encZData[i], gamma * degree3[2], wBits + 3 * aBits)

In both places, it were used to align the operands (as `logp` and `mod`).
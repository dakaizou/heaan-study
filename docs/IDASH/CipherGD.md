`IDASH/src/CipherGD` is the bridge between HEAAN and IDASH. Most operations on the encrypted data happens here, and it can be seen as the encrypted version of `IDASH/src/GD`. For example, `CipherGD.encSigmoid` is the counterpart of `GD::plainSigmoid`

### plainSigmoid

```c++
// plainSigmoid
 for (long i = 0; i < factorDim; ++i) {

	 for (long j = 0; j < sampleDim; ++j) {
	
		 grad[i] += (degree3[0] + ip[j] * degree3[1] + pow(ip[j], 3) * degree3[2]) * zData[j][i];
	
	 }

 grad[i] *= gamma;

 }
```

### encSigmoid

```c++
scheme.addConstAndEqual(encIP2, degree3[1] / degree3[2], wBits - 2 * aBits);

 NTL_EXEC_RANGE(cnum, first, last);

 for (long i = first; i < last; ++i) {

	 // grad[i] *= gamma * degree3[2]
	
	 scheme.multByConst(encGrad[i], encZData[i], gamma * degree3[2], wBits + 3 * aBits);
	
	 scheme.reScaleByAndEqual(encGrad[i], wBits);
	
	 scheme.modDownToAndEqual(encGrad[i], encIP.logq);
	
	 // grad[i] *= ip
	
	 scheme.multAndEqual(encGrad[i], encIP);
	
	 scheme.reScaleByAndEqual(encGrad[i], wBits);
	
	 // grad[i] *= ip^2
	
	 scheme.multAndEqual(encGrad[i], encIP2);
	
	 scheme.reScaleByAndEqual(encGrad[i], wBits);
	
	  
	
	 Ciphertext tmp;
	
	 // tmp = grad[i] * gamma * degree3[0]
	
	 scheme.multByConst(tmp, encZData[i], gamma * degree3[0], wBits);
	
	 scheme.reScaleByAndEqual(tmp, wBits);
	
	 scheme.modDownToAndEqual(tmp, encGrad[i].logq);
	
	  
	
	 // grad[i] += tmp
	
	 scheme.addAndEqual(encGrad[i], tmp);

 }

 NTL_EXEC_RANGE_END;
```
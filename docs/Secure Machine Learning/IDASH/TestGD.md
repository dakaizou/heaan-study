TestGD contains mostly high level operations focusing on gradient decent itself.

When [[IDASH2017 CLI arguments|isEncrypted]] is set to `1`, `testEncNLGD` or `testEncNLGDFOLD` is called, otherwise `testPlainNLGD` or `testPlainNLGDFOLD` is called.

When the [[IDASH2017 CLI arguments|testfile]] is provided, `testEncNLGD` or `testPlainNLGD` is called, otherwise `testEncNLGDFOLD` or `testPlainNLGDFOLD` is called.

----------------

# testEncNLGDFOLD
- Initialize [[fdimBits]], [[sdimBits]], [[wBits]], [[logP|pBits]] etc.
- Create `Ring`, `SecretKey`, `Ciphertext` etc.
- For each fold:
	- Encrypt the data with `cipherGD.encZData`
	- Create the encrypted weights data with `cipherGD.encWVDataZero` or `cipherGD.encWVDataAverage`
	- Calculate the encrypted gradient descent in `cipherGD.encNLGDiteration`
	- Calculate the plain gradient descent in `GD::plainNLGDiteration` for comparing the correctness at the end
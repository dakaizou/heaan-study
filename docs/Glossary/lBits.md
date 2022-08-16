This is only used in the commented out heuristic calculation for [[logQ]]

```c++
long logQ = isInitZero ? 
(wBits + lBits) + numIter * ((kBits + 1) * wBits + 2 * pBits + aBits) :
(sdimBits + wBits + lBits) + numIter * ((kBits + 1) * wBits + 2 * pBits + aBits)
```

However, `logL` also appears in the function `Scheme::addBootKey` and `logL`, `logSlots`, [[logN]] seems to be used interchangebly.
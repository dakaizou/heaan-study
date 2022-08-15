$Q$ is the noise budget in the HEAAN scheme. 

One thing to note is that although HEAAN allows $logQ$ to be passed into `scheme.encrypt`, simply pass it in doesn't actually work. Because the way HEAAN was written, $logQ$ has to be changed before compiling HEAAN (in `HEAAN/src/Params.h`)
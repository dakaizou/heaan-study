1. HEAAN
    - Compile from source
        - Platform: Ubuntu 20.04
        - Steps:
            1. Install GMP
            `sudo apt install libgmp3-dev`

            1. Compile and install NTL
            `curl -LO https://libntl.org/ntl-11.5.1.tar.gz`
            `gunzip ntl-11.5.1.tar.gz`
            `tar xvf ntl-11.5.1.tar`
            `cd ntl-11.5.1/src`
            `./configure`
            `make`
            `sudo make install`

            1. Compile HEAAN
            `git clone git@github.com:snucrypto/HEAAN.git`
            `cd HEAAN/HEAAN/lib`
            `make`

            1. Run some tests
            `cd ../run` (`HEAAN/HEAAN/run`)
            `make`
            `./TestHEAAN Encrypt`
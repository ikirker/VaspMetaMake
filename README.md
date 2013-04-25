VASP Metamakefile
=================

So, we were having some problems building VASP, and at some point I figured it would be easier to make a Makefile to build everything rather than have to tweak individual makefiles provided with the source each time.

This Makefile thus unpacks the source bundles, and attempts to build 6 versions using serial and parallel, and the 3 different options for charge reduction. Hopefully it should be easy enough to edit; it's not very cunning.

In the simplest case, to use, just have a `vasp.5.x.x.tar.gz` and `vasp.5.lib.tar.gz` source package in the current working directory, and enter:

    make -f MetaMakefile

Since the 6 different versions can be built in parallel, though, you may want to use:

    make -f MetaMakefile -j 6

Or something like that. The individual VASP builds can't be parallelised because there are unresolved dependencies, but this is handled by the MetaMakefile, which only uses -j 1 for each VASP make.

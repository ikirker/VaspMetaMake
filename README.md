VASP Metamakefile
=================

So, we were having some problems building VASP, and at some point I figured it would be easier to make a Makefile to build everything rather than have to tweak individual makefiles provided with the source each time.

This Makefile thus unpacks the source bundles, and attempts to build 6 versions using serial and parallel, and the 3 different options for charge reduction. Hopefully it should be easy enough to edit; it's not very cunning.


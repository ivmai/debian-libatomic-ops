# The atomic_ops library (libatomic_ops)

IN NEW CODE, PLEASE USE C11 OR C++14 STANDARD ATOMICS INSTEAD OF THIS PACKAGE.

This is version 7.4.4 of libatomic_ops.

You might find a more recent version
[here](http://www.hboehm.info/gc/), or
[here](https://github.com/ivmai/libatomic_ops).


## Overview

This package provides semi-portable access to hardware-provided
atomic memory update operations on a number architectures.  These might
allow you to write code:

* That does more interesting things in signal handlers.

* Makes more effective use of multiprocessors by allowing you to write
  clever lock-free code.  Note that such code is very difficult to get
  right, and will unavoidably be less portable than lock-based code.  It
  is also not always faster than lock-based code.  But it may occasionally
  be a large performance win.

* To experiment with new and much better thread programming paradigms, etc.

For details and licensing restrictions see the files in the "doc"
subdirectory.

Please address bug reports to [mailing list](mailto:bdwgc@lists.opendylan.org).


## Installation and Usage

The configuration and build scripts for this package were generated by
Automake/Autoconf.  "./configure; make; sudo make install" in this
directory should work.  For a more customized build, see the output of
"./configure --help".

Note that much of the content of this library is in the header files.
However, two small libraries are built and installed:

* libatomic_ops.a is a support library, which is not needed on some platforms.
  This is intended to be usable, under some mild restrictions, in free or
  proprietary code, as are all the header files.  See doc/LICENSING.txt.

* libatomic_ops_gpl.a contains some higher level facilities.  This code is
  currently covered by the GPL.  The contents currently correspond to
  the headers atomic_ops_stack.h and atomic_ops_malloc.h.


## Platform Specific Notes

Win32/64: src/Makefile.msft contains a very simple Makefile for building
and running tests and building the gpl library.  The core atomic_ops
implementation is entirely in header files.

HP-UX/PA-RISC: aCC -Ae won't work as a C compiler, since it doesn't support
inline assembly code.  Use cc.


## Copyright & Warranty

See doc/LICENSING.txt file.

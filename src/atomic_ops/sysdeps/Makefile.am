#General sysdep headers
sysdep_HEADERS= generic_pthread.h \
	  atomic_load_store.h \
	  aligned_atomic_load_store.h \
	  ordered_except_wr.h \
	  acquire_release_volatile.h \
	  ordered.h \
	  emul_cas.h
sysdepdir= ${includedir}/atomic_ops/sysdeps

#Headers for GCC
sysdepgcc_HEADERS= gcc/x86.h gcc/x86_64.h gcc/ia64.h \
	gcc/alpha.h gcc/arm.h \
	gcc/powerpc.h gcc/sparc.h \
	gcc/hppa.h gcc/m68k.h gcc/s390.h
sysdepgccdir=${includedir}/atomic_ops/sysdeps/gcc

#Headers for ECC
sysdepecc_HEADERS= ecc/ia64.h
sysdepeccdir=${includedir}/atomic_ops/sysdeps/ecc

#Headers for Microsoft Windows
sysdepmsftc_HEADERS= msftc/x86.h
sysdepmsftcdir=${includedir}/atomic_ops/sysdeps/msftc

#Headers for HP Compiler
sysdephpc_HEADERS= hpc/ia64.h hpc/hppa.h
sysdephpcdir=${includedir}/atomic_ops/sysdeps/hpc

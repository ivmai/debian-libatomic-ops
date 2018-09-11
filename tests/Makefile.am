EXTRA_DIST=test_atomic.template list_atomic.template

BUILT_SOURCES = test_atomic_include.h list_atomic.i
CLEANFILES = test_atomic_include.h list_atomic.c list_atomic.i

TESTS=test_atomic test_atomic_pthreads

#create the test_atomic test program
check_PROGRAMS=test_atomic test_atomic_pthreads

test_atomic_SOURCES=test_atomic.c
test_atomic_LDADD=-lpthread
test_atomic_CFLAGS=-I../src

test_atomic_pthreads_SOURCES=test_atomic.c 
test_atomic_pthreads_CPPFLAGS=-DAO_USE_PTHREAD_DEFS
test_atomic_pthreads_LDADD=-lpthread ../src/libatomic_ops.la
test_atomic_pthreads_CFLAGS=-I../src

test_atomic_include.h: test_atomic.template
	sed -e s/XX// test_atomic.template > test_atomic_include.h
	sed -e s/XX/_release/ test_atomic.template >> test_atomic_include.h
	sed -e s/XX/_acquire/ test_atomic.template >> test_atomic_include.h
	sed -e s/XX/_read/ test_atomic.template >> test_atomic_include.h
	sed -e s/XX/_write/ test_atomic.template >> test_atomic_include.h
	sed -e s/XX/_full/ test_atomic.template >> test_atomic_include.h
	sed -e s/XX/_release_write/ test_atomic.template \
					>> test_atomic_include.h
	sed -e s/XX/_acquire_read/ test_atomic.template \
					>> test_atomic_include.h

list_atomic.c: list_atomic.template
	echo "#include \"atomic_ops.h\" " > list_atomic.c
	sed -e s/XX// list_atomic.template >> list_atomic.c
	sed -e s/XX/_release/ list_atomic.template >> list_atomic.c
	sed -e s/XX/_acquire/ list_atomic.template >> list_atomic.c
	sed -e s/XX/_read/ list_atomic.template >> list_atomic.c
	sed -e s/XX/_write/ list_atomic.template >> list_atomic.c
	sed -e s/XX/_full/ list_atomic.template >> list_atomic.c
	sed -e s/XX/_release_write/ list_atomic.template >> list_atomic.c
	sed -e s/XX/_acquire_read/ list_atomic.template >> list_atomic.c

list_atomic.i: list_atomic.c
	$(COMPILE) $< -E > list_atomic.i

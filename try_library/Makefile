#!/usr/bin/make -f

MYFLAGS=-DNDEBUG

#----------------------------------------------------------------------
all: try_main


try_main.o: try_main.void try_imports.void try_header.void try_cstdarg.void try_cstdio.void try_cassert.void
	voidc $< -- $(MYFLAGS)

try_module.o: try_module.void try_imports.void try_header.void try_cstdio.void
	voidc $< -- $(MYFLAGS)

cstdio_mod.o: cstdio_mod.void try_imports.void try_cstdio.void
	voidc $< -- $(MYFLAGS)

try_main: try_main.o try_module.o cstdio_mod.o
	clang $^ -o $@


clean:
	-rm -fv try_main *.o *.voidc*



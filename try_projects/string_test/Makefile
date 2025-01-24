#!/usr/bin/make -f


#----------------------------------------------------------------------
all: try_string


main.o: main.void
	voidc $< -T


try_string: main.o
	clang $^ -o $@


clean:
	-rm -fv try_string *.o
	-rm -fvr __voidcache__



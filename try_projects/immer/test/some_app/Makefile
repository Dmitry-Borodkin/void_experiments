#!/usr/bin/make -f


#----------------------------------------------------------------------
all: some_app


main.o: main.void
	voidc $< -T


some_app: main.o
	clang $^ -o $@


clean:
	-rm -fv some_app *.o
	-rm -fvr __voidcache__



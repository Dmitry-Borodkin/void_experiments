#!/usr/bin/make -f

LIBS=$$(pkg-config gtk+-3.0 --libs) $$(pkg-config fontconfig --libs)


#----------------------------------------------------------------------
all: try_app


main.o: main.void
	voidc $< -T


try_app: main.o
	clang $^ $(LIBS) -o $@


clean:
	-rm -fv try_app *.o
	-rm -fvr __voidcache__



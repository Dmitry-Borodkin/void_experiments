#!/usr/bin/make -f

LIBS=$$(pkg-config gtk+-3.0 --libs)


#----------------------------------------------------------------------
all: gtk_tries


main.o: main.void
	voidc $< -T


gtk_tries: main.o
	clang $^ $(LIBS) -o $@


clean:
	-rm -fv gtk_tries *.o
	-rm -fvr __voidcache__


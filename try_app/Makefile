#!/usr/bin/make -f

MYFLAGS=-- -DNDEBUG

LIBS=$$(pkg-config gtk+-3.0 --libs) $$(pkg-config freetype2 --libs)


#----------------------------------------------------------------------
all: try_app


main.o: main.void imports.void
	voidc $< $(MYFLAGS)


try_app: main.o
	clang $^ $(LIBS) -o $@


clean:
	-rm -fv try_app *.o *.voidc*



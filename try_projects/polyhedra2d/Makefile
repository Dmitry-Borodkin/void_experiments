#!/usr/bin/make -f

#MYFLAGS= -T -- -DNDEBUG
MYFLAGS= -T

#----------------------------------------------------------------------
all: try_geom


geometry_mod.o: geometry_mod.void imports.void geometry.void cstdarg.void cstdio.void type_traits.void
	voidc $< $(MYFLAGS)

geomobjects_mod.o: geomobjects_mod.void imports.void geometry.void geomobjects.void cstdarg.void cstdio.void type_traits.void
	voidc $< $(MYFLAGS)

trigroup_mod.o: trigroup_mod.void imports.void geometry.void cstdarg.void cstdio.void type_traits.void
	voidc $< $(MYFLAGS)


try_geom.o: try_geom.void imports.void geometry.void geomobjects.void cstdarg.void cstdio.void type_traits.void trigroup.void
	voidc $< $(MYFLAGS)

try_geom: try_geom.o geometry_mod.o geomobjects_mod.o cstdio_mod.o trigroup_mod.o
	clang $^ -lm -fsanitize=address -o $@


cstdio_mod.o: cstdio_mod.void imports.void cstdarg.void cstdio.void
	voidc $< $(MYFLAGS)





clean:
	-rm -fv try_geom *.o
	-rm -fvr __voidcache__



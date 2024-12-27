#!/usr/bin/make -f

#MYFLAGS= -T -- -DNDEBUG
MYFLAGS= -T

#----------------------------------------------------------------------
all: try_geom


geometry_mod.o: geometry_mod.void geometry.void
	voidc $< $(MYFLAGS)

geomobjects_mod.o: geomobjects_mod.void geometry.void geomobjects.void
	voidc $< $(MYFLAGS)

trigroup_mod.o: trigroup_mod.void geometry.void trigroup.void
	voidc $< $(MYFLAGS)


try_geom.o: try_geom.void geometry.void geomobjects.void trigroup.void
	voidc $< $(MYFLAGS)

try_geom: try_geom.o geometry_mod.o geomobjects_mod.o trigroup_mod.o
	clang $^ -lm -fsanitize=address -o $@




clean:
	-rm -fv try_geom *.o
	-rm -fvr __voidcache__



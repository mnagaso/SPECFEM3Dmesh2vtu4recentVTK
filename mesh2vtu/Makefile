# Makefile

#############################################################
## modify to match your compiler defaults
CXX=g++

## modify to match your library paths
# VTK libraries
VTK=/usr/local
VER=8.90
#LIBS=-L$(VTK)/lib/libvtkCommonCore-$(VER).so.1 -L$(VTK)/lib/libvtkIOCore-$(VER).so.1 -L$(VTK)/lib/libvtkRenderingCore-$(VER).so.1 -L$(VTK)/lib/libvtkFiltersCore-$(VER).so.1 -L$(VTK)/lib/libvtkDataModel-$(VER).so.1 -L$(VTK)/lib/libvtkIOXML-$(VER).so.1 -L$(VTK)/lib/libvtksys-$(VER).so.1 -L$(VTK)/lib/libvtkloguru-$(VER).so.1  -lvtkCommonCore-$(VER) -lvtkIOCore-$(VER) -lvtkRenderingCore-$(VER) -lvtkFiltersCore-$(VER) -lvtkCommonDataModel-$(VER) -lvtkIOXML-$(VER) -lvtksys-$(VER) -lvtkloguru-$(VER)  #-lvtkGraphicsCore-$(VER)
LIBS=-L$(VTK)/lib/  -lvtkCommonCore-$(VER) -lvtkIOCore-$(VER) -lvtkRenderingCore-$(VER) -lvtkFiltersCore-$(VER) -lvtkCommonDataModel-$(VER) -lvtkIOXML-$(VER) -lvtksys-$(VER) -lvtkloguru-$(VER)  #-lvtkGraphicsCore-$(VER)


INCLUDES=-I$(VTK)/include -I$(VTK)/include/vtk-$(VER) #-I/VTK/build/Common/Core -I/VTK/Common/Core -I/VTK/Utilities/KWIML -I/VTK/Common/DataModel -I/VTK/build/Common/DataModel
CPPFLAGS= -O3 $(INCLUDES) -Wno-deprecated

#############################################################


all: mesh2vtu ugrid ugrid_pts

mesh2vtu: mesh2vtu.o
	$(CXX) $(CPPFLAGS) -o mesh2vtu mesh2vtu.o $(LIBS)

mesh2vtu.o: mesh2vtu.cxx
	$(CXX) $(CPPFLAGS) -c mesh2vtu.cxx -o mesh2vtu.o

ugrid: ugrid.o
	$(CXX) $(CPPFLAGS) -o ugrid ugrid.o $(LIBS)

ugrid.o: ugrid.cxx
	$(CXX) $(CPPFLAGS) -c ugrid.cxx -o ugrid.o

ugrid_pts: ugrid_pts.o
	$(CXX) $(CPPFLAGS) -o ugrid_pts ugrid_pts.o $(LIBS)

ugrid_pts.o: ugrid_pts.cxx
	$(CXX) $(CPPFLAGS) -c ugrid_pts.cxx -o ugrid_pts.o

clean:
	rm -f mesh2vtu ugrid ugrid_pts *.o *~ core

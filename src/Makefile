FC       = gfortran
FCFLAGS  = -O3 -cpp
FCFLAGS += -fopenmp
FCFLAGS += -Wall -fbounds-check -fbacktrace -g -pg -ffpe-trap=invalid,zero,overflow -std=f2008

TARGET = Ising2d_relaxation.out Ising2d_equilibirum.out

all: $(TARGET)

Ising2d_relaxation.out: Ising2d_relaxation.f90 Ising2d_m.o Ising2d_m.mod
	$(FC) $(FCFLAGS) -o $@ $< Ising2d_m.o
Ising2d_equilibirum.out: Ising2d_equilibirum.f90 Ising2d_m.o Ising2d_m.mod
	$(FC) $(FCFLAGS) -o $@ $< Ising2d_m.o

Ising2d_m.o: Ising2d_m.f90
	$(FC) $(FCFLAGS) -c $<
Ising2d_m.mod: Ising2d_m.f90
	$(FC) $(FCFLAGS) -c $<

clean:
	rm -f *~
distclean:
	rm -f *~ *.out *.mod *.o
force:

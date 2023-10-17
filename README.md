# LAMMPSworkshop
LAMMPS/MD simulation resources and example simulation of pure water



Resources: 

LAMMPS manual: https://docs.lammps.org/Intro.html

LAMMPS git: https://github.com/lammps/lammps

Useful pre/post processing tools including GUI, builds, visualizers, etc.: https://www.lammps.org/prepost.html

Water model review paper: https://pubs.acs.org/doi/10.1021/acs.jcim.1c00794?ref=pdf


Instructions: (requires CMake, MPI, openmp, some CLI skills, linux/mac only)
I make no guarantees that this workflow will work for everyone, if you have issues send me an email, rileyvic@umich.edu
Also, if you've never installed software/used the command line, think of this as a jump into the (relatively shallow) deep end,
google is your friend, copy and paste any error message you get to search for other people's solutions. 

Clone lammps from git:

    git clone https://github.com/lammps/lammps

Create build directory within lammps directory:

    cd lammps
    mkdir build
    cd build

Use cmake to flag the necessary tools for a generally useful LAMMPS install: (will take some time)

    cmake -C ../cmake/presets/most.cmake -D BUILD_MPI=yes -D BUILD_OMP=yes .

Install the lmp executable:

    make install

Check that lmp is in the right place: (should return /usr/local/bin/lmp or something similar)

    which lmp

If it isn't there, from the build directory: (may need to add sudo to the beginning)

    cp lmp /usr/local/bin/lmp

At this stage, you have LAMMPS installed and can use it to run a simulation.
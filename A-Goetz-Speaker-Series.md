# Quantum mechanics machine learning and computational chemistry
Chemistry: the central science

a lot of different sciences are built on chemistry

the purpose of the project is to create simulations to provide insight prediction and design of chemical reactivity, biological function material properties and catalyst activities

the scho0dinger equation is necessary, but it cannot be solved without expansive data in approximations

instead often we use force field functions. These are fast but less accurate

scaling the number of electrons is very expensive. Even when computing power doubles, the number of atoms that can be analyzed cannot be calculated

4 water molecules might take 100 * 100 hours

we must implement quick quantum chemistry code

## QUICK
Gaussian bases set hartree fock and dnesity functional theory calculations

serial, mpi parrallel cpu, single and multi GPU

QM/MM Interface to amber molecular dynamics package

how do we speed things up?
multiple parallel processing units

### Parallel numerical quadrature
octree based parititoning of 3d grid points

prescreening of function values on grid point batches leads to linear scaling for large molecules

grid point batches are processsed in cuda

## Benchmark example
Molecular dynamics:

amber code Atomistic simulations of condensed phase biomolecular

we can simulate the activity of enzymes, oxdase enzyme for instance, that takes protons and oxygen to make water

however activity can happen in femto seconds to seconds. How do we compute relationships over such a huge range of times

the main issue is using rules to predict how interactions will work given environmental conditions for an enzyme or molecule, and then operating that simulation.

### Why simulations?
because often with aerosol particles for instance, its hard to run experiments determining particle interactions. However, with simulations it becomes much easier

we can use machine learning to analyze the molecular structural interactions, like the strength of electric force as distance inscreases or decreases

## Summary
* Quantum mechanics govern molecular and materials structure and property
* efficient accurate approximations exist to solve the electronic shrodinger equation
empirical approximations are requird to performsumulations 
these computations are veruye expensive and high performance parallel computing implementations are required
machine learning can help accelerate these simulations
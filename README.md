# Singularity MPI Container
This repository provides the singularity mpi containers.  These containers are for usage in singularity **hybrid-model**. 

The Open MPI/Singularity workflow in detail:

1. The MPI launcher (e.g., `mpirun`, `mpiexec`) is called by the resource manager or the user directly from a shell.

2. Open MPI then calls the process management daemon (ORTED).

3. The ORTED process launches the Singularity container requested by the launcher command.

4. Singularity instantiates the container and namespace environment.

5. Singularity then launches the MPI application within the container.

6. The MPI application launches and loads the Open MPI libraries.

7. The Open MPI libraries connect back to the ORTED process via the Process Management Interface (PMI).

For more about singularity mpi, please refer to https://sylabs.io/guides/3.5/user-guide/mpi.html.

### Usage

```
Singularity build openmpi.simg openmpi-ib.sif
mpirun -np 2 singularity exec openmpi.simg hostname
```

 **More MPIs to be added...**

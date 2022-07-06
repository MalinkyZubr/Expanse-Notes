# Expanse tutorial notes
## logging onto expanse
1. have an expanse account
2. expect issues
3. use ssh
4. Have a PI with a project to join

ssh username@expanse.sdsc.xsede.org
then enter password

1. log in 
Try using an ssh agent

## Login nodes
DO NOT RUN PARALLEL CODE ON THE LOGIN NODES
they are meant for configuration. Request interactive nodes for jobs

dont use it for data transfer. There are data movememnt systems for that
dont use it for hosting services accepted on the internet
dont run jupyter notebooks

## Environment modules

Expanse uses Lmod, a lua based module system

users setup custom environments including needed comilers and libraries and the batch scheduler

what modules are:
users setup custom environments by loading available modules into the shell environment, including compilers libraries and the batch scheduler

what do they let you do?
Dynamic modification olf your environment

Users must load scheduler, and load a compiler to see available modules

use the command "module spider" to see if a package exists and can be loaded

for additional details, and to identify module dependencies, module spider <application name>

the module paths are different for GPU and CPU nodes, you can do 
module load cpu
module load gpu

dont do both at once!

## Commands:
1. module list: list the modules that are currently loaded
2. module avail: list the modules that are available in the environment
3. module spider: list of the modules and extensions available
4. module display (module_name):show the environment variables used by the module and how they are affected
5. module unload (module name): remove the module from the environment
6. module swap (module one) (module 2): replace the module one with module two in the environment
7. module help: get a list of commands that the module knows about
8. module show (module name): show what module does
9. module purge: purge all modules

## command not found?
Sometimes when switching from one shell to another or attempting to run the module command from within a batch job
moduel commands may not be inherited into the shell
to prevent this from appening, execute the folloiwing:
from the command line: run
source /etc/profile.d/modules.sh

or add your shell script

## Multiple Allocations
Many users will have access to multiple accounts and hence projects

allocation is for a research project and a separate allocation for classroom or education use

users should verify that the correct project is designated for all their batch jobs

awards for allocations are granted for specific purposes, dont misuse them!

to charge your job to one of your pro0jects, replace <<project>> with one from your list and put it into the PBS directive in your job script

"#SBATCH _A <<project>>"
"srun -account=<<project>>"

To get your allocation information, you need to do 
1. module load sdsc
2. expanse-client user
3. expanse-client user -r expanse_gpu

Charging:
Charge unit for all SDSC machines including expanse is the service unit, SU 
1 CPU cor using <= 2g of data for 1 hour
or 1 GPU using < 96G of data for one hour

shared partitions: based on the number of cores or fraction of memory requested whichever is larger
save cpu costs by sharing a node with other people. If you have surplus of cores

minimum charge of 1 SU for a job. Remember to kill jobs not in use

## Compiling and lnking code
CPU:
GNU, Intel, AOCC (AMD) compilers are all available

multiple MPI implenentations
a majlority of the applications were build using gcc 10.2.0

differeing performance of compilers. You must optimize, and test each one. 

CPU and GPU nodes are different

the AMD optimization compiler for C and C++ is only available on CPU nodes

amd can be loaded using module load aocc

for help on amd compilers do:
flang/clang -help

flang is fortran, clang is c and C++

## Parallel Models:
For compiling there are two kinds of jobs. Distributed memory and shared memory
Distributed memory, runs on discrete CPU resources, must go through remote interocnnection for parallelization, distributed services, etc
MPI is the message passing interface
optimized for every machine

shared memory on HPC

if you have 128 cores they cna all share data
all CPUS are connected to a common memory through a single interconnection pipe

## Running jobs on expanse
run jobs on batch mode, let the slurm scheduler find the nodes you need. Have the code ready to launch, then slurm will launch the code. ONLY ON COMPUTE NODES

limits on the number of jobs to queue up and run, and those you can partition

try to collect jobs into one large jobs, lots of small ones mess with the system

you can use slurm scheduler, or in interactive mode

srun creates interactive session. 
Slurm: make script, submit to slurm, tell it what to do, and it will do what you say on the required number of nodes
srun: obtain nodes for live command line interactive access to the job

CPU:
srun --partition=debug --account=(account number/name) --pty --nodes=1 --ntasks-per-node=128 --mem=248 -t 00:30:00 --wait=0 --export=ALL /bin/bash

GPU:
srun --pty --account=(account number/name) --nodes=1 --ntasks-per-node=1 --cpus-per-task=10 -p gpu-debug -gpus=1 -t 00:10:00  /bin/bash

## Slurm
Simple linux utility for resource management

glue for parallel computer

take request, lots of services
take request
how much memory?
how much time?
nodes?
name of code?
other arguments?
whats the best set of nodes to run the script?

automates the setup process for running jobs

receive  ajob id, and get notification the job is running. Submit a batch script to run on slurm

## Slurm partitions on expanse
basically the types of nodes
compute: regular compute nodes, large jobs
shared: single node jobs using fewer than 128 cores
gpu: used for exclusive access to the GPU nodes
gpu-shared: single node job using fewer than 4 gpus
large shared, single node jobs using memory up tot 2 TB
debug: priority access to compute nodes set aside for testing of jobs with short wait time and limited resources

## Common slurm commands
submit jobs:
sbatch mycode-slurm.sb
returns job ID

check job status using the squeue command:
squeue -u $USER
returns all jobs assigned to a user

Monitor running job:
squeue -u $USER
show progress on the job you are running

cancel a job:
scancel (job id)

## batch scripting
l;earn bash scripting
"#SBATCH" keyword: parse the following scripts and put it into a slurm job

## Filesystems
logon: home directory, login nodes

lustre filesystems: good for scalable large block IO

Local node scratch: stores data on job. Will be deleted when job is done, so remember to move it out before that happens!

Lustre filesystem: 12 pb lustre parallel file system

everyone has a default location

best for scalable large block IO. DO NOT DO SMALL FILE TRANSFER IO. IT WILL CRIPPLE THE HPC SYSTEMS DO NOT DO THIS

scratch storage is local on a node. At the very end, all the data is gone. Movde the data back into the lustre system

## Globus
Use for very large jobs, manages all the backend activity and storage. Automates data movmeemnt asynchronously. Very efficient and optimized

## examples
get examples from expanse 101 repository


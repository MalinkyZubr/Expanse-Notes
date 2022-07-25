# Data management
what is data mangement?
moving and controlling data after processing

mechanisms:
external hard drives, remote machines
hard drives on local machine
supercomputer

## traditional data management tools
1. scpL secure copy (remote file copy program)
2. sftp secure file transfer 
3. rsync, fast versatile copying tool from remote computer

### Open Science Chain
utilizes blockchain to store information abpout data and data in general to track and manage. Open Science chain.org
very good if the datasert is evolving and you want live tracking of its data and metadata

### hpcshare 
very useful for sharing data from and on hpc systems

can also create small visualizations of file formats, json and csv only however

performance and scalability of application

Globus:
a tool that provides fast secure and reliable file transfer and data sharing mechanisms

https://www.globus.org 

to use globus with a supercomputer it must connect to your own machine

https://www.globus.org/globus-connect-personal

shell commands like scp and sftp are also good
rsync and aspera also work

## Expanse's tiered storage
Node local NVME drives for workloads that dont need to share data files across nodes

Lustre filesystem for IO workloads that require high bandwidth and large capacity shared storage

Network files system cluster for user home directory stoage

ceph object storage for short term storage during jobs

why so many filesytstems?
performance
shared access across nodes
backup, long term storage
quotas

Application focus:
storage choices should be driven by application need, but applications need to adapt as they scale

writing a few small files to an nfs server is fine, writing 1000s simultanously will annihilate the server

NFS: NO BIG FILES, ONLY 100 GB STORAGE!!!
storage is backed up

LUSTRE SCRATCH FILE SYSTEM IS TEMPORARY FOR PROJECT OUTPUT. ALWAYS MOVE IT OUT OR BACK IT UP. PURGED AFTER 90 DAYS
the LFS typically used to store large output and input files, for project specific uses
allows distributed access
Storage limit around 2.5 PB

LFS regular for a project lasts until the project ends, if there is no renewal. It is not automatically backed up!

node local ssd storage
typically used to store large numbers of small files
fast node local access
storage limits compute shared 1 tb gpu gpu shared 1.5 tb large shared 3.2

only accessible from a compute node
purged after job. in the script running, make it copy out the data to somewhere else

## Guidelines
lustre scratch: /exapnse/lustre/scratch/$USER/temp_project
storing data for active simulations
not backed up
90 day purge policy
large block scalable IO

compute GPU node local NVMe storage: /scratch/$USER/job_$SLURM_JOBID
meta data intensive jobs, high IOPs
file per core type IO with continuous writes
purged at end of the job

Lustre projects space: /expanse/lustre/projects/GROUP/$USER

home directory: /home/$USER: Only for source files, libraries, binaries. DO NOT USE IT FOR ANY IO INTENSIVE JOB

## Magnitude Guide

Storage     | file/directory      | file sizes      | BW
local HDD   | 1000s               | GB              | 100 MB/s
local NVMes | 1000s               | GB              | 1000 MB/s
RAM FS      | 10000s              | GB              | Several GB/s
NFS         | 100s                | GB              | 100 MB/s
LUSTRE      | 100s                | TB              | 100 GB/s

the LFS can also distribute files across multiple OSTs in a process called striping, in case those files cant fit in one place. This also helps improve3 the bandwidth of operations

## LFS Commands
1. lfs help: list all commands available
2. lfs getstripe (file_name): display the stripe data of a file
3. lfs setstripe -c 16 testout




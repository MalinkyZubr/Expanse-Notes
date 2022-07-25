# Running Jupyter Notebooks on Expanse
DO NOT RUN JUPYTER NOTEBOOKS ON THE LOGIN NODE! THEY WILL BE DELETED!

important and convenient to have customize virtual python environemnts

recommended to use miniconda

optionally you could use singularity containers. These are harder to use hwoever

### creating a conda environment
conda create --name example_env

to see which virtual environments have been created:
conda env list

to run a virtual environment:
source activate example_env
dont use conda activate

install JupyterLab and JupyterNotebooks

NOTE:
By default environment files are stored in the home directory, so either run the envioronment in a batch node (not jsrun) or find a way to force conda to store environment files in your own work node

if you launch the notebook from the home directory, you wont be able to run notebooks from the project directory

jupyter labs also allows you to have terminal windows open

lots are hosted on jupyter hub, so people can collaborate and share resources

### WARNING: THE JUPYTER NOTEBOOK URL IS A PASSWORD. IT GIVES ACCES TO YOUR SYSTEM. ANYONE WHO GETS ACCESS TO IT CAN GET ACCESS TO THE SYSTEM. SHUT DOWN THE NOTEBOOK AND EXIT COMPLETELY WHEN DONE. BY DEFAULT THE NOTEBOOKS ARE RUN ON HTTP, AND CAN BE HACKED WHEN COMMUNICATING WITH THE SERVER

the ideal configuration:

SSH encryption for all messages https connection to client 

runs isolated machine proxy through JH Website.

This is achieved by the reverse proxy service and jupyterhub both running on VM

no apps on the login nodes

use secure connections hwerever and whenever possible

## Methods for running notebooks on expanse
even when ssh is used to connect and start running the jupyter server, the server itself operates on HTTP. Basically, the initial connection is secure, but the connection it establishes is not

SSH Tunneling is very secure. However it does have some problems, and its a bit more complicated. Takes some learning, and not entirely stable

ssh tunnel:
1. create ssh connection, and open jupyter notebook on http. 
2. set up the ports on the jupyter notebook and your laptop to operate an ssh tunnel

using local port forwarding to connect to a jupyter notebook server:
1. ssh -L 8888:127.0.0.1:8888 username@expanse.sdsc.edu
2. then launch the jupyter notebook using jupyter notebook --no-browser --ip=`/bin/hostname`

## The reverse proxy service
ideally a way to simplify the entire process. Takes a request from a remote client, processes it, returns information to the user and the server. Creates a firewall between the remote service and client

For jupyter notebooks:
1. login to expanse
2. run slurm batch srun -> reverse proxy service
3. comet compute nodes -> reverse proxy service
4. https connection through the reverse proxy to the compute node

RPS is a prototype system. The notebooks are hosted internally and avaialable to use as an HTTPS connection. Once its learned

to use RPS:
1. SSH to an expanse login node
2. Activate the conda environment from a bashrc or yaml file
3. clone the repo git clone https://github.com/sdsc-hpc-training-org/reverse-proxy.git
4. check software environment on the login node to make sure its functioning


From within the RPS repo you will want to use start-jupyter

./start-jupyter -help

the newest version of the server uses the .config to configure the system. There are ways to directly configure the machine

remember to load the slurm module

### Always do these things
module load slurm BEFORE starting jupyter notebook

then take the notebook link and put it in the search browser. Make sure it is kept safe

however, the first thing youll get is a waiting page, which wont go away until something is running in the queue

how long will it take for it to go away? we dont know. If the job is running and you wait too long, something is wrong, and you should submit a note

## Live Demo
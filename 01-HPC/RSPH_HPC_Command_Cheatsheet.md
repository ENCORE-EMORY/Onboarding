

# RSPH HPC Command Cheatsheet
Weiwei Wu (weiwei.wu@emory.edu)   
AUG 2024

- [1- Login](#1--login)
- [2- Cluster Information](#2--cluster-information)
- [3- Transferring Files](#3--transferring-files)
- [4- Linux Commands](#4--linux-commands)
- [5- Modules](#5--modules)
- [6- Submitting Jobs](#6--submitting-jobs)
- [7- Shell Example](#7--shell-example)
    - [1) Standard Serial Job](#1-standard-serial-job)
    - [2) Job Arrays](#2-job-arrays)
    - [3) GPU Job](#3-gpu-job)
- [8- Running R using Jupyter Notebook](#8--running-r-using-jupyter-notebook)
- [9- Running Interactive Session on Compute Node](#9--running-interactive-session-on-compute-node)





<br>

!! Notice: This is not an HPC tutorial. For detailed HPC instructions, please refer to the [BIOS at RSPH – HPC Documentation](https://scholarblogs.emory.edu/rsph-hpc/)  

<br>

### 1- Login  
```bash
ssh <your_netID>@clogin01.sph.emory.edu
```
<br>

### 2- Cluster Information
- View available partitions and notes  
```bash
sinfo
```
- View all running and queued jobs  
```bash
squeue
```
- View nodes details  
```bash
scontrol show node node243 # Amount of memory, cpus, GPUs for node243
```
<br>

### 3- Transferring files  
- Upload file to HPC  
```bash
scp –r NetID@clogin01.sph.emory.edu:<local_file_path> <hpc_file_path>
```
- Download file to HPC  
```bash
scp –r <hpc_file_path> NetID@clogin01.sph.emory.edu:<local_file_path> 
```

- More interactive choice: Use SCP client, e.g. FileZilla, WinSCP, Cyberduck   
<br>

### 4- Linux Commands  
```bash
cd <dir_name>      # navigates into the directory “dir_name”
ls <dir_name>      # lists all files and directories in the current directory
pwd                # print working directory
cp <from_file_path> <to_file_path>
                   # copy file
cp -r <from_folder_path> <to_folde_path>
                   # copy entire folder
rm <file_name>     # permanently delete the file “file_name”
rm -r <file_name>  # permanently delete entire folder
nano <file_name>   # opens the text editor with “file_name” open
cat <file_name>    # display entire file
du -sh             # check the usage of current folder
du -sh <specific_folder>
                   # check the usage of certain folder
Ctl-c              # kill current command
Ctl-z              # suspend current command
man cp             # manual page for command
```
<br>

### 5- Modules  
- Available module  
```bash
module available
```
- Information about a specific module  
```bash
module spider <module_name>
```
- Load module  
```bash
module load <module_name>
```
  Load model of specific version: `module load R/4.4.0`  
  
- Unload module  
```bash
module unload <module_name>
```
- Lists all currently loaded modules  
```bash
module list
```
<br>

### 6- Submitting Jobs
- Submit a job  
```bash
cd <location of your shell/slurm>
sbatch <your_shell/slurm_file>
```
- View your jobs  
```bash
squeue --me
```
- Cancel a job  
```bash
scancel <job_ID>
```
- View job status while running  
```bash
sstat -j <job_ID>
```
<br>

### 7- Shell Example  
##### 1) Standard Serial Job  
Request for 1 node, 4 cores, 4Gb memory (1G per core), 1 hour run time on the partitions 'preemptable' and 'week-long-cpu'. The job name is `hello_world`. The output and error file name are `job_<job_ID>.out` and `job_<job_ID>.err`.     
```bash
#!/bin/bash
#SBATCH --job-name=hello_world 
#SBATCH --nodes=1
#SBATCH --ntasks-per-node=4
#SBATCH --mem-per-cpu=1G
#SBATCH --time=01:00:00
#SBATCH --partition=preemptable,week-long-cpu
#SBATCH --output=job_%J.out
#SBATCH --error=job_%J.err
#SBATCH –-mail-user=<YOUR_EMAIL_ADDRESS@emory.edu>
#SBATCH –-mail-type=<NONE, BEGIN, END, FAIL, REQUEUE> 

R_SCRIPT_DIR="/projects/compbio/users/<your_NetID/your_project/scripts>"
cd $R_SCRIPT_DIR

<Load modules / Activate environment>
<run application>
```
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;Run R script: `Rscript <your_R_script_name>.R`   
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;Run Python script: `Python <your_R_script_name>.py`  
&ensp;&ensp;&ensp;&ensp;&ensp;`srun` command can also be used for running scripts.  
<br>

##### 2) Job Arrays  
  Request for 20G per core, 1 hour run time on the partitions 'preemptable' and 'week-long-cpu'. The job name is `my_batch_job`. 1000 job instances, one for each index 1, 2, 3, ..., 1000. The output and error file name are `job_<job_ID>_<array_number>.out` and `job_<job_ID>_<array_index>.err`.   
  
```bash
#!/bin/bash

#SBATCH --job-name=my_batch_job
#SBATCH --mem-per-cpu=20G
#SBATCH --time=01:00:00
#SBATCH --partition=preemptable,week-long-cpu
#SBATCH --array=1-1000
#SBATCH --output=job_%A_%a.out
#SBATCH --error=job_%A_%a.err
#SBATCH –-mail-user=<YOUR_EMAIL_ADDRESS@emory.edu>
#SBATCH –-mail-type=<NONE, BEGIN, END, FAIL, REQUEUE, ALL> 

echo "I am job $SLURM_JOBID running on nodes $SLURM_JOB_NODELIST"

R_SCRIPT_DIR="/projects/compbio/users/<your_NetID/your_project/scripts>"
cd $R_SCRIPT_DIR

<Load modules / Activate environment>
<run application>

echo "Completed job on node $HOSTNAME“
```
<br>

##### 3) GPU Job  
```bash
#!/bin/bash

#SBATCH --job-name=my_gpu_job
#SBATCH --time=01:00:00
#SBATCH --partition=<name_of_GPU_partition>
#SBATCH --output=%x_%j.out
#SBATCH --error==%x_%j.err
#SBATCH –-mail-user=<YOUR_EMAIL_ADDRESS@emory.edu>
#SBATCH –-mail-type=<NONE, BEGIN, END, FAIL, REQUEUE, ALL> 

#SBATCH –-nodes=1             # Number of nodes
#SBATCH –-ntasks-per-node=1   # Number of tasks per node
#SBATCH --cpus-per-task=2     # Number of cores per task 

echo "I am job $SLURM_JOBID running on nodes $SLURM_JOB_NODELIST"

R_SCRIPT_DIR="/projects/compbio/users/<your_NetID/your_project/scripts>"
cd $R_SCRIPT_DIR

<Load modules / Activate environment>
<run application>

echo "Completed job on node $HOSTNAME“
```
<br>

### 8- Running R using Jupyter Notebook  
- Login  
```bash
ssh -L 8999:localhost:8999 <your_netID>@clogin01.sph.emory.edu
```
- Allocate Computation Resources on the HPC  
	Apply for *1* CPU core, *1*0GB memory, *8* hours on the *interactive-cpu* partition  
```bash
salloc -p interactive-cpu -n 1 -t 0-8:00 --mem=10000
```
- Switch allocated node  
```bash
ssh -L 8999:localhost:8999 $SLURM_JOB_NODELIST
```
- Activate your R environment  
```bash
cd <location_of_your_project>
conda activate <your_r_environment_name>
```
- Start Jupyter server  
```bash
jupyter notebook --NotebookApp.token='' --no-browser --port=8999
```
- Open Jupyter Notebook at Local Machine  
	Open a browser, visit [http://localhost:8999](http://localhost:8999/)  
- Monitor the memory/CPU resources  
```bash
top -o %MEM
kill -9 PID
```
- Deactivate the environment when you are done  
```bash
conda deactivate
```
<br>

### 9- Running Interactive Session on Compute Node
- Start an interactive job using command `srun` on login node `cloin01`   
  Start an interactive job on the interactive-cpu partition, with 1 node, 4 cores, 1G memory per core and 30 minutes run time. 
```bash
srun --pty --partition=interactive-cpu --nodes=1 --ntasks-per-node=4 --mem-per-cpu=1G --time=00:30:00 bash
```
- Run  
```bash
<load module>
<start the module>
```

- Example: Run R interactively   
      
    ```bash
    module load R/4.4.2
    R
    ```
    
- Example: Run Python interactively  
    
    ```bash
    module load python/3.8
    python3
    ```
<br>

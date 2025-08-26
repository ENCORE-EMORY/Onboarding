# Onboarding
Here is the training resource for new ENOCRE lab members

- [I. High Performance and Cloud Computing Cluster](#i-high-performance-and-cloud-computing-cluster)
  - [1- RSPH HPC](#1--rsph-hpc)
    - [1.1- Get Started with RSPH HPC](#11-get-started-with-rsph-hpc)
    - [1.2- Environment Setup and Job Submission](#12-environment-setup-and-job-submission)
    - [Link for HPC Command Cheatsheet](01-HPC/RSPH_HPC_Command_Cheatsheet.md)
  - [2- Access RSPH HPC and ENCORE Folder](#2--how-to-access-the-rsph-hpc-and-encore-folder)

- [II. Share Folder for ENOCRE member](#ii-share-folder-for-enocre-member-optional) (optional)
  - [1- How to map ENCORE shared folder](#1--how-to-map-encore-shared-folder)
  - [2- Current ENCORE folder structure](#2--current-encore-folder-structure)
- [III. Scientific Writing and Presentations](#iii-scientific-writing-and-presentations)
- [IV. Research Resource](#iv-research-resource)
  - [Bioinformatics](#bioinformatics)
  - [Linux](#linux)
  - [Python](#python)
  - [R](#r)
  - [Jupyter Notebook](#jupyter-notebook-recommended-for-programing-with-python)
  
<br />
<br />

# I. High Performance and Cloud Computing Cluster

### 1- RSPH HPC
*[Official RSPH-HPC Documentation](https://scholarblogs.emory.edu/rsph-hpc/)*

The RSPH HPC cluster is a system that consists of 25 compute nodes, 24 of which have 32 compute cores and 192GB of RAM each. The last node is a “large memory node” with 1.5 TB of RAM. These systems are connected together via 25GB Ethernet network, and all have access to a shared 1 Petabyte Panasas parallel file system.

In addition to the hardware, the system runs the CentOS Linux operating system (currently version 8), which is a “white-box” implementation of the Red Hat Enterprise Linux OS that purports to be 100% binary compatible with the commercial version.

Job scheduling is handled by the SLURM job scheduler, an application that currently runs on most of the Top 500 supercomputing sites in the world.


#### 1.1 Get Started with RSPH HPC
1) HPC documentation [link](https://scholarblogs.emory.edu/rsph-hpc/getting-started/) from the BIOS department. This guide is more hands-on than the one initially shared in the HPC welcome email
2) BIOS Introduction Session on RSPH HPC: [slides](https://scholarblogs.emory.edu/rsph-hpc/files/2020/11/2020-11-20-BIOS-HPC-Workshop.pdf) [recording](https://rsph.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=a9e7a90f-055c-4753-9e51-ac7a003b9d58)
3) Interactive R Coding with Jupyter Notebook: [tutorial](https://github.com/Environment-and-Seniors-Health-Emory/Getting_started/blob/main/HPC_cluster_GUI_Jupyter_Guide.md) by Dr. Liuhua Shi from the EH department
4) Unix command line: Dr. David Benkeser’s [DATA/INTRO 550 course](https://benkeser.github.io/info550/lectures/) provides a detailed lecture on using the Unix command line [slides](https://benkeser.github.io/info550/lectures/03_commandline/commandline.html#1) [recording](https://benkeser.github.io/info550/recordings/unix-command-line)
5) \***HPC Cheat Sheet** in this ENCORE GitHub [HPC Command Cheatsheet](01-HPC/RSPH_HPC_Command_Cheatsheet.md) with some template codes that might be helpful if you are new to the SLURM job scheduler
6) SCP Clients for File Transfer: [FileZilla](https://filezilla-project.org/) works well on both Windows and macOS. Some people prefer [Cyberduck](https://cyberduck.io/) for macOS   
7) \***Folder Setup**: It’s best to create your own folder named with your NetID under either `/projects/compbio/users/` (ENCORE) or another PI's folder instead of using your home directory, since the home directory has a 25 GB quota limitation. You can see storage limits for the ENCORE folder below

#### 1.2 Environment Setup and Job Submission
1) Conda Environment Setup: [Conda documentation](https://docs.conda.io/projects/conda/en/latest/user-guide/getting-started.html) a useful reference if you are not familiar with Conda environments.
  - Make sure Jupyter has been installed in your new Conda environment using `conda install jupyter` before interactive coding
  - For additional package installation, I suggest using Mamba in addition to `conda install`, which works well for resolving dependencies quickly
2) Submitting jobs: See [BIOS HPC Documentation - Applications](https://scholarblogs.emory.edu/rsph-hpc/74-2/)

<br />

### 2 – How to Access the RSPH HPC and ENCORE Folder

1. Contact your PI/advisor **and** Ximing (ximing.ran@emory.edu), then wait for approval from the IT department.  
2. Follow the instructions above in the ENCORE GitHub to set up your HPC environment.  

**Notice:** Please be mindful of the storage limitations within the ENCORE folder:

| User                     | Storage Limitation |
|--------------------------|--------------------|
| Undergraduate and Master | 1 TB               |
| PhD and other            | 5 TB               |

If you require additional storage, contact your PI/advisor.


<br />
<br />


# II. Share Folder for ENOCRE member (OPTIONAL)

### 1- How to map ENCORE shared folder?

- **MacOS**
  - Ensure you are connected to Emory Internet or Emory VPN.
  - Go to **Finder**, click on **Go**, and select **Connect to Server**.
  - Type the following: `smb://nasn2acts.cc.emory.edu/rsphprojects-ts`. You may be prompted to log in with your Emory NetID and password for the first time. The `ENCORE` folder will then appear under the `R` drive.
  - Navigate to `~/ENCORE/ENCORE Lab` to find shared resources.

- **Windows**
  - Ensure you are connected to Emory Internet or Emory VPN.
  - Open **File Explorer** and select **This PC**.
  - Click on **Map Network Drive**.
  - Type the following: `\\nasn2acts.cc.emory.edu\rsphprojects-ts`. You may be prompted to log in with your Emory NetID and password for the first time. The `ENCORE` folder will then appear under the `R` drive.
  - Navigate to `~/ENCORE/ENCORE Lab` to find shared resources.

**Notice**: Connection to the RSPH drive may be lost after disconnecting from Emory Internet or VPN. Adding the drive address to your list of personal servers will make it easier to reconnect.

- **Emory Device**
  -  The `ENCORE` folder will automatically appear in the `R` drive on any Emory computer after you log in with your Emory credentials.
  
Contact Weiwei (weiwei.wu@emory.edu) if you cannot find the `ENCORE` folder under the `R` drive after mapping.  

### 2- Current ENCORE folder structure
<pre>
ENCORE
└── ENCORE lab 
    ├── Events
    ├── Lab meetings
        ├── Presentation slides
        ├── Recording
    └── Resources
        ├── 00 ENCORE info
        ├── 01 Onboarding
        ├── 02 HPC instruction
        ├── 03 Templates
        └── 04 Academic writing
</pre>

<br />
<br />


  
# III. Scientific Writing and Presentations

- ***Reporting Statistical Results 2022-04-01.pdf*** by Patrick D. Kilgo and Lisa K. Elon, BIOS, RSPH  
  Located at `ENCORE/ENCORE lab/Resources/04 Academic writing` in ENCORE shared OneDrive folder  

<br />
<br />

# IV. Research Resource

## Bioinformatics
1. *[Bioinformatics workshop documentations](https://ucdavis-bioinformatics-training.github.io/)* by UCDAVIS Bioinformatics Core with the following Covered Topics:
- Bioinformatics Prerequisites (Command Line and R)  
- Single-Cell RNA-Seq Analysis  
- RNA-seq Analysis  
- Microbial Community Analysis (Amplicon)  
- Variant Analysis (Variant calling with GATK, Variant Annotation)  

2. *[Analysis of single cell RNA-seq data](https://scrnaseq-course.cog.sanger.ac.uk/website/index.html)* by Hemberg lab, Welcome Sanger Institute, UK

3. *[ENAR 2021 short course on single cell RNA-seq analysis](https://www.haowulab.org/teaching/ENAR2021/scRNAseq.html)* by Hao Wu, Emory University, and Ziyi Li, MD Anderson Cancer Center
   
## Linux

- *[Cheat sheets](https://infoplatter.wordpress.com/2014/04/06/bioinformaticians-pocket-reference/)* of AWK, C++, Python, R, Screen, UNIX, Vim, Git

## R

- *[Manual for R - An Introduction to R](https://cran.r-project.org/doc/manuals/r-release/R-intro.html)*
- *[R/Rstudio Tutorial Essential Videos](https://resources.rstudio.com/)*

## Python

- *[Python Tutorial](https://docs.python.org/3/tutorial/)*
- Coursera Python Courses: *[Programming for Everybody (Getting Started with Python)](https://www.coursera.org/learn/python)*
- Coursera Python Courses: *[Applied Data Science with Python](https://www.coursera.org/specializations/data-science-python#courses)*

## Jupyter Notebook (Recommended for Programing with Python)

- *[Introduction to Jupyter Notebooks](https://programminghistorian.org/en/lessons/jupyter-notebooks)*
- *[Jupyter Kernels](https://github.com/jupyter/jupyter/wiki/Jupyter-kernels)*

<br />
<br />



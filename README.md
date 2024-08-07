# Onboarding
Here is the train resource can be used for new member to ENOCRE lab

# High Performance and Cloud Computing Cluster

RHPC *[Toturial to RHPC](https://scholarblogs.emory.edu/rsph-hpc/)*

The RSPH HPC cluster is a system that consists of 25 compute nodes, 24 of which have 32 compute cores and 192GB of RAM each. The last node is a “large memory node” with 1.5 TB of RAM. These systems are connected together via 25GB Ethernet network, and all have access to a shared 1 Petabyte Panasas parallel file system.

In addition to the hardware, the system runs the CentOS Linux operating system (currently version 8), which is a “white-box” implementation of the Red Hat Enterprise Linux OS that purports to be 100% binary compatible with the commercial version.

Job scheduling is handled by the SLURM job scheduler, which is an application that currently runs on the majority of the Top 500 supercomputing sites in the world.

# Scientific Writing and Presentations


# Research Resource

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

- *[R/Rstudio Tutorial Essential Videos](https://resources.rstudio.com/)*

## Coursera Python Courses

- *[Programming for Everybody (Getting Started with Python)](https://www.coursera.org/learn/python)*
- *[Applied Data Science with Python](https://www.coursera.org/specializations/data-science-python#courses)*

## Jupyter Notebook (Recommended for Programing with Python)

- *[Introduction to Jupyter Notebooks](https://programminghistorian.org/en/lessons/jupyter-notebooks)*
- *[Jupyter Kernels](https://github.com/jupyter/jupyter/wiki/Jupyter-kernels)*



# Share Folder for ENOCRE member

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

- Emory Device
  -  The `ENCORE` folder will automatically appear in the `R` drive on any Emory computer after you log in with your Emory credentials.


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






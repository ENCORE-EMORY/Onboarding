# Onboarding
Here is the training resource for new ENOCRE lab members

- [I. High Performance and Cloud Computing Cluster](#i-high-performance-and-cloud-computing-cluster)
  - [1- RSPH HPC](#1--rsph-hpc)
  - [2- Access RSPH HPC and ENCORE Folder](#2--how-to-access-the-rsph-hpc-and-encore-folder)
  - [Links for RSPH HPC tutorials](01-HPC/RSPH_HPC_Instruction.md)
  - [HPC Command Cheatsheet](01-HPC/RSPH_HPC_Command_Cheatsheet.md)
- [II. Share Folder for ENOCRE member](#ii-share-folder-for-enocre-member-optional)
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
RSPH-HPC *[Toturial to RSPH-HPC](https://scholarblogs.emory.edu/rsph-hpc/)*

The RSPH HPC cluster is a system that consists of 25 compute nodes, 24 of which have 32 compute cores and 192GB of RAM each. The last node is a “large memory node” with 1.5 TB of RAM. These systems are connected together via 25GB Ethernet network, and all have access to a shared 1 Petabyte Panasas parallel file system.

In addition to the hardware, the system runs the CentOS Linux operating system (currently version 8), which is a “white-box” implementation of the Red Hat Enterprise Linux OS that purports to be 100% binary compatible with the commercial version.

Job scheduling is handled by the SLURM job scheduler, an application that currently runs on most of the Top 500 supercomputing sites in the world.


- In this `Onboarding` repository, you can find
  - [links for RSPH HPC tutorials](01-HPC/RSPH_HPC_Instruction.md) and
  - [HPC Command Cheatsheet](01-HPC/RSPH_HPC_Command_Cheatsheet.md) under the folder `01-HPC`.   

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



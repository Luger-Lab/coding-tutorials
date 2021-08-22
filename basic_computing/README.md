# Basic computing - Linux, Bash, and SLURM
## Contents
0. [Linux](#linux)
0. [Bash](#bash)
  0. Description
  0. Setting up a sandbox
  0. Navigation
  0. Basic commands
  0. Variables
  0. Loops
  0. Text editors
  0. Running scripts
  0. Connecting to clusters
0. [SLURM](#slurm)
  0. Description
  0. Sbatch scripts
  0. Queues
  0. Out and error files
  0. Starting, stopping, and monitering jobs
  0. Dependencies
  0. Best practices

## Linux
Linux is the kernel on which most high performance computing (HPC) is done. A kernel is the software that allows an operating system to control physical hardware. The Linux kernel is based on UNIX and is open source and free to use by anyone, as its creator Linus Tuvolds started the kernel under a GNU license back in the 90's. Anyone can contribute code to the kernel, as long as it passes a series of revisions and oversight. Because so many people contribute to the code it is constantly being improved.

To use Linux, you need a distribution (shortened to 'distros'). These distros are tantamount to operating systems (think Windows or MacOS). There are many to choose from: free ones like Ubuntu or Tux and enterprise ones like RedHat and CentOS. Whichever distro you choose, they will all act the same under the hood, even if the desktop appearance is different, because they all operate using the same kernel.

Although many Linux applications have easy to use graphical user interfaces (GUIs), a savvy Linux user will learn how to do everything within a terminal. A terminal is an access point into a computer that takes and returns text commands. Computing through a terminal is almost always faster than using a GUI and generally offers the user more options and customization than a GUI. The language Linux-based operating systems use in the terminal is called Bash.

## Bash
0. Description

Bash is a powerful programming language Linux-based operating systems use to perform tasks. Most of the time user-facing programs will use an easier to debug language like Python or MatLab, but you will need to use bash to navigate  

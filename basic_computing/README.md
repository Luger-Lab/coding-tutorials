# Basic computing - Linux, Bash, and SLURM
[Return to mainpage](https://luger-lab.github.io/coding-tutorials/)
## Contents
0. [Linux](#linux)
0. [Bash](#bash)
    0. Description
    0. Setting up a sandbox
    0. Basic commands
    0. Navigation
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

Bash is a powerful programming language that Linux-based operating systems use to perform tasks. Most of the time user-facing programs will use an easier language to debug like Python or MatLab, but you will need to use Bash to navigate around the terminal and launch jobs.

0. Setting up a sandbox

0. Basic commands
Commands in bash are entered directly into the command line, generally in the following format:
        <command> --<option> <input> <output>
  - The commands are actually executable scripts somewhere in your PATH (usually in your bin folder).
  - Options or "flags" modify the command in someway, like changing the behavior or explicitly defining some input/output. Most of the time, the long form of the option will have two dashes, as in:
          ls --all
  Whereas one letter abbreviations use one dash:
          ls -a
  - Inputs are generally file names or a value required by the option defined.
  - Outputs are where to put the result of the command. Some commands have these, some don't.
  - **As a rule of thumb, most programs will return a brief documentation page when ran with the flag "--help":**
          ls --help

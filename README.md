# Structural biology coding tutorials
[View as website](https://luger-lab.github.io/coding-tutorials/)
## Goal
This set of tutorials will teach [lugerlab](https://lugerlab.org/) members how to process, analyze, and present structural data. Click on a link from the list of tutorials to learn more about it. Then, click on the header for that section to take you to that tutorial.

**All tutorials will be held Tuesdays from 3-5pm, starting 9/7.**

## Tutorials
0. [Basic computing - Linux, Bash, and SLURM](#basic-computing---linux-bash-and-slurm) (9/7/21 - E225)
0. [Basic computing - How computers work](#basic-computing---how-computers-work) (9/14/21 - B432)
0. [Basic Python](#basic-python) (9/21/21 - E225)
0. [Advanced Python - Conda, packages, and scripting](#advanced-python---conda-packages-and-scripting) (10/5/21 - E225)
0. [Advanced Python - Jupyter notebooks, Matplotlib, and Plotly](#advanced-python---jupyter-notebooks-matplotlib-and-plotly) (10/12/21 - B432)
0. [Github](#github) (10/19/21 - E225)
0. [Structural analysis - Chimera and ChimeraX](#structural-analysis---chimera-and-chimerax) (10/24/21 - E225)
0. [EM analysis - RELION](#em-analysis---relion) (11/2/21 - E225)
0. [EM analysis - CryoSparc](#em-analysis---cryosparc) (11/9/21 - E225)
0. [Crystallography analysis - CCP4](#crystallography-analysis---ccp4) (11/16/21 - E225)
0. [Molecular dynamics - AMBER](#molecular-dynamics---amber) (11/30/21 - E225)
0. [Molecular dynamics - NAMD](#molecular-dynamics---namd) (12/7/21 - E225)
0. [Presentation - Making figures and talks](#presentation---making-figures-and-talks) (12/14/21 - E225)

## [Basic computing - Linux, Bash, and SLURM](https://luger-lab.github.io/coding-tutorials/basic_computing/)
Most scientific computing is conducted through operating systems based on the Linux kernel (such as CentOS or Ubuntu). These operating systems use a terminal language known as Bash. Although a lot of actual programming can be done through Bash, it is not as intuitive and easy to debug as languages like Python, so most people simply use it to navigate Linux-based systems and submit programs written in other languages. Some labs have individual workstations that allow users to run their jobs immediately; however scientific computing is trending towards cluster and cloud based data centers. These have the benefits of many more resources that are used more efficiently, they are managed by IT departments, and can be accessed from anywhere. The system most of these data centers rely on to manage which jobs are ran using which resources is called SLURM. In this module, we will discuss how and why we should use Linux, Bash, and SLURM.

## [Basic computing - How computers work](https://luger-lab.github.io/coding-tutorials/basic_computing_computers/)
In order to use computers effectively and understand why jobs fail, we will discuss how computers work generally, where normal bottlenecks are encountered, and how to avoid and fix simple ones.

## [Basic Python](https://luger-lab.github.io/coding-tutorials/basic_python/)
Python is one of the most widely used programming languages for scientific and data research. It is intuitive, easy to debug, and can handle fairly large data sets. In addition, it is open source, provides modules for most applications, and creates beautiful figures. One of its main drawbacks is that it is fairly slow when compared to other languages like MatLab.

## [Advanced Python - Conda, packages, and scripting](https://luger-lab.github.io/coding-tutorials/advanced_python_code/)
In order to share and update code, it needs to be easy to read and debug. We call this type of code 'clean code'. This tutorial will explain how to organize pieces of Python code in such a way that they will be easy for you and others to look at in the future. We will also learn how to write documentation, write and run unit and functional tests, and adhere to the PEP8 guidelines for writing Python code.

## [Advanced Python - Jupyter notebooks, Matplotlib, and Plotly](https://luger-lab.github.io/coding-tutorials/advanced_python_graphing/)
Now that we can write simple Python code, we will focus on how to use three powerful Python packages: Jupyter notebooks, Matplotlib, and Plotly. These tools will help you make quick analysis pipelines, elegant static figures, and powerful interactive figures, respectfully. You will also encounter these packages in Python-base programs like CryoSparc and AMBER, knowing how to use them will greatly increase the usefulness and troubleshooting of these other programs.

## Github
Sharing, storing, and updating software are important aspects of managing code. One of the most widespread ways to do this is through Github. Git is a version control software; a software that keeps track of changes you make to code and ensures that you are always working on up-to-date versions. Github is a repository that allows you and anyone you want to work on the same piece of code. Github stores your code and uses a management system to let users work on different pars of code and then merge it into one project, with the goal of avoiding conflicting lines that will break the code. The other main advantage of Github is that it's a unified source from which to pull other peoples' code and host your own. We will also learn how to write Github flavored Markdown (a great way to keep documentation simple).

## Structural analysis - Chimera and ChimeraX
With a firm base knowledge of computing and writing code, we will being moving onto how to use structural biology specific software. Chimera and ChimeraX are a pair of programs designed to display and analyze PDBs and electron density maps, using both GUIs and the command line. Chimera is a fully functional program that we will use to analyze and build structures as well as write and import code to customize and speed up this process. ChimeraX is the successor of Chimera, however it doesn't contain all of features of Chimera yet. We will use ChimeraX to develop publication and presentation quality figures, do interactive molecular dynamics simulations, and look at structures in virtual reality.

## EM analysis - RELION
## EM analysis - CryoSparc
## Crystallography analysis - CCP4
## Molecular dynamics - AMBER
After obtaining a structure, it is often informative to simulate it under different conditions and perturbations using molecular dynamics (MD) simulations. These simulations can help you understand how stable parts of the structure are as well as what impact specific perturbations might have. AMBER is a proprietary Python-based software which academic labs can use for a small fee. We will discuss how MD works generally, how to set up a simulation using AMBER, and how to interpret and analyze the resulting simulations. We will also discuss the main caveats of MD simulations.

## Molecular dynamics - NAMD
GROMACS is another MD simulation software. One of its main advantages is that it is open source and free to use. This tutorial will cover the same aspects as the AMBER tutorial, as well as a discussion of how the two softwares differ and when to use each.

## Presentation - Making figures and talks
This tutorial will cover tips on how to present structural data, graphs, and figures in papers and talks. We will also go into how to tailor these to a specific audience, choose colors, and keep figures focused to convey specific meaning. Making a salient talk is one of the hardest skills to master for academic researchers. Much of this presentation will be adapted from the work of [Dan Larramore](link to dans website), who's talk on this subject can be found [here](insert dans talk). We also discuss how to integrate structural data into talks, use powerful features of Microsoft PowerPoint, and create interactive slides.

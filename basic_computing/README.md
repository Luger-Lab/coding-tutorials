# Basic computing - Linux, Bash, and SLURM
[Return to mainpage](https://luger-lab.github.io/coding-tutorials/)
## Contents
0. [Linux](#linux)
0. [Bash](#bash)

    0. [Description](#description)
    0. [Setting up a sandbox](#setting-up-a-sandbox)
    0. [Basic commands](#basic-commands)
    0. [Navigation](#navigation)
    0. [Variables](#variables)
    0. [Arrays](#arrays)
    0. [Loops](#loops)
    0. [Text editors](#text-editors)
    0. [Running scripts](#running-scripts)
    0. [Connecting to remote computers](#connecting-to-remote-computers)
    0. [Advanced commands](#advanced-commands)

0. [SLURM](#slurm)

    0. [Description](#description-1)
    0. [Sbatch scripts](#sbatch-scripts)
    0. [Queues](#queues)
    0. [Out and error files](#out-and-error-files)
    0. [Starting, stopping, and monitoring jobs](#starting-stopping-and-monitoring-jobs)
    0. [Dependencies](#dependencies)
    0. [Best practices](#best-practices)

## Linux
Linux is the kernel on which most high performance computing (HPC) is done. A kernel is the software that allows an operating system to control physical hardware. The Linux kernel is based on UNIX and is open source and free to use by anyone, as its creator Linus Tuvolds started the kernel under a GNU license back in the 90's. Anyone can contribute code to the kernel, as long as it passes a series of revisions and oversight. Because so many people contribute to the code it is constantly being improved.

To use Linux, you need a distribution (shortened to 'distros'). These distros are tantamount to operating systems (think Windows or MacOS). There are many to choose from: free ones like Ubuntu or Tux and enterprise ones like RedHat and CentOS. Whichever distro you choose, they will all act the same under the hood, even if the desktop appearance is different, because they all operate using the same kernel.

Although many Linux applications have easy to use graphical user interfaces (GUIs), a savvy Linux user will learn how to do everything within a terminal. A terminal is an access point into a computer that takes and returns text commands. Computing through a terminal is almost always faster than using a GUI and generally offers the user more options and customization than a GUI. The language Linux-based operating systems use in the terminal is called Bash.

## Bash
0. ##### Description #####
  Bash is a powerful programming language that Linux-based operating systems use to perform tasks. Most of the time user-facing programs will use an easier language to debug like Python or MatLab, but you will need to use Bash to navigate around the terminal and launch jobs.

0. ##### Setting up a sandbox #####
  A sandbox is a safe environment in which to code without being able to break your computer. In our case we will be using CU's Computer Science coding space :

  https://coding.csel.io/hub/login

  - All you need to do is sign in with your CU credentials.

  - Once logged in click on the 'Default Coding Environment' widget (we'll discuss how this service actually works in a later tutorial).

  - You can bookmark this site for later use.

  In this code space, you'll see a file tree on the left side and a series of widgets on the right, we'll discuss how to use a few of these over the course of this series.

  - For now, click on the black 'Terminal' widget in the bottom row. What you've opened is a Linux terminal emulator that we will use to learn basic Bash commands.

0. ##### Basic commands #####
  Commands in bash are entered directly into the command line, generally in the following format:

  `<command> --<option> <input>`

  The command is then executed when you press enter.

  - The commands are actually executable scripts somewhere in your PATH (usually in your bin folder).
  - Options or "flags" modify the command in someway, like changing the behavior or explicitly defining some input/output. Most of the time, the long form of the option will have two dashes, as in:

    `ls --all`

    Whereas one letter abbreviations use one dash:

    `ls -a`

  - Inputs are generally file names or a value required by the option defined.
  - **As a rule of thumb, most programs will return a brief documentation page when ran with the flag "--help":**

    `ls --help`

      0. **ls** This first command, 'ls' lists the files and directories in your current folder or 'directory' as it's called in Linux. Two common flags to use with ls are '-a' and '-l'.
          ```
          jovyan@jupyter-shla9937:~$ ls
          cs_class
          ```
      - `ls -a` returns 'all' the files and directories in a give directory, including hidden ones, whose names start with a '.', we'll talk about these in a later tutorial.
```
jovyan@jupyter-shla9937:~$ ls -a
.   .bash_history            .bashrc  .conda    .config   .empty      .ipynb_checkpoints  .jupyter  .python_history
..  .bash_history-00035.tmp  .cache   .condarc  cs_class  .gitconfig  .ipython            .local    .wget-hsts
```

      - `ls -l` will return the 'long' version of a file name, including permissions, owner, size, and date created.
```
jovyan@jupyter-shla9937:~$ ls -l
total 4
drwxr-sr-x 11 jovyan users 4096 Aug 26 17:49 cs_class
```
      0. **pwd** The next thing we need to know is where we are, we can figure this out by using the command `pwd`, which prints the working directory and will give an output like:
```
jovyan@jupyter-shla9937:~$ pwd
/home/jovyan
```
      Here, each backslash represents another layer of the file tree and is know as the 'absolute path'. Try it and see where you are, as we move about later, try it again to keep oriented.

      0. **echo** If you simply want to return some text or the value of a variable, you can use `echo <word, phrase or variable>`. Try to return the phrase 'Hello world'.
```
jovyan@jupyter-shla9937:~$ echo Hello world.
Hello world.
```
      0. **touch** There are many ways to make a new file, but the most direct way is simply `touch <filename>`. This command creates an empty file that you can then do things with. Try this command using your own filename and use the extension '.txt' **remember not to `touch` a filename that already exists as it will overwrite it.**
```
jovyan@jupyter-shla9937:~$ touch dummy.txt
jovyan@jupyter-shla9937:~$
```
      0. **mkdir** Similar to touch, we can also make a directory using `mkdir <directory_name>`.
```
jovyan@jupyter-shla9937:~$ mkdir new_directory
jovyan@jupyter-shla9937:~$
```
      0. **cp** One thing you can do with this new file is 'copy' it. This is the first command we've used that requires two arguments: `cp <source_file> <destination_file>`
```
jovyan@jupyter-shla9937:~$ cp dummy.txt copy_of_dummy.txt
jovyan@jupyter-shla9937:~$
```
        - **In Bash, spaces separate arguments, therefore don't use them in filenames. If you need to specify a filename with a space in it, you will need to wrap it with quotes. Anything inside a set of quotes is treated as a single argument: `'file name with space.txt'`. Use underscores if you need to separate words: `file_name_without_spaces.txt`** Try to copy the file you made, remember to use a new name, otherwise you'll overwrite it.
        - We can also copy the directory we made by using `cp -r <directory_name> <new_name>`. The '-r' here stands for 'recursively' or 'go through and copy everything in this directory'.
      0. **rm** Now that we have two files that are copies of each other, we can delete the original. To do this we'll use the `rm` or 'remove' command, here we need only specify the file to remove:  
        - `rm <filename>`. Try it.
        - Now try to remove the copied directory we just made. Bash is smart like this and doesn't want us to remove a directory on accident. To remove an entire directory we will have to do it recursively: `rm -r <directory_name>`
      0. *Direct.* To 'direct' the output of a function into a file, we can use `<some_function> > <filename>`. **Be careful, as this function will overwrite whatever is in a file.** Try using the `echo` function to write a phrase into a .txt file.
      0. **cat** To figure out if we successful in writing to the file, we can use `cat <filename>`. It is a quick way to read all the contents of file. The caveat here is that it will read ALL the contents, no matter how long.
```
jovyan@jupyter-shla9937:~$ cat dummy.txt
This is a file called dummy.
```
      0. **head** This is where `head -n <#> <filename>` comes in handy. It will only read the first number of lines specified with `-n` (if you don't use the n flag, it will read 20 lines).
```
jovyan@jupyter-shla9937:~$ head -n 4 dummy.txt
This is a file called dummy.
line2
line3
line4
```
      0. **tail** Tail is the opposite of head; it reads the last number of lines you specify `tail -n <#> <filename>`.
      0. *Append.* If you'd like to add something to the end of file you can use the double carrot `echo <phrase> >> <filename>`
      0. *Pipe.* Finally, to put multiple functions together, use the `|`. This function takes the output from the previous function and inputs it to the next one. This is called piping. Try something like `mkdir <directory_name> | cd <directory_name> | touch <new_file | echo <phrase> > <new_file> | cat <new_file> `.

0. ##### Navigation #####
    0. **cd** To navigate from directory to directory, we can use `cd` or 'change directory'.
        - We can move into a deeper directory by `cd <directory name>`
        - Up a directory with `cd ..` ('..' represents the parent directory)
        - The same directory `cd .` ('.' represents your current directory, we'll use it later)
        - An adjacent directory by specifying a 'relative path' `cd ../jon`
        - A specific directory by specifying the absolute path `cd /home/jon`
        - Your home directory with either `cd ~` or simply `cd`
    0. **mv** Similar to, and much faster than the `cp` function, we can use `mv <source_file> <destination_file>` to move a file from one location to another. Because you are not actually copying and remove the file, simply changing its location information, this function is often instant.
    Another use of this function is to rename files (because that is essentially what you are doing). To do this simply `mv <old_name> <new_name>`, you can also move and rename entire directories.
    0. *Tab filling.* One of the biggest timesavers in coding is using the tab key to autofill a function in your path or the name of a file/directory after you have typed the first few characters.
    Tabbing twice will give you a list of all files or directories in your current directory.
    0. *Home directory.* You home directory is usually where you will start a terminal session and contains all of the personal files necessary for you to work, including hidden files and programs. Usually your home directory is stored on a smaller, faster drive and not meant for the storage of large datasets. You can get to your home directory by using:
        - the absolute path `/home/shawn`
        - relative path eg. `../../shawn`
        - the tilde `cd ~`
        - an empty cd `cd `
    0. *Permissions.* All files and folders on a computer have a set of permissions, which you can view using `ls -l`. There are three levels of permissions: user, group, and other. And three types of permission in each level: read(r), write(w) and execute(x). These are denoted by sets of 3 letters per level.
```
      -rwx------ 1 shla9937 lugerlab 0 Sep  3 16:48 user.txt
      -rwxrwxr-- 1 shla9937 lugerlab 0 Sep  3 16:48 group.txt
      -rwxrwxrwx 1 shla9937 lugerlab 0 Sep  3 16:48 other.txt
```


0. ##### Variables #####
Variables can be defined in bash using the syntax: `<varibale_name>=<variable_value>`.
You can then call the variable using `$<variable_name>`.
And clear its value with `unset <variable_name>`.

0. ##### Arrays #####

0. ##### Loops #####
    0. *For Loops* Now that you can use variables you can
    0. *if statements*
    0. While loops

0. ##### Text editors #####
    0. Nano
    0. Vim
    0. Gedit
    0. Atom

0. ##### Running scripts #####

0. ##### Connecting to remote computers #####
    0. ssh
    0. Putty
    0. Forwarding
    0. **exit**

0. ##### Advanced commands #####
    0. **top**
    0. **crtl+c**
    0. **history**
    0. **clear**
    0. **\***
    0. **rsync**
    0. **grep**
    0. **screen**
    0. **chmod**
    0. **sudo**

## Slurm
  0. ##### Description #####
  0. ##### Sbatch scripts #####
  0. ##### Queues #####
  0. ##### Out and error files #####
  0. ##### Starting, stopping, and monitoring jobs #####
  0. ##### Dependencies #####
  0. ##### Best practices #####

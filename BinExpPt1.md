# Binary Exploitation: Part1
  > Binary Exploitation involves manipulating executable files to behave unlike how they were intended. This exploitation could be using the files permissions to access other inaccessible files or to gain secure information in the file. In CTF competitions, sometimes source code is provided with the executable, but other times only the binary is provided. This section serves as an introduction to the essential Linux commands and concepts needed to exploit a binary.  

## File 
  When first presented with a binary, it is helpful to run the **file** command before doing anything else with the executable because the output gives you a starting point on how to manipulate the file. 
  <img src = "https://github.com/UDCTF/UDCTF.github.io/blob/master/LittleTommy.PNG" width = 1500 height = 75>
  This command can be used when files are missing their extension. The "dynamically-linked" portion of the output lets the user know that commands like **ltrace** will work on this file. **ltrace** does not work on "statically-linked" files. 
## Strings 
  The **strings** commmand is a good second step when exploiting a binary because it provides the user with all of the human-readable pieces of text that are in the file. This command is part of the binutils package, which may not be installed on your computer, so try running **sudo apt-get install binutils** in the command line, which will give you access to a few important commands that can be used when manipulating binary files. For practice, install this binary using **wget http://pwnable.kr/bin/flag**. Using the file commmand we see 
## ltrace 


## Symbolic Links 

## Absolute vs. Relative Paths 

## Exercises 

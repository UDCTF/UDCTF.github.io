# Binary Exploitation: Part1
  > Binary Exploitation involves manipulating executable files to behave unlike how they were intended. This exploitation could be using the files permissions to access other inaccessible files or to gain secure information in the file. In CTF competitions, sometimes source code is provided with the executable, but other times only the binary is provided. This section serves as an introduction to the essential Linux commands and concepts needed to exploit a binary.  

## File 
  When first presented with a binary, it is helpful to run the **file** command before doing anything else with the executable because the output gives you a starting point on how to manipulate the file. 
  <img src = "https://github.com/UDCTF/UDCTF.github.io/blob/master/LittleTommy.PNG" width = 1500 height = 75>
  This command can be used when files are missing their extension. The "dynamically-linked" portion of the output lets the user know that commands like **ltrace** will work on this file. **ltrace** does not work on "statically-linked" files. 
## Strings 
  The **strings** commmand is a good second step when exploiting a binary because it provides the user with all of the human-readable pieces of text that are in the file. This command is part of the binutils package, which may not be installed on your computer, so try running **sudo apt-get install binutils** in the command line, which will give you access to a few important commands that can be used when manipulating binary files. For example, install this binary using **wget http://pwnable.kr/bin/flag**. Using the file commmand we see that this is a 64-bit ELF file, and when we run it we get an obscure message.
<img src="https://github.com/UDCTF/UDCTF.github.io/blob/master/pwnable_flag.PNG"> 
Before using any advanced binary exploitation techniques, we should try the **strings** command on the executable. When the command is ran, the command prompt overflows with text where there is a only a few characters per line. Since nothing meaningful can be shown in a few characters, we use the min-length option for the **strings** command (details for the **strings** command can be found using **man strings** in the command prompt). Running **strings -n 20** in the command prompt gives 
<img src="https://github.com/UDCTF/UDCTF.github.io/blob/master/UPX%20Packer.PNG"> 
Towards the bottom of the output, we can see that the file is packed with the UPX packer. Using Google, we can look up the UPX Packer, and install the necessary unpacker. Although the rest of the challenge requires assembly language, we can see that the strings command is very useful in finding information about executables. 
## ltrace 
**ltrace** is a command that displays dynamic system calls and their parameters while the program is running. These dynamic system calls may include string comparisons. For example, **ssh leviathan1@leviathan.labs.overthewire.org -p2223** with password rioGegei8m.  

## Symbolic Links 

## Absolute vs. Relative Paths 

## Exercises 

# MY Linux Notes

 - let's read linux pocket guide book and take notes

 - how a program works on linux is :
    - The program name refers to a program name somewhere on disk that the shell will locate and run.

 - The code down below is couns lines in a file and prints it
```
    wc -l LPG.md
```

 - commands can run several programs at a time, either in sequence (one prog after another) or in a "pipleline" with the output of onecommand becomeing input of the next.
 - the shell has a programming language build so it van rn : run tihs program, write it out to this file, if any error occur, send email the  results

## the calendar
 - cal command is a good way to get calendar, Usage : cal day month year
```
    cal 3 9 2023
```

 - count the number of visible items at home
```
    ls $HOME | wc -l
```

 - see how much is used on a partition of your hard disk

```
    df -h /
```

 - logged in time:
```
    las -1 $USER
```

~~~
    ip addr show eth0
~~~

 - there we have a good friend on shell : echo.
    - it prints the content of variables given to it or directly the data has given


 - There is a abilty to write a huge comment with the '\' flag that means the comment is still continueing. u can go alt enter to next line.


 - there is a man like command; info. usage is like info ls


 - /usr/share/doc : this file contains documents for many programs


## linux help sites :
- linuxquestions.org , unix.stach , exchange.com , linuxhelp.net


## Shells :
 - Bourne shell
 - Korn shell
 - C shell

 - Note : the window (terminal console) is not shell it is just a graphical program.

## File SYS:
 - partial (?)
 - in linux all files and dirst descend from the root. This is unlike windows or Dos
    - for ordinary users the hoe is /home but for root it is /root


    - cd ~user_name goes to home of the user

## System Directories
 - /usr/local/share     /emacs
 - scope     | category| application

 - Categories for Programs:
 - bin : programs (usually binary files)
 - sbin : programs (usually binary files) intended to be run by superuser
 - lib : libraries of code used by programs

 - Categories for documentation
 - doc
 - info
 - man
 - share : program-specific files, such as exmaples and istallation

 - Categoris for configuration : 
 - etc : config files for the system 
 - init.d : configuration files for booting linux
 - rc.d : configuration files fot booting linux; alsa rc1.d, rc2.d

 - Categories for programming : 
 - include : Header files
 - src : sruce code

 - Categories for hardware : 
 - dev : Device files for interfacing with disks and other hardware
 - media : Mount Points : dir that provides accest to disks
 - mnt : Mount Points : dir that provides accest to disks

 - Categories for runtime files :
 - var : files specific to this computer, ceated and updated as the computer runs
 - lock : lock files are created by programs to say "I am running" existance of lock fike may prevent another program or another instance of the same program.
 - log : it track system events, error, earning and informational messages
 - run : PID files, which contain ID's of running processes
 - tmp : temporary storage for programs or people to use 
 - proc : operateing system state ... we will se...

# page 30





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

## Operating System Dİrectories
 lowest-leve part of linux operating system:
 - /boot
   - Files for booting the system. This is where kernel lives, typically named /boot(vmlinuz od smilar
 - /lost+found
   - Damaged files that where rescued by a disk recovery tool
 - /proc
   - Describes currently running process
 the files in proc provide views into the running kernel. they are zero sized, read only, dated now.

## File Protections
  Who has permission?
  every file and directory has an owner who has permission to do anythink with it. it is who created it. but ownership can be changed by the superuser.
  Additionally, a predefined group of users may have permission to access a file.
  Finally can be opened to all users with login accounts on system. you'll also see this set of users called the world or simply other.
 File owners, groups and the world may each have permission to read, write(modify), execute(run) particular files. Permissions also extend to directories, which users can read (access files within the directory), write(create and delete files within directory), and execute(enter the directory with cd).

  to see the ownership and permissions of a file use -l flag for directory use -ld flag

  position : Meaning
     1     :   - = file, d = dir, l = sybolic link, p = named pipe, c = character device, b = block device
     2-4 : Read, write, exec for file's owner
     5-7 : Read, write, exec for file's group
     8-10 : Read, write, exec for file's users

## Shell Features
  to see who's logged into the computer, use : who
  to learnd running bash program use : echo $SHELL
  when you run a command it might be a Linux program or built-in command to learn use ; type command.
    type cd

## Selevted Features of tge bash Shell

### Wildcards
  they are a shorthand for sets of files with similar names.
  a* means all files whose names begin with 'a'
  
  ls never knows you used a wildcard : it sees only the final list of filenames after the shell expands the wildcard.
  wildcards are handled compleately by the shell befor the associated program even runs.

### Dot Files
  filenames with a leading period. they are called also "hidden files".
  ls will omit the file from directory listings, unless you provide the -a option.

  wildcards never match two characters: a leading presiod, and the directory slash (/).

 Wildcard : Meaning
 *       : Zero or more consecutive characters
 ?       : Any single character (bir karakterin yerine gelebilecek olanları doldurur)
 [set]   : any single character in the given as set, mostly usage is like [aeiou] or [a-z] for all letters
 [ ^set] : any single character not in given set, such as [ ^0-9] to mean any nondigit
 [!set]  : Same as [ ^set]

### Brace expansion
 {x,yy,zzz}
 uses this 3 list element and add's it to the word
 sand{x,yy,zzz} means : sandx sandyy sandyyy

### Shell Variables
 MYVAR=3
 echo $MYVAR

 Some standart defined variables

|--|--|
| DISPLAY |X window manager name|
| HOME | home directory|
| LOGNAME | your login name|
| MAIL | your incomin mailbox|
| OLDPWD | shell's previous directory|
| PATH | shell search path|
| PWD | shell's current dir|
| SHELL | the path to ypur shell|
| TERM | the type of your terminal|
| USER | login name|

To make a variable avaliable to other programs your shell invokes use the export command:
 export MYVAR
 export MYVAR=3

To list a shell's encironment variables run : printenv


### Search Path
 program are scattered to /bin and /usr/bin dirs. when you run a command the var PATH tells the shell ehere to look.
 when you run who the shell looks at the $PATH var's directories.

 To add directories to your shell's search path temporary, modifiy the PATH var.
```
 PATH=$PATH:/usr/emrebin
```
this affects the current shell. To make it permant modify the PATH variable in your startup file ~.bash_profile

### Aliases
 The aliases are shortcut definitions.
 alias ll='ls -lG'

# page 39







# Shell Notes : 
 - ls -l : uzun liste biçminde dosya hakkında bilgi verir : yetkiler, kullanıcı, tarih vb.

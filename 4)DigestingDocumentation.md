# Digesting Documentation

## Learining from documentation
The typical need you'll have for documentation is just to figure out how to use all these dang programs, and a specific case of that is figuring out what arguments to specify on the command line. This module will mostly dig into that concept, as a proxy for figuring out how to use the programs in general. Through the rest of the module, you'll go through various ways of asking the environment for help for the programs, but first, we'll dig into the concept of reading documentation.

The correct usage of programs depends, in a large part, on the proper specification of arguments to them. Recall the -a of ls -a in the hidden files challenge of the Basic Commands module: that -a was an argument that told ls to list out hidden files as well as non-hidden files. Because we wanted to list out hidden files, invoking ls with the -a argument was the correct way to use it in our scenario.

The program for this challenge is /challenge/challenge, and you'll need to invoke it properly in order for it to give you the flag. Let's pretend that this is its documentation:

Welcome to the documentation for /challenge/challenge! To properly run this program, you will need to pass it the argument of --giveflag. Good luck!

Given that knowledge, go get the flag!

### Solve
**Flag:** `pwn.college{w5vKugKIi5qwv1ukvsQxlbcoBYr.QX0ITO0wyNwIzNzEzW}`

To get to the flag we should pass an argument to the command line.

```bash
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
pwn.college{w5vKugKIi5qwv1ukvsQxlbcoBYr.QX0ITO0wyNwIzNzEzW}
```

### New Learnings
Reading documentation.

### References 
No reference.

## Learning complex usage
While using most commands is straightforward, the usage of some commands can get quite complex. For example, the arguments to commands like sed and awk, which we're definitely not getting into right now, are entire programs in an esoteric programming language! Somewhere on the spectrum between cd and awk are commands that take arguments to their arguments...

This sounds crazy, but you've already encountered this with the find level in Basic Commands. find has a -name argument, and the -name argument itself takes an argument specifying the name to search for. Many other commands are analogous.

Here is this level's documentation for /challenge/challenge:

Welcome to the documentation for /challenge/challenge! This program allows you to print arbitrary files to the terminal, when given the --printfile argument. The argument to the --printfile argument is the path of the flag to read. For example, /challenge/challenge --printfile /challenge/DESCRIPTION.md will print out the description of the level!

Given that documentation, go get the flag!

### Solve
**Flag:** `pwn.college{MNZoG0NsetrGHLHbPCw8CKwF_eN.QX1ITO0wyNwIzNzEzW}`

To get to the flag i used --printfile/flag argument as the challenge description said and flag is the general file where u can find the flag.

```bash
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
pwn.college{MNZoG0NsetrGHLHbPCw8CKwF_eN.QX1ITO0wyNwIzNzEzW}
```

### New Learnings
--printfile argument is also used to printfile.
### References 
No reference.

## Reading Manuals
This level introduces the man command. man is short for manual, and will display (if available) the manual of the command you pass as an argument. For example, let's say we wanted to learn about the yes command (yes, this is a real command):

hacker@dojo:~$ man yes
This will display the manual page for yes, which will look something like this:

YES(1)                           User Commands                          YES(1)

NAME
       yes - output a string repeatedly until killed

SYNOPSIS
       yes [STRING]...
       yes OPTION

DESCRIPTION
       Repeatedly output a line with all specified STRING(s), or 'y'.

       --help display this help and exit

       --version
              output version information and exit

AUTHOR
       Written by David MacKenzie.

REPORTING BUGS
       GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
       Report any translation bugs to <https://translationproject.org/team/>

COPYRIGHT
       Copyright  ©  2020  Free Software Foundation, Inc.  License GPLv3+: GNU
       GPL version 3 or later <https://gnu.org/licenses/gpl.html>.
       This is free software: you are free  to  change  and  redistribute  it.
       There is NO WARRANTY, to the extent permitted by law.

SEE ALSO
       Full documentation <https://www.gnu.org/software/coreutils/yes>
       or available locally via: info '(coreutils) yes invocation'

GNU coreutils 8.32               February 2022                          YES(1)
The important sections are:

NAME(1)                           CATEGORY                          NAME(1)

NAME
	This gives the name (and short description) of the command or
	concept discussed by the page.

SYNOPSIS
	This gives a short usage synopsis. These synopses have a standard
	format. Typically, each line is a different valid invocation of the
	command, and the lines can be read as:

	COMMAND [OPTIONAL_ARGUMENT] SINGLE_MANDATORY_ARGUMENT
	COMMAND [OPTIONAL_ARGUMENT] MULTIPLE_ARGUMENTS...

DESCRIPTION
	Details of the command or concept, with detailed descriptions
	of the various options.

SEE ALSO
	Other man pages or online resources that might be useful.

COLLECTION                        DATE                          NAME(1)
You can scroll around the manpage with your arrow keys and PgUp/PgDn. When you're done reading the manpage, you can hit q to quit.

Manpages are stored in a centralized database. If you're curious, this database lives in the /usr/share/man directory, but you never need to interact with it directly: you just query it using the man command. The arguments to the man command aren't file paths, but just the names of the entries themselves (e.g., you run man yes to look up the yes manpage, rather than man /usr/bin/yes, which would be the actual path to the yes program but would result in man displaying garbage).

The challenge in this level has a secret option that, when you use it, will cause the challenge to print the flag. You must learn this option through the man page for challenge!

### Solve
**Flag:** `pwn.college{4h2ROFIGZ0jKbof9_PnyGJwSHed.QX0EDO0wyNwIzNzEzW}`

To solve this challenge we should open manual page for challenge.After opening manual we will find that, if we use --hjbofn 420 argument we will get the flag.

```bash
hacker@man~reading-manuals:~$ man challenge 
hacker@man~reading-manuals:~$ /challenge/challenge --hjbofn 420
pwn.college{4h2ROFIGZ0jKbof9_PnyGJwSHed.QX0EDO0wyNwIzNzEzW}
```

### New Learnings
man command is used to open manual and can be opened without giving the absolute path.

### References 
No reference.

## Searching Manuals
You can scroll man pages with the arrow keys (and PgUp/PgDn) and search with /. After searching, you can hit n to go to the next result and N to go to the previous result. Instead of /, you can use ? to search backwards!

Find the option that will give you the flag by reading the challenge man page.

### Solve
**Flag:** `pwn.college{4If4SaWf8oZZvGsfDckz8s_tFgp.QX1EDO0wyNwIzNzEzW}`

To get to the flag I should open man page of challenge.In man page there were many arguments, to find the right one I used /flag in man page to find the correct argument to display flag.

```bash
hacker@man~searching-manuals:~$ man challenge 
hacker@man~searching-manuals:~$ /challenge/challenge --ne
pwn.college{4If4SaWf8oZZvGsfDckz8s_tFgp.QX1EDO0wyNwIzNzEzW}
```

### New Learnings
/ is used to search in man page.

### References 
No reference.

## Searching for manuals
This level is tricky: it hides the manpage for the challenge by randomizing its name. Luckily, all of the manpages are gathered in a searchable database, so you'll be able to search the man page database to find the hidden challenge man page! To figure out how to search for the right manpage, read the man page manpage by doing: man man!

HINT 1: man man teaches you advanced usage of the man command itself, and you must use this knowledge to figure out how to search for the hidden manpage that will tell you how to use /challenge/challenge

HINT 2: though the manpage is randomly named, you still actually use /challenge/challenge to get the flag!

### Solve
**Flag:** `pwn.college{cEitgOpSauRNqvysoNgLevb3__Y.QX2EDO0wyNwIzNzEzW}`

To find the hidden man page, i opened man page of man and used /search to find the correct argument, I came across -k argument which let me search the manual by the keywords in the description of the manual.I opend the correct man page and went through the description and found flag.

```bash
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man -k challenge
citgpauqvy (1)       - print the flag!
hacker@man~searching-for-manuals:~$ man citgpauqvy
hacker@man~searching-for-manuals:~$ /challenge/challenge --citgpa 320
Correct usage! Your flag: pwn.college{cEitgOpSauRNqvysoNgLevb3__Y.QX2EDO0wyNwIzNzEzW}
```

### New Learnings
-k argument can be used to search the man pages by taking the keyword from the user which is in the description of the man page we search for.

### References 
No reference.

## Helpful Programs
Add challenge description here

### Solve
**Flag:** `pwn.college{QBUBPsIDU3GFcCmewQHtKls0B-K.QX3IDO0wyNwIzNzEzW}`
We should first use --help argument to reach the flag.After using --help argument it gave an argument to print the value which is requried to get the flag and an argument to show the flag which requires the value.I used the argument to show the flag followed by the value to get the flag.

```bash
hacker@man~helpful-programs:~$ /challenge/challenge --help
usage: a challenge to make you ask for help [-h] [--fortune]
                                            [-v]
                                            [-g GIVE_THE_FLAG]
                                            [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct
                        value
  -p, --print-value     print the value that will cause the
                        -g option to give you the flag
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 303
hacker@man~helpful-programs:~$ /challenge/challenge -g 303
Correct usage! Your flag: pwn.college{QBUBPsIDU3GFcCmewQHtKls0B-K.QX3IDO0wyNwIzNzEzW} 
```

### New Learnings
--help command is used when man page is not there.

### References 
No reference.

## Help for Builtins
Some commands, rather than being programs with man pages and help options, are built into the shell itself. These are called builtins. Builtins are invoked just like commands, but the shell handles them internally instead of launching other programs. You can get a list of shell builtins by running the builtin help, as so:

hacker@dojo:~$ help
You can get help on a specific one by passing it to the help builtin. Let's look at a builtin that we've already used earlier, cd!

hacker@dojo:~$ help cd
cd: cd [-L|[-P [-e]] [-@]] [dir]
    Change the shell working directory.
    
    Change the current directory to DIR.  The default DIR is the value of the
    HOME shell variable.
...
Some good information! In this challenge, we'll practice using help to look up help for builtins. This challenge's challenge command is a shell builtin, rather than a program. Like before, you need to lookup its help to figure out the secret value to pass to it!

### Solve
**Flag:** `pwn.college{gl6HV-GXn5dGDjUo7M3llNJcscM.QX0ETO0wyNwIzNzEzW}`

I used help command followed by challenge as said in the problem statement and found out that we should use --secret argument followed by a value given after using help command to get the flag.

```bash
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "gl6HV-GX".
hacker@man~help-for-builtins:~$ challenge --secret gl6HV-GX
Correct! Here is your flag!
pwn.college{gl6HV-GXn5dGDjUo7M3llNJcscM.QX0ETO0wyNwIzNzEzW}
```

### New Learnings
help is a builtin command.

### References 
No reference.

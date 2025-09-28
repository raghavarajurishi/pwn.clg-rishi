# Pondering Paths

## The Root
Alright, so the filesystem starts at /. Under that, there are a whole mess of other directories, configuration files, programs, and, most importantly, flags. In this level, we've added a program right in /, called pwn, that will give you the flag. All you need to do for this level is to invoke this program!

You can invoke a program by providing its path on the command line. In this case, you'll be giving the exact path, starting from /, so the path would be /pwn. This style of path, one that starts with the root directory, is referred to as an "absolute path".

Start the challenge, launch a terminal, invoke the pwn program using its absolute path, and Capture that Flag! Good luck!

### Solve
**Flag:** `pwn.college{oanDQI7idEwz_WmPvmSJEX_kU9Z.QX4cTO0wyNwIzNzEzW}`

To solve this challenge we should open pwn.I should enter the path to pwn.

```bash
hacker@paths~the-root:~$ /pwn
pwn.college{oanDQI7idEwz_WmPvmSJEX_kU9Z.QX4cTO0wyNwIzNzEzW}
```

### New Learnings
If we use "/" its an absolute path.

### References 
No references 

## Program and absolute paths
Let's explore a slightly more complicated path! Except for in the previous level, challenges in pwn.college are in the challenge directory and the challenge directory is, in turn, right in the root directory (/). The path to the challenge directory is, thus, /challenge. The name of the challenge program in this level is run, and it lives in the /challenge directory. Thus, the path to the run challenge program is /challenge/run.

This challenge again requires you to execute it by invoking its absolute path. You'll want to execute the run file that is in the challenge directory that is, in turn, in the / directory. If you invoke the challenge correctly, it will give you the flag. Good luck!

### Solve
**Flag:** `pwn.college{oLxgI9K6GxKgpkbh9h-DR18Ctmq.QX1QTN0wyNwIzNzEzW}`

The flag is in the run file which is in challenge directory which is in root(/)directory.We should open run file to solve this challenge.

```bash 
hacker@paths~program-and-absolute-paths:~$ /challenge/run
pwn.college{oLxgI9K6GxKgpkbh9h-DR18Ctmq.QX1QTN0wyNwIzNzEzW}
```

### New Learnings
Nothing new

### References 
No references 

## Position thy self
The Linux filesystem has tons of directories with tons of files. You can navigate around directories by using the cd (change directory) command and passing a path to it as an argument, as so:

hacker@dojo:~$ cd /some/new/directory
hacker@dojo:/some/new/directory$
This affects the "current working directory" of your process (in this case, the bash shell). Each process has a directory in which it's currently hanging out. The reasons for this will become clear later in the module.

As an aside, now you can see what the ~ was in the prompt! It shows the current path that your shell is located at.

This challenge will require you to execute the /challenge/run program from a specific path (which it will tell you). You'll need to cd to that directory before rerunning the challenge program. Good luck!

### Solve
**Flag:** `pwn.college{8woM1Pbj6nqMexS5OPDEdxlLWDw.QX2QTN0wyNwIzNzEzW}`

To know the flag location, i gave a path, it showed correct path.I opened that directory and gave absolute path to run file which gave me the flag.

```bash
hacker@paths~position-thy-self:~$ /challenge/run
hacker@paths~position-thy-self:~$ cd /tmp
hacker@paths~position-thy-self:/tmp$ /challenge/run
pwn.college{8woM1Pbj6nqMexS5OPDEdxlLWDw.QX2QTN0wyNwIzNzEzW}
```

### New Learnings
cd command is used to open that directory.

### References 
No references 

## Position elsewhere
The Linux filesystem has tons of directories with tons of files. You can navigate around directories by using the cd (change directory) command and passing a path to it as an argument, as so:

hacker@dojo:~$ cd /some/new/directory
hacker@dojo:/some/new/directory$
This affects the "current working directory" of your process (in this case, the bash shell). Each process has a directory in which it's currently hanging out. The reasons for this will become clear later in the module.

As an aside, now you can see what the ~ was in the prompt! It shows the current path that your shell is located at.

This challenge will require you to execute the /challenge/run program from a specific path (which it will tell you). You'll need to cd to that directory before rerunning the challenge program. Good luck!

### Solve
**Flag:** `pwn.college{olTDuTneT5lo1NdqJAG4Jji-lBc.QX3QTN0wyNwIzNzEzW}`

I gave a path so that it would give me the correct path to the flag file.I used cd command to open the correct directory by giving it the absolute path and opened the file which has flag.

```hacker@paths~position-elsewhere:~$ /challenge/run```
```hacker@paths~position-elsewhere:~$ cd /usr/share/zoneinfo/posix/Asia```
```hacker@paths~position-elsewhere:/usr/share/zoneinfo/posix/Asia$ /challenge/run```
```pwn.college{olTDuTneT5lo1NdqJAG4Jji-lBc.QX3QTN0wyNwIzNzEzW}```

### New Learnings
Nothing new

### References 
No references 

## Position yet elsewhere
The Linux filesystem has tons of directories with tons of files. You can navigate around directories by using the cd (change directory) command and passing a path to it as an argument, as so:

hacker@dojo:~$ cd /some/new/directory
hacker@dojo:/some/new/directory$
This affects the "current working directory" of your process (in this case, the bash shell). Each process has a directory in which it's currently hanging out. The reasons for this will become clear later in the module.

As an aside, now you can see what the ~ was in the prompt! It shows the current path that your shell is located at.

This challenge will require you to execute the /challenge/run program from a specific path (which it will tell you). You'll need to cd to that directory before rerunning the challenge program. Good luck!

### Solve
**Flag:** `pwn.college{syDT4OCiajWGS-8WEgvvmi-D_nE.QX4QTN0wyNwIzNzEzW}`

I gave a path so that it would give me the correct path to the flag file.I used cd command to open the correct directory by giving it the absolute path and opened the file which has flag.

```hacker@paths~position-yet-elsewhere:~$ /challenge/run```
```hacker@paths~position-yet-elsewhere:~$ cd /sys```
```hacker@paths~position-yet-elsewhere:/sys$ /challenge/run```
```pwn.college{syDT4OCiajWGS-8WEgvvmi-D_nE.QX4QTN0wyNwIzNzEzW} ```

### New Learnings
You can open any directory no matter where u are by giving cd command and giving it absoluter path.

### References 
No references 

## implicit relative paths,from /
Now you're familiar with the concept of referring to absolute paths and changing directories. If you put in absolute paths everywhere, then it really doesn't matter what directory you are in, as you likely found out in the previous three challenges.

However, the current working directory does matter for relative paths.

A relative path is any path that does not start at root (i.e., it does not start with /).
A relative path is interpreted relative to your current working directory (cwd).
Your cwd is the directory that your prompt is currently located at.
This means how you specify a particular file, depends on where the terminal prompt is located.

Imagine we want to access some file located at /tmp/a/b/my_file.

If my cwd is /, then a relative path to the file is tmp/a/b/my_file.
If my cwd is /tmp, then a relative path to the file is a/b/my_file.
If my cwd is /tmp/a/b/c, then a relative path to the file is ../my_file. The .. refers to the parent directory.
Let's try it here! You'll need to run /challenge/run using a relative path while having a current working directory of /. For this level, I'll give you a hint. Your relative path starts with the letter c 😊

### Solve
**Flag:** `pwn.college{gLLlngnWpwZCXS0is_hqaFGwn-0.QX5QTN0wyNwIzNzEzW}`

As given in the problem statement the flag is in root directory.After opening root directory u should enter relative path to the run file.

```hacker@paths~implicit-relative-paths-from-:~$ cd /```
```hacker@paths~implicit-relative-paths-from-:/$ challenge/run```
```pwn.college{gLLlngnWpwZCXS0is_hqaFGwn-0.QX5QTN0wyNwIzNzEzW}```

### New Learnings
A relative path does not start with "/".Current working directory is the directory where my prompt is currently at.

### References 
No references 

## explicit relative paths,from /
Previously, your relative path was "naked": it directly specified the directory to descend into from the current directory. In this level, we're going to explore more explicit relative paths.

In most operating systems, including Linux, every directory has two implicit entries that you can reference in paths: . and ... The first, ., refers right to the same directory, so the following absolute paths are all identical to each other:

/challenge
/challenge/.
/challenge/./././././././././
/./././challenge/././
The following relative paths are also all identical to each other:

challenge
./challenge
./././challenge
challenge/.
Of course, if your current working directory is /, the above relative paths are equivalent to the above absolute paths.

This challenge will get you using . in your relative paths. Get ready!

### Solve
**Flag:** `pwn.college{gWPwLXiiaQ7S7ULSYXj6fmJ4yB4.QXwUTN0wyNwIzNzEzW}`

As given in the challenge the flag is in root directory.After opening root directory u should use . as it refers right to the same directory.

```cd /```
```./challenge/run```
```pwn.college{gWPwLXiiaQ7S7ULSYXj6fmJ4yB4.QXwUTN0wyNwIzNzEzW}```

### New Learnings
. refers to the same directory no matter how many . u use its going to be same.

### References 
No references 

## Implicit relative path
In this level, we'll practice referring to paths using . a bit more. This challenge will need you to run it from the /challenge directory. Here, things get slightly tricky.

Linux explicitly avoids automatically looking in the current directory when you provide a "naked" path. Consider the following:

hacker@dojo:~$ cd /challenge
hacker@dojo:/challenge$ run
This will not invoke /challenge/run. This is actually a safety measure: if Linux searched the current directory for programs every time you entered a naked path, you could accidentally execute programs in your current directory that happened to have the same names as core system utilities! As a result, the above commands will yield the following error:

bash: run: command not found
We'll explore the mechanisms behind this concept later, but in this challenge, we'll learn how to explicitly use relative paths to launch run in this scenario. The way to do this is to tell Linux that you explicitly want to execute a program in the current directory, using . like in the previous levels. Give it a try now!

### Solve
**Flag:** `pwn.college{8e5_6U8IxBqw60tBGk0QsjAcBH8.QXxUTN0wyNwIzNzEzW}`

The flag is located in the /challenge directory.After opening that directoy we should use . to run the flag file as the linux system might accidentally execute programs in your current directiry which have the same names as core system utilites.

```cd /challenge/```
```./run```
```pwn.college{8e5_6U8IxBqw60tBGk0QsjAcBH8.QXxUTN0wyNwIzNzEzW}```

### New Learnings
. can also be used to safely open/run files.

### References 
No references 

## home sweet home

Every user has a home directory, typically under /home in the filesystem. In the dojo, you are the hacker user, and your home directory is /home/hacker. The home directory is typically where users store most of their personal files. As you make your way through pwn.college, this is where you'll store most of your solutions.

Typically, your shell session will start with your home directory as your current working directory. Consider the initial prompt:

hacker@dojo:~$
The ~ in this prompt is the current working directory, with ~ being shorthand for /home/hacker. Bash provides and uses this shorthand because, again, most of your time will be spent in your home directory. Thus, whenever bash sees ~ provided as the start of an argument in a way consistent with a path, it will expand it to your home directory. Consider:

hacker@dojo:~$ echo LOOK: ~
LOOK: /home/hacker
hacker@dojo:~$ cd /
hacker@dojo:/$ cd ~
hacker@dojo:~$ cd ~/asdf
hacker@dojo:~/asdf$ cd ~/asdf
hacker@dojo:~/asdf$ cd ~
hacker@dojo:~$ cd /home/hacker/asdf
hacker@dojo:~/asdf$
Note that the expansion of ~ is an absolute path, and only the leading ~ is expanded. This means, for example, that ~/~ will be expanded to /home/hacker/~ rather than /home/hacker/home/hacker.

Fun fact: cd will use your home directory as the default destination:

hacker@dojo:~$ cd /tmp
hacker@dojo:/tmp$ cd
hacker@dojo:~$
Now it's your turn to play! In this challenge, /challenge/run will write a copy of the flag to any file you specify as an argument on the commandline, with these constraints:

Your argument must be an absolute path.
The path must be inside your home directory.
Before expansion, your argument must be three characters or less.
Again, you must specify your path as an argument to /challenge/run as so:

hacker@dojo:~$ /challenge/run YOUR_PATH_HERE

### Solve
**Flag:** `pwn.college{M8Xt4ArNiAV596Rkuaa8jJd6zz9.QXzMDO0wyNwIzNzEzW}`

To solve this, we should write a copy of the flag to a specific file and run it.

```hacker@paths~home-sweet-home:~$ /challenge/run ~/r ```
```pwn.college{M8Xt4ArNiAV596Rkuaa8jJd6zz9.QXzMDO0wyNwIzNzEzW}```

### New Learnings
cd will use home directory as default destination.
### References 

No references 

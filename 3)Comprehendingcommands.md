# Comprehending Commands

## cat: not the pet, but the command!
One of the most critical Linux commands is cat. cat is most often used for reading out files, like so:

hacker@dojo:~$ cat /challenge/DESCRIPTION.md
One of the most critical Linux commands is `cat`.
`cat` is most often used for reading out files, like so:
cat will concatenate (hence the name) multiple files if provided multiple arguments. For example:

hacker@dojo:~$ cat myfile
This is my file!
hacker@dojo:~$ cat yourfile
This is your file!
hacker@dojo:~$ cat myfile yourfile
This is my file!
This is your file!
hacker@dojo:~$ cat myfile yourfile myfile
This is my file!
This is your file!
This is my file!
Finally, if you give no arguments at all, cat will read from the terminal input and output it. We'll explore that in later challenges...

In this challenge, I will copy the flag to the flag file in your home directory (where your shell starts). Go read it with cat!

### Solve
**Flag:** `pwn.college{oSy_Sne938zQwggHk-Zj3wodyMj.QXxcTN0wyNwIzNzEzW}`

The flag is in flag file.We should read flag file by using cat command.

```bash
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{oSy_Sne938zQwggHk-Zj3wodyMj.QXxcTN0wyNwIzNzEzW}
```

### New Learnings
cat command is used to read files.

### References 
No references 

## catting absolute paths
In the last level, you did cat flag to read the flag out of your home directory! You can, of course, specify cat's arguments as absolute paths:

hacker@dojo:~$ cat /challenge/DESCRIPTION.md
In the last level, you did `cat flag` to read the flag out of your home directory!
You can, of course, specify `cat`'s arguments as absolute paths:
...
In this directory, I will not copy it to your home directory, but I will make it readable. You can read it with cat at its absolute path: /flag

### Solve
**Flag:** `pwn.college{cWhPrDinFePEI43z9NU36EIofPz.QX5ETO0wyNwIzNzEzW}`

In order get the flag we should read the flag file which is in root directory.We use cat command followed by the absolute path of flag file.

```bash 
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{cWhPrDinFePEI43z9NU36EIofPz.QX5ETO0wyNwIzNzEzW}
```

### New Learnings
cat command's arguments can be absolute path.

### References 
No references 

## more catting practice
You can specify all sorts of paths as arguments to commands, and we'll practice some more with cat. In this level, I'll put the flag in some crazy directory, and I will not allow you to change directories with cd, so no cat flag for you. You must retrieve the flag by absolute path, wherever it is.

### Solve
**Flag:** `pwn.college{EO0_9x7AVXBv6dGj9-5xlObyzi5.QXwITO0wyNwIzNzEzW}`

You should directly use cat command on the absolute path of the file.

```bash
hacker@commands~more-catting-practice:~$ cat /lib/terminfo/v/flag
pwn.college{EO0_9x7AVXBv6dGj9-5xlObyzi5.QXwITO0wyNwIzNzEzW}
```

### New Learnings
You can directly use cat command without using cd command by giving the argument absolute path.

### References 
No references 

## grepping for a neddle in a haystack
Sometimes, the files that you might cat out are too big. Luckily, we have the grep command to search for the contents we need! We'll learn it in this challenge.

There are many ways to grep, and we'll learn one way here:

hacker@dojo:~$ grep SEARCH_STRING /path/to/file
Invoked like this, grep will search the file for lines of text containing SEARCH_STRING and print them to the console.

In this challenge, I've put a hundred thousand lines of text into the /challenge/data.txt file. grep it for the flag!

HINT: The flag always starts with the text pwn.college.

### Solve
**Flag:** `pwn.college{MEtmKPfu6so3iTn6weDri2sn3uN.QX3EDO0wyNwIzNzEzW}`

grep command helps us to search the flag.We use grep command followed by pwn.college as the flag starts with that.

```bash 
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{MEtmKPfu6so3iTn6weDri2sn3uN.QX3EDO0wyNwIzNzEzW}
```

### New Learnings
grep is used to search for things.

### References 
No references 

## comparing files
When looking for changes between similar files, eyeballing them might not be the most efficient approach! This is where the diff command becomes invaluable.

diff compares two files line by line and shows you exactly what's different between them. For example:

hacker@dojo:~$ cat file1
hello
world
hacker@dojo:~$ cat file2
hello
universe
hacker@dojo:~$ diff file1 file2
2c2
< world

> universe
The output tells us that line 2 changed (2c2), with world in the first file (<) being replaced by universe in the second file (>).

Sometimes, when new lines are added, you'll see something like:

hacker@dojo:~$ cat old
pwn
hacker@dojo:~$ cat new
pwn
college
hacker@dojo:~$ diff old new
1a2
> college
This tells us that after line 1 in the first file, the second file has an additional line (1a2 means "after line 1 of file1, add line 2 of file2").

Now for your challenge! There are two files in /challenge:

/challenge/decoys_only.txt contains 100 fake flags
/challenge/decoys_and_real.txt contains all 100 fake flags plus the one real flag
Use diff to find what's different between these files and get your flag!

### Solve
**Flag:** `pwn.college{kAxRmBUEVZMO1zvzn-_cy7Nhl2U.01MwMDOxwyNwIzNzEzW}`

We should use diff command to get the difference between two files and u will get the flag.

```bash 
hacker@commands~comparing-files:~$ diff /challenge/decoys_and_real.txt /challenge/decoys_only.txt```
pwn.college{kAxRmBUEVZMO1zvzn-_cy7Nhl2U.01MwMDOxwyNwIzNzEzW}
```

### New Learnings
Diff command tells us the difference between two files.

### References 
No references 

## listing files
So far, we've told you which files to interact with. But directories can have lots of files (and other directories) inside them, and we won't always be here to tell you their names. You'll need to learn to list their contents using the ls command!

ls will list files in all the directories provided to it as arguments, and in the current directory if no arguments are provided. Observe:

hacker@dojo:~$ ls /challenge
run
hacker@dojo:~$ ls
Desktop    Downloads  Pictures  Templates
Documents  Music      Public    Videos
hacker@dojo:~$ ls /home/hacker
Desktop    Downloads  Pictures  Templates
Documents  Music      Public    Videos
hacker@dojo:~$
In this challenge, we've named /challenge/run with some random name! List the files in /challenge to find it.

### Solve
**Flag:** `pwn.college{kzxGcb68ge4jmQYaeT3HqR8CFLp.QX4IDO0wyNwIzNzEzW}`

The flag is present in the challenge directory with an unknown name.To find the flag we should use ls command and to open the correct file we should use . to bypass any errors.

```bash
hacker@commands~listing-files:~$ cd /challenge
hacker@commands~listing-files:/challenge$ ls
hacker@commands~listing-files:/challenge$ ./18204-renamed-run-16602
pwn.college{kzxGcb68ge4jmQYaeT3HqR8CFLp.QX4IDO0wyNwIzNzEzW}
```

### New Learnings
ls command is used to list the files in that directory.

### References 
Chatgpt

## touching files
Of course, you can also create files! There are several ways to do this, but we'll look at a simple command here. You can create a new, blank file by touching it with the touch command:

hacker@dojo:~$ cd /tmp
hacker@dojo:/tmp$ ls
hacker@dojo:/tmp$ touch pwnfile
hacker@dojo:/tmp$ ls
pwnfile
hacker@dojo:/tmp$
It's that simple! In this level, please create two files: /tmp/pwn and /tmp/college, and run /challenge/run to get your flag!

### Solve
**Flag:** `pwn.college{odj6jzaQdTKJJ5GqZ05GRym0HIA.QXwMDO0wyNwIzNzEzW}`

To get the flagh we should create two files in the tmp directory by using touch command.

```bash
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ touch pwn college
hacker@commands~touching-files:/tmp$ /challenge/run
pwn.college{odj6jzaQdTKJJ5GqZ05GRym0HIA.QXwMDO0wyNwIzNzEzW}
```

### New Learnings
touch command is used to create files in the directory.

### References 
No reference.

## removing files
Files are all around you. Like candy wrappers, there'll eventually be too many of them. In this level, we'll learn to clean up!

In Linux, you remove files with the rm command, as so:

hacker@dojo:~$ touch PWN
hacker@dojo:~$ touch COLLEGE
hacker@dojo:~$ ls
COLLEGE     PWN
hacker@dojo:~$ rm PWN
hacker@dojo:~$ ls
COLLEGE
hacker@dojo:~$
Let's practice. This challenge will create a delete_me file in your home directory! Delete it, then run /challenge/check, which will make sure you've deleted it and then give you the flag!

### Solve
**Flag:** `pwn.college{wovx4YM_-hT2pYkBxbZJOJZu74Z.QX2kDM1wyNwIzNzEzW}`

In order to get the flag u should delete the delete_me file and get to the flag.

```bash
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
pwn.college{wovx4YM_-hT2pYkBxbZJOJZu74Z.QX2kDM1wyNwIzNzEzW}
```

### New Learnings
rm command is used to delete the files.

### References 
No reference.

## moving files
You can also move files around with the mv command. The usage is simple:

hacker@dojo:~$ ls
my-file
hacker@dojo:~$ cat my-file
PWN!
hacker@dojo:~$ mv my-file your-file
hacker@dojo:~$ ls
your-file
hacker@dojo:~$ cat your-file
PWN!
hacker@dojo:~$
This challenge wants you to move the /flag file into /tmp/hack-the-planet (do it)! When you're done, run /challenge/check, which will check things out and give the flag to you.
### Solve
**Flag:** `pwn.college{QBgQAl4jVzX4TlwhPGSWuUUaRZi.0VOxEzNxwyNwIzNzEzW}`

We should move the /flag to /tmp/hack-the-planet by using mv command.

```bash
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
hacker@commands~moving-files:~$ /challenge/check
pwn.college{QBgQAl4jVzX4TlwhPGSWuUUaRZi.0VOxEzNxwyNwIzNzEzW}
```

### New Learnings
mv command is used to move files around.

### References 
No reference.

## hidden files
Interestingly, ls doesn't list all the files by default. Linux has a convention where files that start with a . don't show up by default in ls and in a few other contexts. To view them with ls, you need to invoke ls with the -a flag, as so:

hacker@dojo:~$ touch pwn
hacker@dojo:~$ touch .college
hacker@dojo:~$ ls
pwn
hacker@dojo:~$ ls -a
.college	pwn
hacker@dojo:~$
Now, it's your turn! Go find the flag, hidden as a dot-prepended file in /.

### Solve
**Flag:** `pwn.college{gJu5qje2ZhI4sbLudclscNMNkkJ.QXwUDO0wyNwIzNzEzW}`

The flag is a hidden file which is in root directory.We should open root directory and use -a command to see hidden files and read the file whcich contains the flag.

```bash
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls -a
hacker@commands~hidden-files:/$ cat .flag-6880400429469 
pwn.college{gJu5qje2ZhI4sbLudclscNMNkkJ.QXwUDO0wyNwIzNzEzW}
```

### New Learnings
-a is used to show hidden files

### References 
No reference.

## An epic filesyetem quest
With your knowledge of cd, ls, and cat, we're ready to play a little game!

We'll start it out in /. Normally:

hacker@dojo:~$ cd /
hacker@dojo:/$ ls
bin   challenge  etc   home  lib32  libx32  mnt  proc  run   srv  tmp  var
boot  dev        flag  lib   lib64  media   opt  root  sbin  sys  usr
That's a lot of contents! One day, you will be quite familiar with them, but already, you might recognize the flag file and the challenge directory.

In this challenge, I have hidden the flag! Here, you will use ls and cat to follow my breadcrumbs and find it! Here's how it'll work:

Your first clue is in /. Head on over there.
Look around with ls. There'll be a file named HINT or CLUE or something along those lines!
cat that file to read the clue!
Depending on what the clue says, head on over to the next directory (or don't!).
Follow the clues to the flag!
Good luck!

### Solve
**Flag:** `pwn.college{helloworld}`

type in your solve and your thought process behind solving the challenge. Include as much as info as possible. Use triple ticks for any bash commands and output you type on the terminal.

```bash
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls
hacker@commands~an-epic-filesystem-quest:/$ cat GIST
hacker@commands~an-epic-filesystem-quest:/$ cd /usr/local/lib/python3.8/dist-packages/dpkt-1.9.8.dist-info
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/dpkt-1.9.8.dist-info$ ls
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/dpkt-1.9.8.dist-info$ cat LEAD
hacker@commands~an-epic-filesystem-quest:/$ cd /opt/pwndbg/.venv/lib/python3.8/site-packages/mako/ext/__pycache__
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/mako/ext/__pycache__$ ls
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/mako/ext/__pycache__$ cat HINT
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/mako/ext/__pycache__$ cd /opt/pwndbg/.venv/lib/python3.8/site-packages/colored_traceback/always/__pycache__
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/colored_traceback/always/__pycache__$ ls
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/colored_traceback/always/__pycache__$ cat DOSSIER
hacker@commands~an-epic-filesystem-quest:/$ cd /usr/local/lib/python3.8/dist-packages/angr/analyses/propagator
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/angr/analyses/propagator$ ls
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/angr/analyses/propagator$ cat NUGGET
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/angr/analyses/propagator$ cd  /opt/linux/linux-5.4/drivers/net/can/sja1000
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/can/sja1000$ ls -a
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/can/sja1000$ cat .INSIGHT
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/can/sja1000$ cd /usr/share/icons/ubuntu-mono-light/places
hacker@commands~an-epic-filesystem-quest:/usr/share/icons/ubuntu-mono-light/places$ ls
hacker@commands~an-epic-filesystem-quest:/usr/share/icons/ubuntu-mono-light/places$ cat CLUE
hacker@commands~an-epic-filesystem-quest:/usr/share/icons/ubuntu-mono-light/places$ ls /usr/local/lib/python3.8/dist-packages/pwnlib/shellcraft/templates/i386/android
hacker@commands~an-epic-filesystem-quest:~$ cat /usr/local/lib/python3.8/dist-packages/pwnlib/shellcraft/templates/i386/android/TRACE-TRAPPED
hacker@commands~an-epic-filesystem-quest:~$ ls /opt/busybox/busybox-1.33.2/coreutils
hacker@commands~an-epic-filesystem-quest:~$ cat /opt/busybox/busybox-1.33.2/coreutils/README-TRAPPED
pwn.college{sWr8hcuAwVAUh1VsiH6QRMUhJPR.QX5IDO0wyNwIzNzEzW}
```

### New Learnings
Nothing new.

### References 
No reference.

## finding files
So now we know how to list, read, and create files. But how do we find them? We use the find command!

The find command takes optional arguments describing the search criteria and the search location. If you don't specify a search criteria, find matches every file. If you don't specify a search location, find uses the current working directory (.). For example:

hacker@dojo:~$ mkdir my_directory
hacker@dojo:~$ mkdir my_directory/my_subdirectory
hacker@dojo:~$ touch my_directory/my_file
hacker@dojo:~$ touch my_directory/my_subdirectory/my_subfile
hacker@dojo:~$ find
.
./my_directory
./my_directory/my_subdirectory
./my_directory/my_subdirectory/my_subfile
./my_directory/my_file
hacker@dojo:~$
And when specifying the search location:

hacker@dojo:~$ find my_directory/my_subdirectory
my_directory/my_subdirectory
my_directory/my_subdirectory/my_subfile
hacker@dojo:~$
And, of course, we can specify the criteria! For example, here, we filter by name:

hacker@dojo:~$ find -name my_subfile
./my_directory/my_subdirectory/my_subfile
hacker@dojo:~$ find -name my_subdirectory
./my_directory/my_subdirectory
hacker@dojo:~$
You can search the whole filesystem if you want!

hacker@dojo:~$ find / -name hacker
/home/hacker
hacker@dojo:~$
Now it's your turn. I've hidden the flag in a random directory on the filesystem. It's still called flag. Go find it!

Several notes. First, there are other files named flag on the filesystem. Don't panic if the first one you try doesn't have the actual flag in it. Second, there're plenty of places in the filesystem that are not accessible to a normal user. These will cause find to generate errors, but you can ignore those; we won't hide the flag there! Finally, find can take a while; be patient!

### Solve
**Flag:** `pwn.college{helloworld}`

To find the flag file, i used find command to search for the flag file in the root by using -name.

```bash
hacker@commands~finding-files:~$ find / -name flag
hacker@commands~finding-files:~$ cat /usr/local/lib/python3.8/dist-packages/pwnlib/flag
cat: /usr/local/lib/python3.8/dist-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ cat /opt/linux/linux-5.4/arch/s390/numa/flag
pwn.college{8U4Keqt_uUKC74Jye2VngeO60Dh.QXyMDO0wyNwIzNzEzW}
```

### New Learnings
find command is used to search anything in the root.

### References 
No reference.



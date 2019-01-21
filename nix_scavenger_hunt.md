# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox.
/c/Users/James C/Documents/GitHub/wats1030-intro-to-unix

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. 
challenge_files  LICENSE  nix_scavenger_hunt.md  nix_scavenger_hunt_stretch.md  README.md  super_scavengers.md

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory.
It will show permission, user, group, file size, date moddified, and file name.

total 78K
drwxr-xr-x 1 James C 197609    0 Jan 17 17:18 .
drwxr-xr-x 1 James C 197609    0 Jan 17 17:19 ..
drwxr-xr-x 1 James C 197609    0 Jan 17 17:18 .git
drwxr-xr-x 1 James C 197609    0 Jan 17 17:18 challenge_files
-rw-r--r-- 1 James C 197609 1.1K Jan 17 17:18 LICENSE
-rw-r--r-- 1 James C 197609 5.5K Jan 17 17:18 nix_scavenger_hunt.md
-rw-r--r-- 1 James C 197609  325 Jan 17 17:18 nix_scavenger_hunt_stretch.md
-rw-r--r-- 1 James C 197609 2.8K Jan 17 17:18 README.md
-rw-r--r-- 1 James C 197609  268 Jan 17 17:18 super_scavengers.md*

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://man.he.net/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command.
-a, --all
    do not ignore entries starting with .

 -l
    use a long listing format

-h, --human-readable
    with -l, print sizes in human readable format (e.g., 1K 234M 2G)

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem.
bin  cmd  dev  etc  git-bash.exe  git-cmd.exe  LICENSE.txt  mingw64  proc  ReleaseNotes.html  tmp  unins001.dat  unins001.exe  unins001.msg  usr

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues)
/

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. 
/c/Users/James C

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern.
3 file
2015_special_stuff.demo 
cloaked-wookie.demo
scooter-double-mamba.demo

* Use the `cd` command to move "up" one directory. 
one folder up 
~/Documents/GitHub/wats1030-intro-to-unix (master)

* Press the up arrow on your keyboard.
The previous command is what I entered

* Press the up arrow a few more times.
The previous history command what I entered

* Run the `history` command.
all of the commands that I have entered, including the bad ones, so I am not going to copy and paste it

### Observing the System

* Discover what account you are logged into using the `whoami` command.
James C

* Discover who else is on your system with the `who` command.
nothing listed, I presume I am the only person

* How long has your system been running? Use `uptime` to see, and 
bash: uptime: command not found

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) 
Process ID, parent process ID, process group ID, Window process ID, Device number controling TTY, Useer ID number, Stamp time, Command

PID    PPID    PGID     WINPID   TTY         UID    STIME COMMAND
16396       1   16396      16396  cons0     197609 17:59:05 /usr/bin/bash
8096   16396    8096      12364  cons0     197609 19:26:56 /usr/bin/ps

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) 
bash: top: command not found

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename.
2 files 
credit_cards.txt
credit_cards2.txt

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) 
1-15-2015

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`.
./challenge_files/tmp/modi_laboriosam.txt

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). 
2 files

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory.
serial-numbers/eaque_molestiae.txt

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`.
a lot of user and demo files from 01 to wow

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. 
bash: more: command not found

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user.
ps aux command generated a short list of 2
adding grep with my user name nothing happened
grep: C: No such file or directory
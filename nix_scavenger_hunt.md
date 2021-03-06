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

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:* 
        /home/cabox/workspace   
* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?* 
        LICENSE    challenge_files  nix_scavenger_hunt.md          super_scavengers.md
        README.md  nix.hunt         nix_scavenger_hunt_stretch.md
* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*
        The results appear larger
        total 40K
        drwxrwxr-x  4 cabox cabox 4.0K Apr 11 10:24 .
        drwxr-xr-x 11 cabox cabox 4.0K Apr  9 21:44 ..
        drwxrwxr-x  8 cabox cabox 4.0K Apr  9 21:44 .git
        -rw-rw-r--  1 cabox cabox 1.1K Apr  9 21:44 LICENSE
        -rw-rw-r--  1 cabox cabox 2.7K Apr  9 21:44 README.md
        drwxrwxr-x  7 cabox cabox 4.0K Apr  9 21:44 challenge_files
        -rw-r--r--  1 cabox cabox    0 Apr 11 10:24 nix.hunt
        -rw-rw-r--  1 cabox cabox 5.4K Apr  9 21:44 nix_scavenger_hunt.md
        -rw-rw-r--  1 cabox cabox  317 Apr  9 21:44 nix_scavenger_hunt_stretch.md
        -rw-rw-r--  1 cabox cabox  191 Apr  9 21:44 super_scavengers.md
  
* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://man.he.net/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
        I never really got 'man' to work on my laptop but I searched for outside results.
       man is the system's manual pager.
       man ls
           Display the manual page for the item (program) ls.
       man -a intro
           Display,  in  succession,  all  of the available intro manual pages
           contained within the manual.  It is possible to quit  between  suc-
           cessive displays or skip any of them.
       man -l -Tdvi ./foo.1x.gz > ./foo.1x.dvi
           This  command  will  decompress  and format the nroff source manual
           page ./foo.1x.gz into a device independent (dvi) file.   The  redi-
           rection is necessary as the -T flag causes output to be directed to
           stdout with no pager.  The output could be viewed  with  a  program
           such  as  xdvi or further processed into PostScript using a program
           such as dvips. 
      man -h Could not find!
      man ls
           Display the manual page for the item (program) ls.

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
     bin   dev  fastboot  lib    media  opt   root  sbin  sys  usr
     boot  etc  home      lib64  mnt    proc  run   srv   tmp  var        

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
    /home/cabox
* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*
    cabox@box-codeanywhere:~$ ~
    -bash: /home/cabox: Is a directory
     bash: /c/Users/Jshort: Is a directory
     /c/Users/Jshort
* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How      many files do you find?*
     one file
* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
    'ls' command
* Press the up arrow on your keyboard. *What just happened?*
    It went to the previous command
* Press the up arrow a few more times. *What do you see?*
    It keeps scrolling through the previous commands
* Run the `history` command. *What do you see?*
    All commands that Ive used
### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
    Jshort
* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
    There doesnt appear to be anyone else on my system.
* How long has your system been running? Use `uptime` to see, and *paste the result here:*
    bash command was not found
* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
    PID    PPID    PGID     WINPID   TTY         UID    STIME COMMAND
    11208    7812   11208       6324  pty0      197611 18:36:28 /usr/bin/bash
     6740       1    6740       6740  cons0     197611 15:16:20 /usr/bin/bash
     8124    6740    8124       1852  cons0     197611 18:41:47 /usr/bin/ps
     7812       1    7812       7812  ?         197611 18:36:27 /usr/bin/mintty
     9972       1    9972       9972  ?         197611 14:32:10 /usr/bin/ssh-agent

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
    'top' comman was not found
### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
    2 files found with the word 'credit'
* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
    1-15-2015
* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
    located in the tmp file
* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
eaque_molestiae.txt
Excepturi vero itaque minus deserunt. Dolores esse et quisquam veritatis mollitia non eaque.
Quo sed et totam excepturi reiciendis voluptate eveniet. Cum accusantium officia iusto. Exercitationem ullam rerum voluptatem explicabo quos dolores facilis perspiciatis.
Dolor praesentium natus dolores quis et quia sit inventore. Quidem voluptatem laboriosam deserunt qui facilis autem. Qui tenetur voluptatem in voluptate odit laborum aliquid. Sit architecto sed delectus et. Impedit eos quaerat reiciendis nihil quis.
Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia.
Beatae delectus voluptatem rerum id eum quia id et. Doloremque et unde officiis libero. Eum dolor impedit ullam amet sed qui nobis perferendis.
### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
    challenge_files
files.txt
LICENSE
nix.hunt
nix_scavenger_hunt.md
nix_scavenger_hunt_stretch.md
README.md
super_scavengers.md
* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
    A directory of dates and times and usage size with who is working
    
* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:* test1

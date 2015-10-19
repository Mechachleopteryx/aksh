+ [GRUB](#grub)
+ [CONFIG](#config)
+ [DEB Packages](#deb-packages)
   + [PPA](#ppa)
+ [BASH SHELL](#bash-shell)
   + [Automation](#automation)
   + [Bash Scripting](#bash-scripting)
   + [Julia](#julia)
+ [Kernel-HDD](#kernel-hdd)
   + [ISO](#iso)
+ [REGEX](#regex)
+ [General](#general)
+ [UTILITIES](#utilities)
    + [LaTeX](#latex)
    + [ARBTT](#arbtt)
    + [Backups](#backups)

----

# GRUB
+ https://help.ubuntu.com/community/DataRecovery

### grub rescue mode
+ grub rescue, https://www.howtoforge.com/tutorial/repair-linux-boot-with-grub-rescue/
+ How to Rescue a Non-booting GRUB 2 on Linux, https://www.linux.com/learn/tutorials/776643-how-to-rescue-a-non-booting-grub-2-on-linux/
+ https://www.linux.com/learn/tutorials/809671-get-your-data-back-with-linux-based-data-recovery-tools
+ https://www.howtoforge.com/tutorial/repair-linux-boot-with-grub-rescue/
    + Basic Commands: https://www.howtoforge.com/tutorial/repair-linux-boot-with-grub-rescue/#basic-commands-available
+ http://www.cgsecurity.org/wiki/TestDisk
+ http://askubuntu.com/questions/142300/fixing-grub-error-error-unknown-filesystem/179662#179662
+ http://askubuntu.com/questions/493826/grub-rescue-problem-after-deleting-ubuntu-partition
+ HOWTO : [Boot & Install Ubuntu from the Grub Rescue Prompt](https://ubuntuforums.org/showthread.php?t=1599293)
+ http://www.supergrubdisk.org/
+ https://help.ubuntu.com/community/Grub2/Troubleshooting
+ http://itsfoss.com/solve-error-partition-grub-rescue-ubuntu-linux/
+ Recovering a deleted partition table: http://tldp.org/HOWTO/Partition/recovering.html

----

# CONFIG

+ Stow: https://www.gnu.org/software/stow/
+ http://en.wikipedia.org/wiki/Category:Configuration_files
+ http://en.wikipedia.org/wiki/INI_file

## Config-Git
+ https://stackoverflow.com/questions/21249071/where-do-you-store-your-gitconfig-file
+ https://stackoverflow.com/questions/11786623/cant-hard-link-the-gitconfig-file

## INI-RC-YAML
+ https://stackoverflow.com/questions/5014632/how-can-i-parse-a-yaml-file-from-a-linux-shell-script
   - https://gist.github.com/pkuczynski/8665367
+ screenrc, http://www.softpanorama.org/Utilities/Screen/screenrc_examples.shtml

----

# DEB Packages
+ DPKG cheat sheet: http://www.cyberciti.biz/howto/question/linux/dpkg-cheat-sheet.php
+ Syntax 	Description 	Example
+ dpkg -i {.deb package} 	Install the package 	dpkg -i zip_2.31-3_i386.deb
+ dpkg -i {.deb package} 	Upgrade package if it is installed else install a fresh copy of package 	dpkg -i zip_2.31-3_i386.deb
+ dpkg -R {Directory-name} 	Install all packages recursively from directory 	dpkg -R /tmp/downloads
+ dpkg -r {package} 	Remove/Delete an installed package except configuration files 	dpkg -r zip
+ dpkg -P {package} 	Remove/Delete everything including configuration files 	dpkg -P apache-perl
+ dpkg -l 	List all installed packages, along with package version and short description 	dpkg -l ; dokg -l | less ;  dpkg -l '*apache*' ; dpkg -l | grep -i 'sudo'
+ dpkg -l {package} 	List individual installed packages, along with package version and short description 	dpkg -l apache-perl
+ dpkg -L {package} 	Find out files are provided by the installed package i.e. list where files were installed 	dpkg -L apache-perl ; dpkg -L perl
+ dpkg -c {.Deb package} 	List files provided (or owned) by the package i.e. List all files inside debian .deb package file, very useful to find where files would be installed 	dpkg -c dc_1.06-19_i386.deb
+ dpkg -S {/path/to/file} 	Find what package owns the file i.e. find out what package does file belong 	dpkg -S /bin/netstat
dpkg -S /sbin/ippool
+ dpkg -p {package} 	Display details about package package group, version, maintainer, Architecture, display depends packages, description etc 	dpkg -p lsof
+ dpkg -s {package} | grep Status 	Find out if Debian package is installed or not (status) 	dpkg -s lsof | grep Status


## PPA
#### Adding PPA's
1. Add a PPA using APT in terminal by typing the following command: `sudo add-apt-repository ppa:PPA_Name/ppa`

#### Removing PPA's
1. Remove a PPA using APT in terminal by typing the following command: `sudo add-apt-repository --remove ppa:PPA_Name/ppa`
2. Remove a PPA from the source list, else it will get pulled when you update the system.
   + First, find where these PPAs are stored by listing all the PPAs added in your system: `sudo ls /etc/apt/sources.list.d`.
   + Then remove the PPA using the following command: `sudo rm -i /etc/apt/sources.list.d/PPA_Name.list`
3. Remove a PPA by using `ppa-purge` in terminal - What about the applications installed using PPAs? Will they be removed as a result of removing the PPA? The answer is NO. So, we use `PPA purge` to remove the PPA and uninstall all the programs installed by the PPA.
   + Install ppa-purge with this command: `sudo apt-get install ppa-purge`
   + Then use it to purge the PPA: `sudo ppa-purge ppa-url` {{The URL of the PPA can be found in the Software Sources list.}}

----

# BASH SHELL
+ https://en.wikipedia.org/wiki/List_of_Unix_commands
+ [ctypes.sh](https://github.com/taviso/ctypes.sh) :: A BASH plugin that provides a foreign function interface directly in your shell. In other words, it allows you to call routines in shared libraries from within bash.
+ https://stribika.github.io/2015/01/04/secure-secure-shell.html
+ What is the difference between executing a bash script and sourcing a bash script?, http://superuser.com/questions/176783/what-is-the-difference-between-executing-a-bash-script-and-sourcing-a-bash-scrip

### Automation
+ [basher](https://github.com/basherpm/basher) :: A package manager for shell scripts. 
+ https://github.com/alebcay/awesome-shell

### Bash Scripting
+ https://help.ubuntu.com/community/Beginners/BashScripting

### Julia
+ http://stackoverflow.com/questions/30586740/julia-command-line-running-processes-in-parallel
+ http://blog.leahhanson.us/running-shell-commands-from-julia.html
+ http://julialang.org/blog/2012/03/shelling-out-sucks/
+ http://julialang.org/blog/2013/04/put-this-in-your-pipe/   
+ https://www.reddit.com/r/Julia/comments/2ph74u/interacting_with_shell/

----

# Kernel-HDD
+ http://www.brendangregg.com/perf.html
+ Initramfs, https://en.wikipedia.org/wiki/Initramfs

## ISO
+ http://releases.ubuntu.com/
+ Ubuntu iso via wget, https://askubuntu.com/questions/305304/download-13-04-iso-with-wget
+ 64-bit Vs. 32-bit, https://superuser.com/questions/238112/what-is-the-difference-between-i686-and-x86-64

#### Ubuntu Cloud Snappy
+ https://askubuntu.com/questions/620996/how-to-install-snappy-ubuntu-15-04-core-images-on-a-pc
+ http://www.ubuntu.com/cloud/tools/snappy
+ https://wiki.ubuntu.com/Core

### multiboot iso
+ SARDU, http://www.howtogeek.com/howto/39880/how-to-combine-rescue-disks-to-create-the-ultimate-windows-repair-disk/
+ MultiCD, https://github.com/IsaacSchemm/MultiCD
   + http://multicd.us/#Instructions
+ https://askubuntu.com/questions/46624/how-to-create-a-bootable-usb-with-multiple-iso-images-in-it
+ https://ubuntuforums.org/showthread.php?t=1071869

----

# REGEX
+ http://en.wikipedia.org/wiki/List_of_Unix_commands
+ http://stackoverflow.com/questions/16956810/finding-all-files-containing-a-text-string-on-linux?rq=1
+ https://en.wikipedia.org/wiki/Regular_expression#Syntax
+ http://www.theunixschool.com/2012/07/find-command-15-examples-to-exclude.html

----

# General
+ List Open Files for Process, http://www.cyberciti.biz/faq/howto-linux-get-list-of-open-files/
+ http://askubuntu.com/questions/240857/what-commands-will-change-my-screens-brightness
+ [Installing Image Magick on Ubuntu 14.04](https://gist.github.com/rodleviton/74e22e952bd6e7e5bee1)
+ https://github.com/ewiger/findtools

----

# UTILITIES

## Arbtt
__desktop timetracker__
+ https://www.joachim-breitner.de/blog/336-The_Automatic_Rule-Based_Time_Tracker
+ GITHUB mirror :
+ http://arbtt.nomeata.de/#how
+ Install : http://arbtt.nomeata.de/#install
+ Sample Categorize :: http://darcs.nomeata.de/arbtt/categorize.cfg
+ http://stackoverflow.com/questions/20973590/arbtt-nested-if-then-else-in-categorize-cfg/20973950#20973950
+ https://wiki.haskell.org/Unicode-symbols
+ http://darcs.nomeata.de/arbtt/doc/users_guide/arbtt-stats.html#idp213048

## Backups
+ [attic](https://github.com/jborg/attic) :: Deduplicating backup program. [Docs](https://attic-backup.org/).
+ https://github.com/xolox/python-rotate-backups
+ BakThat {Stopped} : https://github.com/tsileo/bakthat
+ rsync, http://www.mikerubel.org/computers/rsync_snapshots/

http://stackoverflow.com/questions/123198/how-do-i-copy-a-file-in-python
http://stackoverflow.com/questions/3207219/how-to-list-all-files-of-a-directory-in-python
http://codereview.stackexchange.com/questions/49351/python-back-up-script
https://pypi.python.org/pypi/storelet

## LaTeX
+ Prof. Edward R. Scheinerman's resources to "[Learn LaTeX](http://www.ams.jhu.edu/~ers/learn-latex/)".
+ http://tex.stackexchange.com/questions/8374/the-key-to-understanding-the-latex-syntax
+ latex for MATH: http://en.wikibooks.org/wiki/LaTeX/Mathematics
+ LaTeX tutorial : http://www.pages.drexel.edu/~pyo22/students/latexRelated/latexTutorial.html
+ http://latex-project.org/intro.html

----


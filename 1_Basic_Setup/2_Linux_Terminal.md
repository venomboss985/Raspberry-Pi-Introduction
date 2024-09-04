---
marp: true
theme: gaia
class: invert
paginate: true
style: |
  .columns {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }
header: "*Basic Setup Pt. 2* :tv:"
---
<!-- _header: "" -->
# Linux and Terminal Overview :desktop_computer:

* Pi OS desktop and compatibility overview
* Hacking with the terminal
* Some Pi specific commands

By: Hedron Hackerspace

![bg right w:600](images/desk_setup.jpg)

---

# Pi OS

* Debian based
* Full desktop environment
  * LibreOffice => MS Office
  * LxTask => Task Manager
* Contains some development utilities
  * IDEs and text editors
  * Interpreters/compilers
  * Lots of CLI tools

![bg right w:600](images/bookworm_desktop.png)

---

# Software Compatibility

* Not everything is going to run on a Pi
  * Runs Linux instead of Windows
  * Using an ARM SoC (armv8) instead of an x86 CPU
* General hardware limitations
  * 4 cores, 4 threads (no SMT* or hyperthreading)
    * Slow cores (at most 2.1GHz all core)
  * 8GB RAM (at most)
  * Might be using a small and/or slow MicroSD card
<!-- _footer: "* - Simultaneous multithreading" -->
---

## How to find Compatible Software

### Web Search

1. Search software or task + "raspberry pi" (easiest)
2. Search for a Debian ARM version (armv8)
3. Look in support threads or forums for other people's findings

### Last Resort

* If source is available, compile it yourself

---

# The Terminal

* Text-based interface
* Speaks directly to the OS
* Extremely powerful tool
* Deceptively simple

## We will cover

* Linux file system
* Navigation commands
* Some Pi specific commands

![bg right w:600](images/pi_terminal.png)

---

# Getting Help

<div class=columns>
<div>

## `--help` flag

* `<command> --help`
* Prints out the basics on how to use the flagged command
* Try running `cd --help`

</div>
<div>

## `man` command

* Use `man <command>` to receive much more detailed information
* Short for "manual" or "man pages"
* Try running `man less`

</div>
</div>

---

# The `sudo` prefix

* Short for "superuser do"
* Runs the proceeding command as the root user
* Users not added to the `sudo` group can't use it </br> ('pi' user has access by default)
* Used when a command needs root permissions to run
* Try running `apt-get update`, then prefixing with `sudo`

---

# In Linux, ***EVERYTHING*** </br> is a file

* Use the command `ls /dev`
* Shows every hardware device connected to the Pi
* `ls /dev/bus/usb/001` shows what is currently plugged into the USB ports of the Pi

![bg right w:600](images/ls_dev.png)
<!-- _footer: "We will get into using `ls` later" -->
---

# Who, What, and Where Am I?

<div class=columns>
<div>

## `pwd` command

* Prints the working directory/folder you are currently in
  * Ex. `pwd`
* Short for </br>"print working directory"

</div>
<div>

## `whoami` command

* Prints the currently logged in user
  * Ex. `whoami`

## `hostname` command

* Prints the computer's name
  * Ex. `hostname`

</div>
</div>

---

# Listing Files and Moving Directories

<div class=columns>
<div>

## `ls` command

* Lists folders and files in the specified directory*
  * Ex. `ls /`
* Short for "list"
* `-a` flag to list hidden </br> folders and files
* `-g` flag to list permissions

</div>
<div>

## `cd` command

* Changes the active/working directory*
  * Ex. `cd ~/Desktop`
* Short for "change or choose directory"
* Uses relative and absolute directories

</div>
</div>

<!-- _footer: "* - Assumes current directory if not specified" -->
---

## Relative and Absolute Paths

* There are relative and absolute directories:
  * `.`  = Relative/current folder
  * `..` = Up one level
  * `~`  = Home directory of the active user
  * `/`  = Root directory
* Makes folder navigation much quicker
* Directories can be strung together
  * Ex. `cd ../build`
  * Ex. `cd /boot` or `cd ~/Desktop`

---

# Creating Files and Folders

<div class=columns>
<div>

## `touch` command

* Creates a file* with the specified name and extension
  * Ex. `touch notes.txt`
* File extension is not strictly necessary
  * Ex. `touch Dockerfile`

</div>
<div>

## `mkdir` command

* Creates a folder* with the specified name
  * Ex. `mkdir build`
* Short for "make directory"
* `-p` flag creates parent folders if they don't exist
  * Ex. `mkdir -p parent/child`

</div>
</div>

<!-- _footer: "* - Assumes current directory if not specified" -->
---

# Deleting Files and Folders

<div class=columns>
<div>

## `rm` command

* Deletes the specified file or folder
  * Ex. `rm notes.txt`
* Short for "remove"
* `-r` flag recursively deletes everything in a directory (including the parent folder)
  * Ex. `rm -r build/`

</div>
<div>

## `rmdir` command

* Deletes the specified folder
  * Ex. `rmdir build`
* Short for "remove directory"
* `-p` flag deletes parent folders
* Will not work if folder contains any items

</div>
</div>

---

# Moving and Copying Files

<div class=columns>
<div>

## `mv` command

* Moves contents to a </br> new directory
  * Ex. `mv notes.txt ~/Documents`
* Short for "move"
* Also renames files
  * Ex. `mv notes.txt nos.md`
* Works with folders too

</div>
<div>

## `cp` command

* Copies a file to a </br> new directory
  * Ex. `cp program.o ~/Desktop`
* Short for "copy"
* `-r` flag recursively copies folder contents
  * Ex. `cp -r build/ ~/Desktop`

</div>
</div>

---

# Viewing File Contents

<div class=columns>
<div>

## `cat` command

* Prints the contents of the file
  * Ex. `cat notes.txt`

## `less` command

* Scrollable file text with interactive commands
  * Ex. `less notes.txt`

</div>
<div>

## `head`/`tail` commands

* Prints first/last 10 lines </br> of a file
  * Ex. `tail notes.txt`
* `-n` prints N amount of lines
  * Ex. `head -n 25 notes.txt`
  * Ex. `tail --lines=5 temp.txt`

</div>
</div>

---

# APT Commands

* APT = Advanced Packaging Tool
* Package manager for Ubuntu/Debian based systems
* Needs root permissions
* 5 main commands (`-y` accepts "Are you sure?" prompts)
  * `install` - Installs a package
  * `remove` - Uninstalls a package (`--purge` to remove user data)
  * `update` - Updates all package info if a new version is released
  * `upgrade` - Updates all packages that have a new version
  * `autoremove` - Deletes any packages that are no longer needed

---

# Other Linux Commands

* Covered the foundational commands to any Linux system
* Too many commands to go over in one session </br> (let alone several classes)
* Most important commands - `man <command>` and `<command> --help`
* Some others you can try out:
  * `htop` - Terminal based task manager
  * `ip a` - Network connection information
  * `df -h` - Storage information
  * `uname -a` - Hardware and OS information

---

# Some Pi Specific Commands

* `vcgencmd measure_temp` - Measures CPU temps
* `vcgencmd measure_clock` - Measures CPU clock speed
* `vcgencmd measure_voltage` - Measures CPU voltage
* `raspinfo` - Raspberry Pi info (also creates `raspinfo.txt` in dir)
* `raspi-config` - Raspberry Pi terminal configurator
* `raspi-gpio` - Raspberry Pi GPIO command interface (covered in depth in the Python module)
* `pinout` - Raspberry Pi peripheral list and GPIO pinout diagram

---

# Next Steps

* Take some time and familiarize yourself with these commands
  * Over time, they will become second nature
* Let me know if you would like another class that covers more useful terminal commands and shortcuts in depth
* After you feel ready, move on to the Python Introduction module
  * Learn basics of Python and create your own programs
  * Learn how to read documentation
  * Interface with the GPIO pins (Digital pins, PWM, I2C/SPI, etc.)

<!-- _footer: "Continue to next section: **2_Python_Intro**" -->
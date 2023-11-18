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

![bg right w:600](https://www.raspberrypi.org/app/uploads/2019/08/MAGPI_85_COVER020819-7.jpg)
<!-- _footer: "Rev. 1.1" -->
---

# Pi OS

* Debian based
* Full desktop environment
  * LibreOffice => MS Office
  * LxTask => Task Manager
* Contains some development utilities
  * IDEs and text editors
    <!-- (VS Code, Thonny, `nano`, `vim`, etc.) -->
  * Interpreters and compilers
    <!-- (Python, C/C++, Lua, etc.) -->

![bg right w:600](https://9to5linux.com/wp-content/uploads/2023/10/rpios.webp)

---

# Software Compatibility

* Not everything is going to run on a Pi
  * Runs Linux instead of Windows
  * Using an ARM SoC (armv8) instead of an x86 CPU
* General hardware limitations
  * 4 cores, 4 threads (no SMT* or hyperthreading)
    * Slow cores (at most 2.1GHz all core)
  * 8GB RAM (at most)
  * Might be using a small MicroSD card
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
* Directly talks to the OS
* Extremely powerful tool
* Deceptively simple

## We will cover

* Linux file system
* Navigation commands
* Some Pi specific commands

![bg right w:600](https://projects-static.raspberrypi.org/projects/raspberry-pi-using/f30504afb3b35e3da258c484813140d8277d6de3/en/images/pi-terminal-ls.png)

---

# Getting Help

<div class=columns>
<div>

## `help` command

* `<command> --help`
* Prints out how to use the command
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

![bg right w:600](https://i.stack.imgur.com/xexRF.png)
<!-- _footer: "We will get into using `ls` later" -->
---

# Who and Where Am I?

<div class=columns>
<div>

## `pwd` command

* Prints the working directory/folder you are currently in
  * Ex. `pwd`
* Short for "print working directory"

</div>
<div>

## `whoami` command

* Prints the current logged in user
  * Ex. `whoami`

## `hostname` command

* Prints the computer's name
  * Ex. `hostname`

</div>
</div>
<!-- _footer: "Might seem useless, but they're used in shell commands and scripts" -->

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

* Changes the working directory*
  * Ex. `cd ~/Desktop`
* Short for "change or choose directory"
* Uses relative and absolute directories

</div>
</div>

<!-- _footer: "* - Assumes local directory if not specified" -->
---

## Relative and Absolute Paths

* There are relative and absolute directories:
  * `.`  = Relative/current folder
  * `..` = Up one level
  * `~`  = Home directory
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

<!-- _footer: "* - Assumes local directory if not specified" -->
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
* Will not work if folder contains any items
* `-p` flag deletes parent folders
* Delete non-empty folders with `--ignore-fail-on-non-empty`

</div>
</div>

---

# Moving and Copying Files

<div class=columns>
<div>

## `mv` command

* Moves contents to a new directory
  * Ex. `mv notes.txt ~/Documents`
* Short for "move"
* Can rename files
  * Ex. `mv notes.txt nos.md`
* Works with folders too

</div>
<div>

## `cp` command

* Copies file to another directory
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

* Prints first/last 10 lines of a file
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

# How to install and use the Bare-Arduino-Project

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](http://doctoc.herokuapp.com/)*

- [About](#about)
- [Installation Guide](#installation-guide)
  - [Important note about bugs and issues](#important-note-about-bugs-and-issues)
  - [Getting Ready - The Toolbox](#getting-ready---the-toolbox)
    - [OS X](#os-x)
    - [Linux](#linux)
  - [1. Install `avr-gcc`, `binutils`, `avr-libc` and `avrdude`](#1-install-avr-gcc-binutils-avr-libc-and-avrdude)
    - [OS X](#os-x-1)
    - [Linux](#linux-1)
  - [2. Clone `Bare-Arduino-Project` repository from Github](#2-clone-bare-arduino-project-repository-from-github)
  - [3. Install `pySerial`](#3-install-pyserial)
  - [4. Test that evrything is up and running](#4-test-that-evrything-is-up-and-running)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## About

You will be guided during the installation and setup of the toolchain.

The toolchain gathers all the pieces of software you need to successfully write, compile, debug, recompile and upload the code of your Arduino projects.

It took us quite some time to figure out what to do, how to do it, which Homebrew `formula` to install, how to use the `Makefile` and so on. When we say quite some time, you can count full working weeks of reading, trying, trying again, cursing because nothing is working, dead ends, new ideas, clearer vision and finally a working toolchain.

> I don't have a mac, I don't know how it works, so this modifications excludes OSX.
> I think this approach less complicated than cloning whole project each time.

Have fun! :)

## Installation Guide

### Important note about bugs and issues

If during or after the installation process, something **does not** work with the [Bare-Arduino-Project](https://github.com/WeAreLeka/bare-arduino-project), please **first report the issue [here** in this repo issue tracker](https://github.com/WeAreLeka/bare-arduino-project/issues) and **not in Arduino-Makefile**.

It will allow us to investigate first and not overflow the Arduino-Makefile issue tracker with unrelated issues.

### Getting Ready - The Toolbox

#### Linux

Before starting we need to install `git` and `arduino`:

```Bash
# First add the git-core ppa
$ sudo add-apt-repository ppa:git-core/ppa

# Update list
$ sudo apt-get update && sudo apt-get upgrade

# Install latest git and Arduino
$ sudo apt-get install git arduino
```

### 1. Install `avr-gcc`, `binutils`, `avr-libc` and `avrdude`

#### Linux

```Bash
$ sudo apt-get install gcc-avr binutils avr-libc avrdude
```

Make sure everything is up and running by running `avr-gcc -v` and `avrdude -v`.

### 2. Clone `Bare-Arduino-Project` repository from Github

Simply clone the repo inside /usr/local/share/bare-arduino-project:

```Bash
# git clone https://github.com/arthurafarias/Bare-Arduino-Project /usr/local/share/bare-arduino-project
```

Initialize and update submodules:

```Bash
# cd /usr/local/share/bare-arduino-project	
# git submodule update --init --recursive
```

[Fork template on github](https://github.com/arthurafarias/Bare-Arduino-Project-Template-Linux)

Follow steps available at https://help.github.com/articles/fork-a-repo/.
 
[Clone template](https://github.com/your-account/your-project)

```Bash
$ git clone https://github.com/you-account/your-project /path/to/your-project
$ cd /path/to/your-project
```

### 3. Install `pySerial`

First, if you don't already have Python, you can install it using apt-get on Ubuntu:

```Bash
$ apt-get install install python python-pip
```

Then install `pySerial`:

```Bash
$ pip install pyserial
```

### 4. Test that evrything is up and running

To make sure you're up and running to hack Arduino, we are going to compile some code.

First `cd` to `/path/to/your-project` folder:

```Bash
$ cd /path/to/your-project
```

**Don't forget** to modify the `Makefile` to suit your needs.

Then compile and upload your code to an **Arduino Mega 2560**:

```Bash
$ make
$ make upload
```

If it's not working, make sure everything has been installed correctly and check your `Makefile` configuration. Also make sure you are using and `Arduino Mega 2560`.

If nothing seems to help, you can fill an [issue here](https://github.com/arthurafarias/Bare-Arduino-Project/issues).

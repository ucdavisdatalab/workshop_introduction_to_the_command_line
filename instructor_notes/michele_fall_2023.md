# Introduction to the Unix Command Line

Instruction notes by Michele Tobias

## 1 Overview

Today we're learning Unix Command Line!

Why do we want to know this?

 * It allows us to talk directly to our computers
 

What kinds of tasks can we use it for?

 * Manage files - especially bulk tasks like moving files
 * Run programs
 * Running programs on remote servers like our compute clusters
 * Version control tools like Git
 * Setting up virtual environments with tools like Docker
 * Installing software and packages for programming languages


## 2 Preliminaries

### Objectives

By the end of the workshop, learners should be able to:

 * Explain the directory structure of their computers
 * Navigate across and within files and directories
 * Create, copy, move, and delete files
 * Use command line tools to edit files
 * Identify where to go for help and to learn more
 
 
 ### Prerequisites
 
 I'm going to assume you're installed some form of Command Line Interface on your computer.
 

### 3 Installation

We're skipping this because you've already done it.


## 4 Interacting with Our Computers

You probably interact with your computer through a **Graphical User Interface** or a **GUI** (pronounced "gooey"). There are images and text that you interact with using a mouse and keyboard.

**BUT** there are other ways you can interact with a computer.

**Command Line Interface** (CLI) is one. It's the original way we worked with computers. That changed in the 1980s when companies like Apple began marketing computers to a wider audience.

### To the Command Line: A Mentality Shift

Working with the command line requires some shifts in thinking if you're used to working with a GUI.

 1. GUIs often handle things for us. With CLI, we often have to do some extra steps. Learning about how our computers work will help.
 2. For people who like to visualize things, the command line can feel like a mystery. How do you even know where to start or what it's doing? This gets easier with practice.

## Command Line Basics

### Start Your Command Line

**Macs:** Applications -> Utilities -> Terminal

**Windows:** 
1. Click on the Windows Start Menu and search for “Git Bash” *- or -*
2. Click on the Windows Start Menu, select Programs, and browse to Git Bash

### The Anatomy of the Command Line

Let's take a tour of the interface!

At first, it's a mostly empty screen.

There is some text (which may or may not have different colors).

This is a prompt.
```
mmtobias@LIBLAP-R90WC4S7 MINGW64 ~
$
```

Pieces of the Prompt:

 * `mmtobias` = user name
 * `LIBLAP-R90WC4S7` = computer
 * `~` = home directory
 * `$` = the command line is ready and waiting
 * Cursor = either a line or box, blinking or not - move it left or right with the arrows on your keyboard


### Interacting with the Command Line

First command:

```
$ echo "Hello world!"
```

Let's look at another, perhaps more useful command, `ls` (short for "list"):

```
$ ls
```

Let's look at the contents of one folder:

```
$ ls Zotero
```

Let's get even more information using flags

l = long listing format
h = human-readable (not H)
a = all - show all the files including hidden ones

```
$ ls -lha Zotero 
```

Output explanation:

 * user name
 * date
 * permissions = on the left
 * file size

### Command Syntax

You may have noticed a pattern to how commands are constructed.

```
$ [command] [optional flags] [file, data, or other pointer on which to run the command]
```

**Word of Warning:** Spaces matter. Don't put spaces in your file names!

This will throw an error:

```$ [command] file name.txt```

This will not:

```$ [command] file\ name.txt```

`\` is an **escape character**. 

### Common Command Line Commands (and More!)

See the reader for a list of common commands!


### When Problems Arise









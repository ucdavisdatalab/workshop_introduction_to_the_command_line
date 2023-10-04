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
 * `MINGW64` = the name of the terminal (you might not have this)
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
$ ls valhalla_california
```

Let's get even more information using flags. Use a flag by adding `-` and then a character or string of characters

l = long listing format
h = human-readable (not H)
a = all - show all the files including hidden ones

```
$ ls -lha Zotero 
$ ls -lha valhalla_california
```

Output explanation:

 * user name
 * date
 * permissions = on the left
 * file size
 
Permissions:
 * r = read
 * w = write
 * x = execute
 
Dot files:
Example: .config or .gitignore

We'll learn more about these in a minute:
`.` means same directory
`..` means go up a directory



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


### Error Messages: When Problems Arise

Read the error messages. They are designed to help you. Most of the time they help.

What happens if you ask ls to show a directory that doesn't exist?

```
$ ls no_name

```

What happens if you write a command that doesn't exist?

```
$ echo"hello"
```

Sometimes you can't interpret what the error is. Search engines can help.


How do you stop a CLI process? **CTRL + C** (you might know this as "copy" but it means "interrupt" to the command line.)

**CAUTION:** there is no "undo" for command line. Be cautious when you are modifying and deleting things on your computer.




## Navigation & File Paths

You're used to using your mouse to navigate and click on things, but with the command line we'll use our keyboard to do this.

### File Paths

**Files** are chunks of data on your computer.

**Directories** are the folders they live in. Directories exist in a **directory structure** - a hierarchical organization of folders (i.e. folders can be inside other folders).

A **Path** is the address for a given directory or file. It's a sequence of folders to navigate to locate a place in your directory structure.

Example directory: workshop/data/trees.csv

Each / in a path denotes a new level in the directory structure - directories can be higher or lower than another.

**Root** is the top-most directory - denoted with / - think of this as the trunk of a tree and the rest of the structure descends below it.

`pwd` tells you your current working directory (path) relative to the root.

### Absolute vs. Relative Paths

There are two ways to write paths: Absolute and Relative

**Absolute Paths** = begin with / (root) and show the full path from the root.

**Relative Paths** = context specific - it depends on where you are in your directory structure
 * Useful when a folder might change locations or computers - this often happens with GitHub repositories
 
Shorthand to note:
 * `.` = the current location
 * `..` = one directory above the current location


Let's try this some of the things we just learned:

What folders do we have again?
```
$ ls
```

Let's change directories (go into a different folder) using a direct path:

```
$ cd /c/Users/mmtobias/Zotero
```

Now let's try going up to the folder above and changing into a different folder using a relative path:

```
$ cd ../valhalla_california
```

## Moving Data Around

Navigate to where we want to make a new directory

```
cd D:/
```

Print the current working directory:

```
pwd
```

Make a new folder

```
mkdir cl_workshop
```

see what happened

```
ls
```

```
ls cl_workshop
```

Let's download an image from the DataLab website. Go to datalab.ucdavis.edu and download any image you like to this new directory.

Let's make a new folder in our workshop folder to hold images:

```
cd cl_workshop/
mkdir images
ls
```

Let's move the image we just downloaded into our new images folder!

```
mv ./datalab_logo_square-square.png ./images/datalab_logo_square-square.png
```

Note: ./ means we're using the current directory so we don't have to write it all out



## Editing Files

### Plain Text vs. Binary Files

**Plain Text** = stored in human-readable form; typically a collection of characters (like UTF or ASCII)

**Binary Text** = stored as a sequence of 0 and 1; no characters; not readable (example: try opening an image file in a text editor)

### Inspecting a File

Let's get more information about our image file:

```
cd /d/cl_workshop

file ./images/datalab_logo_square-square.png./images/datalab_logo_square-square.png

file example.txt

```

Let's look inside a text file:

```
cat example.txt

head example.txt
```

`cat` is short for concatenate and prints all of the file to the screen.

`head` prints the first 10 lines


## Command Line Text Editors

We'll work with a text editor that comes with Macs and Git Bash called **Vim**.

Let's make a text file and add text to it!

`vi` followed by a file name will open the file, and if the file doens't exist yet, it will make it.

```
vi hello.txt
```

Vim has 2 modes:
 1. **Normal** mode = starts in normal mode; command-based; no text editing
 2. **Insert** mode = lets us edit text.
 
Change to insert mode: press **i** on your keyboard --> notice the bottom says **-- INSERT --**

Now write some text.

**ESC Key** returns to normal mode.

Let's save! In Normal mode, type `:w` then hit enter --> note the message at the bottom of the window.

Let's quit Vim now that we're done. Type `:q` then hit enter. --> back to the command line!

Other options:
	`:q!` exits without saving
	`:wq` saves and then exits

See the reader for more!

## Cleaning Up

Now we'll learn about how to remove files - `rm`

Let's delete the text file we just created with Vim.

```
pwd

ls

rm hello.txt

```

Adding the `-r` (recursive) flag allows you to delete folders.

**CAUTION:** Command line has NO undo. Adding the `-i` flag will use interactive mode, which will ask for confirmation before you delete anything.

## Wrap Up

We just scratched the surface of what's possible.

I hope you have learned enough today to feel confident in continuing to learn and work with command line.






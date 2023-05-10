# BASH Tutorial

In this tutorial we will learn about the most common commands used in bash, how they work and what can we do with them.

## Command Change Directory (cd):
The command **Change Directory**, written *cd* in the command line or terminal, is a command that allows to go to a different directory inside of our system.
Basically, it allows to go from the folder we are in to a different folder in our system.

This command can be used in different ways, so we will go through all of them, explaining them and including some examples.

### 1. cd
When we write just the command cd in our terminal and press Enter, we are telling our computer to move from the directory we are at to our HOME directory.
When you open a terminal or console, the current working directory is set to your HOME directory by default. This command will take you to that folder.
It is written in the following way:

```console
SystemName:~ username$ cd
```

Now, let's imagine the structure in our HOME directory is the following: we have three folders (Folder1, Folder2 and Folder3) and inside of each one, there are 2 more folders.
- HOME directory
  * Folder1
    - Folder1_1
    - Folder1_2
  * Folder2
    - Folder2_1
    - Folder2_2
  * Folder3
    - Folder3_1
    - Folder3_2

### 2. cd PATH
In order to go to *Folder3_1* from our HOME directory we need to use *cd* in the following way and press Enter after that.

```console
System:~ username$ cd Folder3/Folder3_1
```
After executing the command we will see the following in our console, indicating the folder we are in:
```console
SystemName:~ username$ cd Folder3/Folder3_1
SystemName:Folder3_1$ 
```

### 3. cd ..
What if we want to go back to the parent folder of the one we are in? In our example, the parent folder of the *Folder3_1* is **Folder3**.
```console
SystemName:Folder3_1$ cd ..
```
After executing the command we will see the following in our console:
```console
SystemName:Folder3_1$ cd ..
SystemName:Folder3$ 
```
We can also concatenate the use of this command if we want. Let's go to Folder3_1 again.
```console
SystemName:~ username$ cd Folder3_1
SystemName:Folder3_1$ 
```
Now, imagine we want to go to the HOME Folder from here (Folder3_1).
Apart from doing it the way we already know, by typing *cd*, we can also do the following:
```console
SystemName:Folder3_1$ cd ../..
```
After executing the command we will see the following in our console, indicating we are back in our Working Directory:
```console
SystemName:Folder3_1$ cd ../..
SystemName:~ username$ 
```

## Command Print Working Directory (pwd):
We have spoken about the Working Directory in the previous section, but... How do I know its PATH? Fortunately we have the *pwd* command for that.
```console
SystemName:~ username$ pwd
```
After writing this command and pressing Enter, the **full path** of your Current Working Directory will be printed in the console.
```console
SystemName:~ username$ pwd
/Users/username/
```
If we are working in a different folder though, the *pwd* command will show the full path of the directory you are currently working at. So, let's go back to Folder3_1 so we can try it.
```console
SystemName:~ username$ cd Folder3/Folder3_1
SystemName:Folder3_1$ pwd
/Users/username/Folder3/Folder3_1
```
As you can see, now the print working directory command returns the full path of the folder we are currently in.
But, what if I want to know the full path of my HOME directory from any folder? We can do this by using the next command in our list: *echo*.

## Command to Print Strings or Lines in a console (echo):
The *echo* command is one of the most used in shell scripts and consoles in *Bash*. Its function is to print in the console a line or a string.
If you don't know what a string is, let's keep it simple. A string is a group of characters. ("Hello" is a string).

Let's go back to how to print the path of our HOME directory from any folder in our system. We are using *echo* command for that, with one of the default variables of your system: $HOME.
```console
SystemName:Folder3_1$ echo $HOME
/Users/username
```
We can also use *echo* command to print strings directly to our command line, like this:
```console
SystemName:Folder3_1$ echo 'Hello, world.'
Hello, world.
```
Of course! A tutorial about any programming language is not a good tutorial unless it has the print(**Hello, world.**) on it.

## Command Make Directory (mkdir):
You have learnt how to use three *Bash* commands so far, but let's learn yet another useful command, the command *mkdir*. This command is used to make directories (a fancy word for folders) in your current directory.
I want to create a new folder (Folder4) in my HOME directory. Can you help me with that?
Let's go back to our home directory first by using what we have already learnt so we can create our new folder there using the *mkdir* command.
```console
SystemName:Folder3_1$ cd
SystemName:~ username$ mkdir Folder4
```
Great! You've made it! Now, let's try to create the folders Folder4_1 and Folder4_2 inside of the new Folder4 you just created!
We can create more than one folder at the same time in the same directory in the following way with the *mkdir* command, but we need to go to our Folder4 first.
```console
SystemName:~ username$ cd Folder4
```
Once we are in Folder4, we can create Folder4_1 and Folder4_2 at the same time with the following syntax:
```console
SystemName:Folder4$ mkdir Folder4_1 Folder4_2
```
As you can see, we just need to provide the names of the folders we want to create separated by a Space in order to do it. Easy peasy!

## Command List Files (ls):
The command *ls* is used to explore the folders and files we have in the current directory. Its default use will return all the folders and files inside of the current directory, except for the **hidden files**. By now, we won't pay attention to what these hidden files are, but they are really important for our system to run correctly and all of their names start with a ".". So better let's not mess with them for now.

In order to explore our files and folders in the current directory we write *ls* and press Enter:
```console
SystemName:Folder4$ ls
Folder4_1 Folder4_2
```
As you can see, this command is giving you a list of the contents of your folder. Probably in your terminal your folders will be displayed in blue. The default colour of folders, files and executable files are blue, white (if your console is in dark mode) or black (if it is in light mode), and green respectively.

We can use the *ls* command with arguments to get more information about the files and folders in our current directory.
These are some of the most useful, depending on what you want:

* -a: Displays all files and directories, including hidden ones that start with a dot (.)
* -l: Displays the files and directories in a long format that includes additional information such as permissions, owner, group, size, and modification date
* -h: Makes the sizes of files and directories human-readable, showing them in units such as kilobytes (KB), megabytes (MB), and gigabytes (GB)
* -S: Sorts the files and directories by size, from largest to smallest
* -t: Sorts the files and directories by modification time, with the most recently modified files and directories displayed first
* -r: Reverses the order of sorting, displaying the files and directories in reverse order
* -R: Displays the files and directories recursively, including all subdirectories and their contents

We can write these arguments in two different ways.
Imagine we want *ls* to display the information in long format, with the sizes being human-readable and with the files sorted by modification time. We will use then the following arguments: -l, -h, -t.
```console
SystemName:Folder4$ ls -l -h -t
total 0
drwxr-xr-x  2 username  staff    64B May 10 12:30 Folder4_2
drwxr-xr-x  2 username  staff    64B May 10 12:30 Folder4_1
```
We can also write it like this:
```console
SystemName:Folder4$ ls -lht
total 0
drwxr-xr-x  2 username  staff    64B May 10 12:30 Folder4_2
drwxr-xr-x  2 username  staff    64B May 10 12:30 Folder4_1
```

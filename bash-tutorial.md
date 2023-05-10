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

```bash
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

```bash
System:~ username$ cd Folder3/Folder3_1
```
After executing the command we will see the following in our console, indicating the folder we are in:
```bash
SystemName:~ username$ cd Folder3/Folder3_1
SystemName:Folder3_1$ 
```

### 3. cd ..
What if we want to go back to the parent folder of the one we are in? In our example, the parent folder of the *Folder3_1* is **Folder3**.
```bash
SystemName:Folder3_1$ cd ..
```
After executing the command we will see the following in our console:
```bash
SystemName:Folder3_1$ cd ..
SystemName:Folder3$ 
```
We can also concatenate the use of this command if we want. Let's go to Folder3_1 again.
```bash
SystemName:~ username$ cd Folder3_1
SystemName:Folder3_1$ 
```
Now, imagine we want to go to the HOME Folder from here (Folder3_1).
Apart from doing it the way we already know, by typing *cd*, we can also do the following:
```bash
SystemName:Folder3_1$ cd ../..
```
After executing the command we will see the following in our console, indicating we are back in our Working Directory:
```bash
SystemName:Folder3_1$ cd ../..
SystemName:~ username$ 
```

## Command Print Working Directory (pwd):
We have spoken about the Working Directory in the previous section, but... How do I know its PATH? Fortunately we have the *pwd* command for that.
```bash
SystemName:~ username$ pwd
```
After writing this command and pressing Enter, the **full path** of your Current Working Directory will be printed in the console.
```bash
SystemName:~ username$ pwd
/Users/username/
```
If we are working in a different folder though, the *pwd* command will show the full path of the directory you are currently working at. So, let's go back to Folder3_1 so we can try it.
```bash
SystemName:~ username$ cd Folder3/Folder3_1
SystemName:Folder3_1$ pwd
/Users/username/Folder3/Folder3_1
```
As you can see, now the print working directory command returns the full path of the folder we are currently in.
But, what if I want to know the full path of my HOME directory from any folder? We can do this by using the next command in our list: *echo*.

## Command ECHO (echo):
The *echo* command is one of the most used in shell scripts and consoles in *Bash*. Its function is to print in the console a line or a string.
If you don't know what a string is, let's keep it simple. A string is a group of characters. ("Hello" is a string).

Let's go back to how to print the path of our HOME directory from any folder in our system. We are using *echo* command for that, with one of the default variables of your system: $HOME.
```bash
SystemName:Folder3_1$ echo $HOME
/Users/username
```

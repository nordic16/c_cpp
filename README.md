# c_cpp
A simple shell script to create a regular C++ project file structure.

# Installation.

### Step 1: Determine whether you have a `bin` folder in your home directory (~)
A great feature of Linux is that you can make your own commands!
<br>In order to create your own commands and keep them organized, we need to create a folder in our home directory containing them, and have it added to `PATH` (an environment variable that tells the shell where to look for executable files).

### Step 2: Setting up the `bin` folder.
If you already have one (you can check by typing the command `ls -a ~ | grep bin`), skip to step 3.

#### Step 2.1 - Creating the `bin` folder
You can create the `bin` folder by typing the following command `mkdir ~/bin`.
<br>Now, we need to export the folder to our `PATH` so that all your scripts within ~/bin are recognized as commands. This process depends a lot on the shell you're using, so **BE CAREFUL**.

#### Step 2.2 - Adding the folder to `PATH`
As it was explained before, `PATH` is an environment variable that tells our shell where to look for our commands.
<br>By default, `PATH` is already set to a list of several folders, as it can be seen by typing the command `echo $PATH`, where each folder is separated from the other by a `:`.

Before adding `bin` to `PATH`, we need to know which shell we're using (bash is the most frequent, but there are others such as zsh, ksh, etc.). To do that, all we have to do is type `echo $0` in   which will output something like `usr/bin/zsh` (you're using zsh) or `usr/bin/bash` (you're using bash). 
<br>For the sake of simplicity, I'm only going to show how to accomplish this with bash and zsh.

**bash:** Open `~/.bash_profile` (aka `~/.profile`) and type the following line: `export PATH=$PATH:~/bin`.
<br>**zsh:** Open `~/.zshenv` and type the same line as above.

The command we used appends the `~/bin` folder to `PATH`, separating it from the others with `:`. For more information, check out [this](https://www.shellscript.sh/variables1.html) tutorial on variables in shell.

Open a new terminal and type the command `c_cpp test` - it should create the project structure for a project called "test"!


# Usage
Go to the directory where you want your project to be stored and type the command `c_cpp test`, then `ls` - You should see a directory called test.
<br>c_cpp uses the following project structure:
```
Project_name
  |
  |---- CMakeLists.txt
  |
  |---- include
  |       |
  |       |---- Project_name
  |                 |
  |                 |---- public_header(s).h
  ---- src
  |     |
  |     |---- private_header(s).h
  |     |
  |     |---- code(s).cpp
  |---- libs
  |       |
  |       |---- A
  |       |
  |       |---- B
  |---- tests
```

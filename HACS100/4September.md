# HACS 100
### Wed. September 4th, 2019
---

# Directory structure

* Like a tree
* One root directory (named `/`)
* Each user has one home
    - Current user's home is referenced with `~`
    - Other user's homes are like `~loginID`
* Current Working Directory -- current "location"
    - Referenced with the name `.` (usually the default though)
* Every directory (besides root) has a __parent__
    - Referenced with the name `..`
* Reference a __child__ using its name
    - Children names must be _unique_ within the directory
    - File/directory names are 256 character max.
    - Any name with special characters (e.g. spaces) in it must be surrounded by __quotes__ (`~/"Like This"`)
    - Usually directories start with an uppercase letter and files start with a lowercase letter

---
## Commands

* `pwd` (print working directory) -- view the current working directory
* `cd [directory]` (change directory) -- navigate the tree
    - _With_ argument: sets the current working directory to that argument
    - _Without_ argument: uses `~`
* `ls` (list) -- display all children of the current working directory
    - Pass argument to view a different directory than the current working directory
    - `-a`: Show "hidden" children (children whose names start with `.` are hidden normally)
    - `-F`: Displays a character after each child representing its type (none for directory, `@` for file, `*` for symbolic link)
    - `-l`: Shows more info about each child
* `touch [filename]` --  creates a new file in the current working directory
* `cat > [filename]` (concatenate) -- creates a new file from user input
    - Use `^D` to stop inputting
* `more [filename]` -- display file contents
    - `less` and `cat` are related
* `rm [filename]` (remove) -- deletes a file (permanently!)

---
## vim - Visual Text Editor

* Files are all stored in ASCII
* Always in one of three __modes__
    - _insert_ mode -- inserts letters when typed
        * Press Escape to go into command mode
    - _command_ mode -- executes commands when keys are typed
    - _last line_ mode -- only edit the last line


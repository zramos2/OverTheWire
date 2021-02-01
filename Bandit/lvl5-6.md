The password is in a file somewhere in **inhere** directory.\
You need to look for the right file with properties:
- human-readable
- 1033 bytes in size
- not executable

A lot of folders labeled as **maybehere**.  Each **maybehere** folder contains a random files with different aspects to them.\
We are trying to find the file that meets the properties of this level.  Such as:
- human-readable
- 1033 bytes in size
- not executable

We need to run a specific search.  Most of the files are readable text but there is only  1 file has **1033** bytes.\
You can use `find . -size 1033c` to find the place of where its located and find the password that way.\
Or you can look up the exact properties and use `cat` to get the password. Like so:\
`find . -type f -size 1033c -exec cat {} \;`

The password for level 6:
`DXjZPULLxYr17uwoI01bNLQbtFemEgo7`

#### Lets break this down and understand how to use the `find` command 
- `.` to indicate the current path you are on
- `-type f` => to indicate the folder
    - `f` : regular file
    - `d` : directory
    - `l` : symbolic link
    - `c` : character devices
- `-size 1033c` => to indicate to find a file by size.  In this case find files with 1033 bytes inside.
    - we chose **1033** as the byte size because lvl 5-6 hints gave us that amount.
- `-exec cat {} \;`  => `find` will execute `cat` and will substitue `{}` with the filenames found. 
    - you can also do `find . -type f -size 1033c -exec cat {}  +`
    - The difference between `;` and `+` is that with `;`, a single `cat` command for each file is exectued whereas with `+` as many files as possible are given as parameters to `cat` at once. [source](https://unix.stackexchange.com/questions/12902/how-to-run-find-exec)
    - use [this](https://linuxaria.com/howto/linux-shell-how-to-use-the-exec-option-in-find-with-examples) for further info on `-exec` with the `find` command


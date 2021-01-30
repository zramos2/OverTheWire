The password is in a file somewhere in **inhere** directory.\
You need to look for the right file with properties:
- human-readable
- 1033 bytes in size
- not executable


`find . -type f -size 1033c -exec cat {} \;`

### Lets break this down and understand how to use the `find` command 
- `.` to indicate the current path you are on
- `-type f` => to indicate the folder
    - f : regular file
    - d : directory
    - l : symbolic link
    - c : character devices
- `-size 1033c` => to indicate to find a file by size.  In this case find files with 1033 bytes inside.
    - we chose **1033** as the byte size because lvl 5-6 hints gave us that amount.

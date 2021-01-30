The password is in a file somewhere in **inhere** directory.

```
find . -type f -size 1033c
```  

`.` to indicate the current path you are on\
`-type f` => to indicate the folder\
`-size 1033c` => to indicate to find a file by size.  In this case find files with 1033 bytes inside.\
- we chose 1033 as the byte size because lvl 5 hints gave us that amount.

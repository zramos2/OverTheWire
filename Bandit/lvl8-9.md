The password for the next level is stored in the **data.txt** file.  The password is the only line of text that occurs once in the file.

If you `cat data.txt`, you'll see that it's a bunch of random passwords.\
If you use `uniq data.txt`, for some reason it still outputs random passwords.  `uniq` is supposed to omit repeated lines.  If you look at the **man pages** for `uniq`, the description says: **filter adjacent matching lines**. This means that all the ones that are the same have to be put together.

This is where we'll use the `sort` command.\
Type `sort data.txt` and you'll see that the output is all the repeated lines are grouped and matched together.\
Now type `sort data.txt | uniq` and it filters out all the repeating lines. However, this **does NOT** mean that the lines occur once.  It only filters out the repeating lines.  

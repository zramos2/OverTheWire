`find . -size 33c -user bandit7 -group bandit6`

You get different results if you use:\
`find / -size 33c -user bandit7 -group bandit6`
- `.` : searches inside the current working directory
- `/` : searches for **all** files and directories
    - it means the **root** directory

Once doing the `find / -size 33c -user bandit7 -group bandit6` command you'll notice **only one** of the outputs does not say permission denied.
- `/var/lib/dpkg/info/bandit7.password` is the **one** output from the command

To be more specific on the outputs:\
`find / -size 33c -user bandit7 -group bandit6 2>/dev/null/` 
- You'll then notice `/var/lib/dpkg/info/bandit7.password` is the only thing thats outputted and looks a lot cleaner 
- Type `cat /var/lib/dpkg/info/bandit7.password` to get the password.


The password for level 7 is:\
`HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs`



#### Lets break this down and understand what `2>/dev/null/` means:
- All the *permission denied* outputs that you see are coming from **standard errors** 
- The `-` denotes for **standard input**
- **Standard output** is all the stuff you see on the screen.
- **Standard error** is similar to standard output and that you see it on the screen but it's **reserved for errors messages**
    - The number `2` indicates **standard error**
- `2>/dev/null/`
    - basically the `2>/dev/null/` translates into:
        - getting all the standard errors and redirects them into the garbage bin
    - `2` : hides all the errors.  Hides all the standard errors.
    - `>` : redirects all the errors
    - `/dev/null/` : this is similar to a garbage bin but it's a digital garbage bin

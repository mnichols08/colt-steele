# Section 04 - Getting Help

All about getting help - finding documentation...

If you seen this command or were told to run `ncal -w` how might you know what `-w` would do?

Well, that is where the `man` pages come in.
just type `man` and see

well it wants an argument so lets try
`man ncal`

Man will enter the file viewer. press `q` to exit if you want to get out of the reader.
space is a nice shortcut to scroll down an entire page

`b` can take you back and `f` can also take you forward

This is a program called LESS

so what is the `-w` in `ncal`?
lets see


to search within a LESS file, you can type `/` and then type in something to search for and find out
`-w` means we get the week number

So how do we read a synopsis?
ncal [31bhJeoSM] 
well the square brackets mean that it those options are all option and also lumped together
if there are other options seperated by brackets they must be seperated

TLDR; `man <app>` will list useful information about using commands in the terminal

User commands are only just a single part of the `man` docs

### Searching the Manual
`man -k ncal` useful for looking for a particular part of a manual
`man -k passwd` shows numerous pages mentioning passwd

### Introducing Type and Which
There are 4 main `types` of commands that can be broken into:
- Built In: These commands are part of the shell (cd)
- Executables - They are typically stored in a folder named `/bin`
- A Shell function
- An alias


`type clear` || clear is hashed (/usr/bin/clear)
`type mkdir` || mkdir is /usr/bin/mkdir
`type cd` || cd is a shell builtin
`type cow` || cow: not found (Could/should be alias but haven't shown how to make yet)

#### Which
This command declares where a command is physically located
`which clear` || /usr/bin/clear

Now we are learning about `cd`
So we go to `man` and ask for help
`man cd` || No manual entry for cd
What? well, we have another approach we can take at this stage.
lets try `help`
`help cd` returns a bunch of infomation about this page.

In general if there are not a page in the `man` program for a command, then check the `help` page instead.
Read, learn.

##### Exercise
# Getting Help Exercise

- There is a command called `whoami`.  **Before you run it**, read the manual page entry on it.  From the manual page entry, can you tell if it needs any options or arguments? What does it do?
    - Based upon what I read in the `man` page, `whoami` is a user command that takes in an optional `option`. The output is the user name associated with the current effective user ID. By providing it with a `-h` you can display help. By providing a `-v`, an output version is printed.
- Now try running it! What happens?
    - It turns out I was wrong! I have to provide the `long-form option` because this one does not accept short ones.
- There is another command called `who`.  Without turning to Google, figure out what it does! Does it require any arguments or options to run?
    - `who` is a user command to print information about users that are currently logged in
    - It does not require arguments outside of it's command name
- Use the `who` command to print out the time of the most recent system boot.  You'll need to find an option to help you do this!
    - `who -b`
    who [OPTION]... [ FILE | ARG1 ARG2 ]
    I am stumped... But in the video he does exactly what I did so I think maybe it is just not working because I have a virtual machine of Ubuntu running perhaps?
    This is the output that renders
    ```
    root@DESKTOP-1UKT1FA:~# who -l
    root@DESKTOP-1UKT1FA:~# who
    root@DESKTOP-1UKT1FA:~# who
    root@DESKTOP-1UKT1FA:~# who -l
    root@DESKTOP-1UKT1FA:~# who lb
    root@DESKTOP-1UKT1FA:~# who -lb
    root@DESKTOP-1UKT1FA:~#
```
- Run a command to figure out whether the `echo` command is a a binary, a shell-built in, or an alias.
    - `type echo` || echo is a shell builtin
- Do the same for  the `date` command
    - `type date` || date is /usr/bin/date
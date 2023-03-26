# Section 04: Getting Help

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


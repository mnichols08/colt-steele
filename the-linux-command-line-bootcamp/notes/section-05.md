# Section 05 - Navigation

## Folder structure of UNIX vs WINDOWS
on UNIX systems there is always a `root` directory at the very top level of a computer
    - not to be confused with the folder that is called `root`. We are referring here to the very top level folder of the UNIX system.
However, on a WINDOWS system, there are hard drives seperated

### Unix

#### `/home` or `~home`
There is an actual folder called `/home`
And inside of `/home` are folders for each user on the machine.
On my machine, I do not even have my own user folder yet as I am in a shell-only version perhaps?
Normally this folder would have all of a user's personal files such as a desktop, their music, documents, themse, settings, etc.

#### `/root`
The `/root` folder contains the files that are shared by users and are accessible regardless of what user is logged in

##### Shorthand `/ or ~`
The shorhand to get to the `root` is `/` where the shorhand to reference `/home` is `~`

#### Print Working Directory
> `pwd` - a command which is simple but useful. It prints the path of the current working directory starting from the root `/`
It proves to be a lot less useful if you are using a prompt where your pwd is given to you on each prompt

##### ls - the most common command
stands for list or short for lists -
simply lists the contents of a directory

We can also use `ls <path>` to cd into a folder and type ls with one command

##### Helpful ls options
- `ls -l` || the long format for each directory which inclues the owner, the group, permissions, modification date, and size
- `ls -a` || 
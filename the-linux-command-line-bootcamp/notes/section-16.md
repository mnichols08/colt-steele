# Altering Permissions
chmod
To change the permissions of a file or directory, we can use the chmod command (change mode).
To use chmod to alter permissions, we need to tell it:
- Who we are changing permission for
- What change we are making
- Which permissions are we setting

When specifying permissions with chmod, we use a special syntax to write permission statements.
First, we specify the "who" using the following values:
- `u` - user (the owner of the file)
- `g` - group (members of the group the file belongs to)
- `o` - others (the "world")
- `a` - all of the above

Next, we tell chmod "what" we are doing using the following characters:
- `-` - (minus sign) removes the permission
- `+` - (plus sign) grants the permission
- `=` - (equals sign) set a permission and removes others
Finally the "which" values are:
- `r` - the read permission
- `w` - the write permission
- `x` - the execute permission

All Together Now
Next, we tell chmod "what" we are doing using the following characters:
- `-` - (minus sign) removes the permission
- `+` - (plus sign) grants the permission
- `=` - (equals sign) set a permission and removes others
Finally the "which" values are:
- `r` - the read permission
- `w` - the write permission
- `x` - the execute permission

chmod octals
chmod also supports another way of representing permission patterns: octal numbers (base 8). Each digit is an octal number represents 3 binary digits.

Changing Our Identity
The may be times when we want to start as hell as another user, from within our own shell session.
We can use the su command to do just that.
For example, `su - hermione` would create a new login shell for the user hermione. WE would need to enter Hermione's password.
To leave the session, type exit.

Root User
In Linux systems, there is a super user called root. The root user can run any command and access any file on the machine, regardless of the file's actual owner.
The root user has tons of power and could easily damage or even destroy the stystem by running the wrong commands!
For the reason, Ubuntu locks the root user by default.

Sudo
Even if the root user is locked by default, we can still run specific commands as the root user by using the sudo command.
Individual users are granted an "allowed" list of commands they can run as the super user.
Run `sudo -l` to see the permitted commands for your particular user.

Sudo + Ubuntu
By default, Ubuntu disables logins to the root account. Instead, the initial user is granted full access to all superuser priveleges:
"User Mikey may run the following commands: "(All: ALL) ALL"
Subsequent users won't have full sudo priveleges by default, but the original user can grant them.

Sudo
To run a command as the root user, prefix it with sudo. You will need to enter the password for your account.
For example to update Ubuntu, I would need to run `apt update`. However, I cannot do this as my 'regular' user, as it is something that impacts all users.
Instead, I need to run the command as the root user using `sudo apt update`

chown
The chown command is used to change the owner and/or the group owner of a specific file or directory
To make bojack the owner of file.txt, we would run `chown bojack file.txt`

To change the owner of a file and the file group owner at once we can provide both using `chown USER: GROUP FILE`

For example, `chown bojack:horses file.txt` will change the owner of file.txt to bojack AND changes the file group owner to the group named horses.

To only change the group owner of a file, we can run `chown :GROUP FILE`
For example, `chown :horses file.txt` will change the file group owner of file.txt to the group named horses.

Groups
To view the groups that a given user belongs to, run `groups USERNAME`
For example, to see which groups hermione is part of, run `groups hermione`

Creating Groups
We can create new groups using the addgroup command.
To create a new group called friends, we would run `addgroup friends`

To add a user to a group, use the adduser command.
To add hermione to friends, we would run `adduser hermione friends`
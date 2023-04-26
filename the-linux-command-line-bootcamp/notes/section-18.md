# Bash Scripts

The Basic Steps
1. Write a script in a file and save it
2. Make the script executable using chmod
3. Verify that the shell can find your script

Shebang!
The first line of our script should read #!/bin/bash
The #! is called the shebang, and is used to tell the OS which interpreter it should use when parsing this file. We want ours to say "use bash to interpret this file!"
After the shebang, we need to include the path to the Bash binary. This is not Bash specific. If we wanted to write a python script, we wouuld include the path to the python binary.

Comments
Lines that begin wtih # will not be read by the shell. Write comments to explain particularly tricky bits of code or to leave notes for yourself.

The Good Stuff
We can write any of the commands that we normally run from the command line. When we execute the script, these commands will run!

Executing The Script
We can execute the script the "long way" by running bash pathToFile.
This works, but it is not as convenient as it could be! What if we could instead just run `hello` from anywhere on our machine, just like we can run `ls` or `grep` anywhere?!

Locating Commands
When we run a command like pwd, the shell starts looking for the executable pwd program in the list of directories stored in the PATH variable. It starts looking in the first location and then keeps looking if it does not find it.

Why It Matters
If we want the shell to find our own programs, we need to make sure we put them in a folder that is in the PATH variable.
A common place to put user-defined programs is in a bin folder located in the user's home directory. For me that would be /home/mikey/bin.
If that directory is not yet part of your path, you can add it by putting PATH="$HOME/bin:$PATH" in your `.bashrc` file

Making It Executable
The next step to making the file containing our script executable is `chmod a+x file`.
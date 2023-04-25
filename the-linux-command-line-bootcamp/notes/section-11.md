# Piping & Constructing Pipelines
The most important thing to learn in this section is what a pipeline is and how to write one.
We will learn about the tr command which is nice-to-have but will also lean about the tee command which is a little more useful but not as imporant as piping.

When it comes to piping, a command accepting standard input is really what glues everything together.
Pipes are used to redirect a stream from one program to another program. We can take the output of one command and redirect it to the input of another.

## Examples
- `ls /usr/bin/ -l | less` This tells the terminal to take the output of `ls usr/bin -l` and use it as the input for less
- `ls /usr/bin -1 | wc -l` - Takes a list of files in a folder and then pipes the output into wc with option l to count lines
- `ls /usr/bin -1 | wc -1 > count.txt` - Takes the output of `ls /usr/bin -1` and then pipes it as an input to `wc -l` and finally redirects the output of that to a file called `count.txt`
- `echo 'she sells seashells by the seashore' > msg` - redirect this phrase int oa file called msg
- `cat msg | tr s S` - reads the contents of the msg file and takes it output as an input to the tr command chaniging lowercase s to S 
- `cat data.txt | tr -d [:alpha:]` - reads the content ofa file and then passes into tr with option d to delete all uppercase or lowercase letters
- `cat data.txt | tr -d :` - removes colons
- `cat data.txt | tr -d : [:blank:]` - removes spaces and tabs
- `cat data.txt | tr -d : [:alpha:] | tr -d : | td -d [:blank:] > newdata.txt` - Chains multiple commands and redirects into a file

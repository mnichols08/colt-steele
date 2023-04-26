
# Piping & Constructing Pipelines
The most important thing to learn in this section is what a pipeline is and how to write one.
We will learn about the tr command which is nice-to-have but will also lean about the tee command which is a little more useful but not as imporant as piping.

When it comes to piping, a command accepting standard input is really what glues everything together.
Pipes are used to redirect a stream from one program to another program. We can take the output of one command and redirect it to the input of another.

## Pipe Examples
- `ls /usr/bin/ -l | less` This tells the terminal to take the output of `ls usr/bin -l` and use it as the input for less
- `ls /usr/bin -1 | wc -l` - Takes a list of files in a folder and then pipes the output into wc with option l to count lines
- `ls /usr/bin -1 | wc -1 > count.txt` - Takes the output of `ls /usr/bin -1` and then pipes it as an input to `wc -l` and finally redirects the output of that to a file called `count.txt`
- `echo 'she sells seashells by the seashore' > msg` - redirect this phrase int oa file called msg
- `cat msg | tr s S` - reads the contents of the msg file and takes it output as an input to the tr command chaniging lowercase s to S 
- `cat data.txt | tr -d [:alpha:]` - reads the content ofa file and then passes into tr with option d to delete all uppercase or lowercase letters
- `cat data.txt | tr -d :` - removes colons
- `cat data.txt | tr -d : [:blank:]` - removes spaces and tabs
- `cat data.txt | tr -d : [:alpha:] | tr -d : | td -d [:blank:] > newdata.txt` - Chains multiple commands and redirects into a file

### Tee
The tee program reads standard input and copies it both to standard output AND save it to file 
#### Example
`cat colors.txt words.txt |tee colorsAndWords.txt | wc` this takes the values of colors.txt and words.txts and combines then, then it redirects that value through a tee, which will both create a file and pass along the output to the next command in a pipeline so in this case the wc command that will return the word count.

# Piping Exercise

Download the starter files here: 

[PokemonExercise.zip](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/65520ea7-129d-4e78-9719-69bfbb7c66e0/PokemonExercise.zip)

Unzip the file.  The resulting folder contains a subfolder called `PokeDex/` which in turn contains a whole bunch of files, each named for a specific Pokemon like: [x]

```bash
PokemonExercise/
	PokeDex/
		100Voltorb
		101Electrode
	  619Mienfoo
		...
```

## Your Task

Complete the following challenges using the starter files.  Make sure that you navigate to the `PokemonExercise/` directory, **but do NOT run any of the following commands from inside the `PokeDex/`** folder.  I repeat: any files that you create for the exercise should live inside of `PokemonExercise/` NOT `PokeDex/`

- Count the number of Pokemon files in the `PokeDex/` folder.  You'll need to combine commands to make this work! [x] 718 - `echo 'The Total number of Pokemon in the PokeDex folder is' >> PokeCount.txt | ls PokeDex -1 | wc -l >> PokeCount.txt &2>> PokeErrors.log` did well =)
- Next, create a new single file called `all-pokemon.txt` in the `PokemonExercise` folder (NOT the `PokeDex` folder)that contains the LOWERCASED name of every single Pokemon file in the directory, sorted in numerical order!  The end result should look like this:  [x] `echo 'All Pokemon in sorted in alphatbetical order and lowercased: ' > all-pokemon.txt 2>> PokeErrors.log | ls Pokedex -1 2>> PokeErrors.log | tr [:upper:] [:lower:] 2>> PokeErrors.log | sort -hb >> all-pokemon.txt 2> PokeErrors.log`
However at the tail end there are some messed up Pokemon

```bash
1bulbasaur
2ivysaur
3venusaur
4charmander
5charmeleon
6charizard
7squirtle
8wartortle
9blastoise
10caterpie
11metapod
12butterfree
...
```

- Now that we have this file that includes all the Pokemon in numerical order, let's print out the three pigeon-related Pokemon: pidgey, pidgeotto, and pidgeot.  Using the command-line, print out lines 16-18.  It should look like this:
[x] - ` echo 'Pigeon related Pokemon' > PidgeMon.txt 2>> PokeErrors.log | sed -n '16,18p' all-pokemon.txt >> PidgeMon.txt 2> PokeErrors.log`
^ This no longer works because of the next command but, we can leverage this command learned later on in the course - `grep -rA2 "pidgey" PokemonExercise/`
```bash
16pidgey
17pidgeotto
18pidgeot
```

- Next, up let's isolate the original 151 Pokemon.  Using a single pipeline...
    - output the first 151 lines of the `all-pokemon.txt` file
    - remove all digits 0-9 from the lines (using `tr` )
    - sort the now number-less lines alphabetically
    - store the new result in a file called `original-151.txt` in `PokemonExercise`
    [x] - `echo 'Original 151 Pokemon:' > original-151.txt 2>> PokeErrors.log | sed -n '2,144p' all-pokemon.txt |tr -d [:digit:] | sort >> original-151.txt 2> PokeErrors.log`
    ```bash
    abra
    aerodactyl
    alakazam
    ...
    wigglytuff
    zapdos
    zubat
    ```


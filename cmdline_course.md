---
layout: default
---

## Introduction

This course on command-line tools covered various different topics and methods for using the command-line environment. On this page I will briefly describe and 
illustrate each week's topic, leading up to the final assignment of working with Jekyll and GitHub pages.

## Week 1

The first week of the course served as the introduction to working with command-line environments, and the work included setting up a working command-line environment 
on my device. For me this meant installing Ubuntu on my Windows computer, and learning to use it.

The commands I learned to use this week include things like the `cd` and `ls` commands for moving between directories and listing their contents, as well as `wget`
for downloading things from the internet into my directory. These and other basic commands I learned during this week have been very useful in my work throughout the 
course, and over time I have managed to acquire a great `touch` for using them. (Pun intended).

## Week 2

This week's content was centered around navigating a UNIX system and managing files and directories within that system. I also learned to connect to a remote server
and change the access rights to a file.

The commands I learned this week that I found myself using the most in the coming weeks and assignments were  
* `cp` for copying files
* `mv` for moving files between directories
* `rm` for deleting files and directories
* `tar` for extracting .tgz files

These commands were needed often in the later weeks' assignments, and they are obviously commands that are very essential to doing any work with command-line environments.
I familiarized myself with these commands and learned to use them quickly and naturally.

## Week 3

During the third week I learned about different text encoding systems, converting from one text file format to another (Windows vs. UNIX), and the basics of corpus processing
with command-line tools. Some of the relevant commands from this week's material are tabled below:

Command | Function  
--- | ---  
`file` | Finding out the file type of a file, for example ASCII text  
`wc` | Figuring out the number of lines, words and characters in a file  
`iconv` | Converting text files from one encoding to another  
`dos2unix` | Converting from Windows text file to UNIX text file  
`unix2dos` | Converting from UNIX text file to Windows text file  

## Week 4

The fourth week's material went deeper into the world of corpus processing, and I learned about things such as using `sed` and regular expressions for editing text files.
Additionally I learned to use text processing pipelines to execute multiple processes back to back with one command-line input line. For example, a combination of
commands such as `cat example_file.txt | tr -s '\n\r\t ' '\n' |  
tr -dc "A-Za-z0-9\n'" | sort | uniq -c |  
sort -nr > example_file.freq.txt`  
would do the following:
1. Bring out the text file example_file.txt for processing purposes
2. Turn the document into a one-word-per-line format by replacing all whitespace characters with linebreaks, with multiple consecutive whitespaces being turned into only one linebreak
3. Delete everything that isn't a letter, a number, a linebreak or an apostrophe in order to get rid of the punctuation marks
4. Alphabetize the list
5. Count the consecutive lines with the same word in them, showing the frequency number next to the word
6. Sort the list into a descending numerical order, i.e. showing the words in order of most to least frequent
7. Direct the output into a new file called example_file.freq.txt  

This is how one can create a frequency list of the words appearing in a text file by piping multiple commands together and thus saving time and manual effort.

## Week 5

Week 5 was definitely the most difficult week of the course for me. We learned about using and writing script files, and I faced some significant struggles in fully understanding how 
they work and being able to write correct scripts that do what they are supposed to. I found the other topic of the week - configuration files - considerably easier, and managed 
to manipulate my .bashrc file and create a unique command line prompt:  

![My personal command-line prompt with a little heart emoticon](https://cdn.discordapp.com/attachments/820653333299068949/914275128710410282/unknown.png) 

This command-line prompt was created by editing the .bashrc file in my directory and changing the value of the environment variable `PS1`. I wanted my prompt to show my username and 
current directory path on the upper line so I can keep track of where I am working, and below it I put the name of my host followed by a small heart symbol just for the fun of it.
Therefore the PS1-line in my .bashrc file looks like this: `export PS1="\n${CYAN}\u\w\n\h <3 ${COLOR_NONE}"`, where `${CYAN}` first sets the prompt's color as cyan (based on a value
table I copypasted into the file from a lecture script), then `\u` determines that the first thing shown on the prompt is my username. The username is followed by the current working
path, as determined by `\w`, after which there is a line break and then `\h`, which stands for the current host. After that comes the heart, and the last part ensures that whatever 
I write as a command after the prompt will not be written in any special color.

## Week 6

The sixth week's topic was program installation and then running those programs. I learned about package managing programs and how different programs have different dependencies 
that are installed the easiest through such package managers. I also learned to use `sudo` to give commands as the root user, as well as to write and run Makefiles.

The package managers I used in my work are apt-get and pip (for python packages). I found them fairly easy to use, especially since I had used apt-get multiple times before for 
various tasks on the course, although I was of course not quite as familiar with all its functionalities back then.

Learning about and using Makefiles turned out to be interesting as well. Knowing I'd struggled with scripts the week prior, I was a little intimidated by having to learn a tool for
building other programs. The tasks turned out quite challenging indeed, and I was not able to complete them all with the success I'd hoped for. However, I still managed to learn the
basic syntax of Makefiles:

`target: prerequisites
	recipe` 

Where `target` functions like a function name in programming, `prerequisites` refers to the files or other targets that are used by the `recipe` to create the target. The `recipe`
itself is a chunk of "instruction code" that the program follows when executing the Makefile in order to create the desires target.

## Week 7

The topic for this week was version control, and I learned to use GitHub repositories to work on projects remotely. I found this part maybe the most interesting out of the whole course, 
and working with GitHub was very pleasant. Learning to use and understand the functions of commands like `git add`, `git commit`, and `git push` was obviously the most integral part of
this week's material, and especially the "understanding the functions of" part was not quite as simple. As a newbie to any kind of version control mechanisms, I had little to no 
intuition for how commands such as those work, but after some reading I was able to understand the difference between "committing" and "pushing" the changes I'd made to the contents of
my repository. Additionally, I found the functionalities of Git branches very interesting.

## Week 8

The last part of the course was to work on this very webpage, both its content and formatting. I learned to use GitHub Pages and Jekyll in order to create everything you've just
been reading and looking at, and I found the process extremely fascinating and fun. I struggled somewhat with certain Jekyll commands, but I feel confident I was able to sort out
all the issues. 

## Week 2 Notes

* Multiple uses of / is as good as one
  - ie : cd ///////usr//////bin will take you to /usr/bin
* The root folder / is its own parent
  - ie : if you do cd .. within the root directory you stay in the same directory.
* Options / Flags can be written in multiple combinations
  - ls -l level1 -di
  - ls -d level1 -il
  - ls level1 -ldi
  - ls -ldi level1
 * long formats for options are also available
  - ls -a is equivalen to ls --all


### Commands
* ls
  - R flag lists all subdirectories recursively 
  - Passing directory name to ls shows what is within that directory. ie : ls -l level1 
  - d flag displays details of a folder without traversing inside it. it : ls -ld level1 
  - 
* ll
  - a shortcut for the ls -la command
* which
  - which *command* will show the location of the command
  - which less will show usr/bin/less
* whatis
  - gives a brief description of the command
* alias 
  - give a nickname to a frequently used command
  - usage : alias ll = 'ls -l'
  - Just typing alias will show a list of aliases
* unalias 
  - used to remove an alias
* rmdir
  - removes an empty directory

### Commands to know contents of a text file

* less
  - displays the content in one screen
  - ls -l /usr/bin/less shows that the command takes 180KB
* wc
  - prints newline,word and byte counts for the file
  - the -l flag shows just the number of lines
* head
  - head profile displays the first ten lines
  - use -n flag to specify the number of lines
* tail
  - tail profile displays the last ten lines
  - use -n flag to specify number of lines to be displayed
* cat
  - in /etc , cat profile would just dump contents on the screen without any further prompts.
  - disadvantages : cant move back and forth to view page by page, can't come out half way through.
  - if the file is very long cat is not the best way to look at the content.
* more
  - similar to less. Allows page by page viewing
  - ls -l /usr/bin/more shows that the command takes 43KB

### Knowing more commands
* man
* which
* apropos
  - For a keyword it shows you all the commands which have that keyword in the description
  - Used to discover new commands
  - IF you type ls -l /usr/bin/apropos you see that it is a symbolic link to whatis, but the outputs are different : Why?
  - Reason : In Linux every executable will know in what name it has been invoked - can have different behaviour depending on the name that invoked it.
  - It also has the same output as *man -k* : Searching for a keyword
* info
  - Allows browsing through commands using the cursor 
  - Can go back using *<* or 'shift'+','
* whatis
* help
  - displays keywords reserved for the shell being run
* type
  - displays what type of command it is 
  - type type shows that it is a 'shell built in' being offered from the shell and not the os
  - type ls shows that it is aliased with some option. which ls shows that it is coming from os because there is an executable available.
 ### Multiple Arguments
 * ##### Recap : Arguments and Options
  - Options are enhanced features of the command
  - Arguments are specific names of files or directories 
 * Second arrument behaviour and interpratation of last argument should be seen in the man pages
 * Recursion is assumed for *mv* and not *cp*
  - recursion is assumed for some commands and should be explicitly stated in others
 * *touch file1 file2 file3* creates all 3 files in one go with identical timestamp.
 * 
## Week 2.3 Notes

### Creating a variable
  - cant start with a number
  - no space around = sign
  - RHS -> number,command or string
* Exporting a variable -> making a variable available for a shell spawned by the current shell.
  - `export myvar="value string"` or `myvar="value string";export myvar`
### Using variable values
  * `echo $myvar` or `${myvar}` or `echo "${myvar}_something"`
  * `unset myvar` -> removing a variable
  * `myvar=` -> removing the value of variable
  #### Test if a variable is not set
  * `[[ -v myvar ]];
  * echo $`
  * 




* Options / Flags can be written in multiple combinations
  - `ls -l level1 -di`
  - `ls -d level1 -il`
  - `ls level1 -ldi`
  - `ls -ldi level1`
 * long formats for options are also available
  - `ls -a` is equivalent to `ls --all`


### Commands
* `ls`
  - R flag lists all subdirectories recursively 
  - Passing directory name to ls shows what is within that directory. ie : ls -l level1 
  - d flag displays details of a folder without traversing inside it. it : ls -ld level1 
  - 

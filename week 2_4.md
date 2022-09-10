- `printenv` or `env` -> gives all the variables
- `echo ${#mydate}` gives the number of characters in the variable
- `date +"%d %B %Y"` -> date month year
### pattern matching
  - `myvar=filename.txt.jpg`
  - `echo ${myvar#*.}` -> txt.jpg not matched will be printed.ie all after the first match
  - `echo ${myvar##*.}` -> jpg -> all after the last match.
  -   `echo ${myvar%.*}` -> filename.txt -> only the matched will be printed
  -   `echo ${myvar%%.*}` -> filename
  -   `echo ${myvar%%.*}.${myvar##*.}` -> filename.jpg
#### replacement
  - `echo ${myvar/e/E}` -> the first small e will be changed to capital E
  - `echo ${myvar//e/E}` -> replace everywhere.
  - `echo ${myvar/#M/m}` -> M at the start change to m. # means that only if it occurs at the start change else dont
  - `echo ${myvar/%g/G}` -> end of the string change.
  - `echo ${myvar/%jpeg/jpg}` 
  - `` myvar1=`echo ${myvar//jpeg/jpg}` ``-> replace the jpeg to jpg in myvar and stores it in myvar1
  - `echo ${mydate#*day}` -> knocks off only sunday and prints the rest
  - ` echo ${mydate,}` -> only first letter changed to lower case
  - `echo ${mydate,,}`-> all the character to lower case
  - `echo ${mydate^}` -> starting letter to caps
  - `echo ${myvar^^}` -> all the string to caps
* `man declare`  -> wont come because its not something
* `help declare` -> its a shell builtin hence its executed
* `type declare` -> shell builtin
  - `declare -i mynum` -> restrict thevalue of mynum to be integers
      - if we declare string it will take 0 as value.

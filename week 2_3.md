## Week 2.3 Notes

### Creating a variable
  - cant start with a number
  - no space around = sign
  - RHS -> number,command or string
* Exporting a variable -> making a variable available for a shell spawned by the current shell.
  - `export myvar="value string"` or `myvar="value string";export myvar`
### Using variable values
  * `echo $myvar` or `${myvar}` or `echo "${myvar}_something"`
  * we can override the previously set variable value by assigning it again.
  * `myvar = 10` -> is not a valid assign because of the space.
  * `myvar=hello world` -> command not found: `echo $?` -> 127-> cmd not found.
  *`myvar="hello world"` -> correct way to assign 
  * `unset myvar` -> removing a variable
  * `myvar=` -> removing the value of variable
  #### Test if a variable is not set
  * `true` `echo $?` -> 0 -> true
  * `false` `echo $?` -> 1 false
  * `[[ -v myvar ]];echo $?` 0->success, myvar is set,1-> failure myvar is not set.
  * `[[ -z ${myvar+x}]];echo $?` 0-> my var is not set,1-> failure : myvar is set,`x` any string used as replacement in case var is not set
  * `myvar=Filename`
  * `echo "$myvar.txt"`-> gives filename.txt
  * `echo $myvar_txt"` -> wont come
  * `echo "${myvar}_txt" -> filename_txt
  * `echo ${myvar} -> filename
  * `bash` -> opens a bash environment
  * `ps --forest`
  * `echo $myvar` -> it wont be present in inner shell
  * `exit` -> goes back to parent shell
  * `export myvar=3.14` -> will be present in subshell also.
  * when a variable is exported,it will be present in subshell,but upon modifying the value in sub shell the modification wont reflect in parent shell.Even we export in the child shell it wont affect the value in parent shell.
  * `` mydate=`date` ``-> stores output of cmd as the value of the variable
  * `` mydate=`echo Sunday that is today` `` -> 
  * `echo ${myvar:-"default"}` -> get or use "default" as a message , '-'(minus) means if the value is not present what to do
  * `echo ${myvar:="default"}` ->  get or set "default" as its value
    - `echo ${myvar:-"myvar is not set"}` -> print if the value is not set 
  * `echo ${myvar:+"default"}` ->if myvar is set:,print "default" as its new output.else display nothing.
  * `echo ${myvar:?"myvar is not set"}` more details on the variable, i.e : bash shell,variable name and the value will be displayed. 
  * `echo ${!H*}` -> list of shell variables that start with H.
  * `echo ${#myvar}` -> length of the string if variable is set, else 0
  * `echo ${myvar:5:4}` -> offset and slice length.if slice is larger than the remaining,then what is left will be printed
  *`echo ${myvar: -2:2} -> start from -ve 2 index.NOTE: a space after : is required to differentiate from  the previous commands.
  * `echo $myvar`
  ### remove matching pattern
  *`echo ${myvar#pattern}` -> match once
  * `echo ${myvar##pattern}`-> max match possible
  ### keep matching pattern
    *`echo ${myvar%pattern}`
    *`echo ${myvar%%pattern}` 
  ### replace matching pattern
    * `echo ${myvar/pattern/string} -> match once and replace with string.
    * `echo ${myvar//pattern/string} -> match max possible and replace with string .
    * `echo ${myvar/#pattern/string}` -> match at beginning and replace with string
    * `echo ${myvar/%pattern/string}` -> match at end and replace with string
 ### Changing case:
  - `echo ${myvar,}` -> change first char to lower case
  - `echo ${myvar,,}` -> change all charcater to lower case
  - `echo ${myvar^}` -> change first char to upper case
  - `echo ${myvar^^}` -> change all chars to upper case
 ### Restricting value types
 -  `declare -i myvar` -> only integers
    * -l -> lower case -> if we give caps it will convert to lower case and store
    * -u  -> upper case
    * -r -> variable is read only,cant modify it.so start bash again to forget it.we can declare a variable and then also we can set it readonly
 -  `declare +i myvar` -> integer restriction removed.
    * +l -> lowercase restriction removed
    * +u -> uppercase restriction removed
    * +r -> NOTE : cant do once it is readonly
   
 ### indexed array 
 index need not be continuous
  -  `declare -a arr` -> declare arr as an indexed array
  -   `arr[0]=Sunday`
  -   `arr[1]=Monday`
  -  `$arr[0]="value"` -> set value of element with index 0 in the array
  -   `echo ${arr[0]}` -> value of element with index 0 in the array
  -   `echo ${#arr[@]}` ->number of elements in the array
  -   `echo ${!arr[@]}` -> display all the indices used
  -   `echo ${arr[@]}` -> dislpay all the values of the elements of the array
  -   `unset 'arr[2]'` -> delete element with index 2 in the array
  -   `arr+=("value")` -> append an element with a value to the end of the array
  -   `arr=(Sunday Monday Tuesday Wednesday Thursday Friday Saturday)` -> declare an array.with indices in order.
  
  ### associative arrays
  
   - `declare -A hash` -> declare hash as an associative array
   -  `hash[0]="Amal"`
   -  `hash[1]="Bimal"`
   -  'hash["mm12b001"]="Charlie"`
   -  `$hash["a"]="value"` -> set value of element with index "a" in the array.

Shell variable manipulations are fast.
  -   `` myfiles=(`ls`) ``
  -   `echo ${#myfiles[@]} ` -> count of files or folders in the folder
  -   `echo ${!myfiles[@]}` -> indexes if the array


    
     
  




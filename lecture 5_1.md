### Shell Script arguments
* `./myscript.sh -l arg2 -v arg4`
* `$0` -> name of the shell program
* `$#` -> no of arguments passed
* `$1` or `${1}` first argument
*  `${11}` -> eleventh argument
*  `$*` or `$@` -> all arguments at once
*  `"$*"` all argument as a single string
*  `"$@"` all argument as separate strings

#### command substitution
* ````var=command````
* `var=$(command)` -> command is executed and output is substituted.
* ```for var in list do commands done```
*  case var in \
   pattern1) \
   &nbsp;&nbsp; commands \
   &nbsp;&nbsp; ;; \
   pattern2) \
   &nbsp&nbsp;; commands \
    &nbsp;&nbsp; ;; \
   esac
   * -> case reverse is esac
   * if loop
   * ` if condition then commands fi` or 
   * `if condition;then commands fi`
   *  `test -e file` -> test if file exists
   *  `[ -e file ] -> same as above
   *  `[[ exprn ]]` eg: `[[ $ver == 5.*]]` => for regular expression and etc,, 
   *  `(( exprn ))` eg: `(( $v ** 2 > 10 ))` => 
   *  ` wc -l file `
   *  pipeline `who|grep "joy" >/dev/null`
   *  `!` for negation of the condition.
* `until condition do commands` -> loops continues until condition becomes true

`my func() { commands }` call `myfunc`-> definitions must be before call.

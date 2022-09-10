### Linux process management

  - `coproc` and `declare` ,`fg`,`jobs` are shell builtins.use `help` with these
  - `echo $-` -> himBHs -> 'H' means command can be executed from history using !n
  - `wc -l /etc/profile` -> no of lines in the file
  - ` echo $?` - returns the exitcode of the previously executed command 0-> success ; 1-256 -> failures
  - 2-> no such directory or file
  - 1 -> permission denied
  - 126 -> file could not be executed.
  - 127 -> command not found (daet).
  - 130 -> ctrl+c
  - 137 -> `kill -9 pid` killed from another shell with -9
  - `bc` -> bench calculator (4567%256) -> ctrl+d to come out.

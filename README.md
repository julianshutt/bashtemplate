# bashtemplate
Use this bash template for clean output and better error handling.

Output example:
<p align="center">
  <img src="https://s18.directupload.net/images/190518/92au6td4.png">
</p>

There are the following output classes: info, warn, success, debug and error.
The classes are structured as follows (info function as example):
```bash
info() {
  local _date
  _date=$(date +%d-%H.%M)
  echo -e "[$_date][INFO]: $1 "
} 
```

So you can easily filter the output your script produces.
Example usage (also the code behind the example screenshot):
```bash
info " I am some random Info."
warn "This is not normal!"
suc "Finished without errors!"
debug "I'm some info just for the devs!"
err "Error, exiting now!"
```

In addition, some functions have more features than just clean output.
### Debug function
The debug() funktion will only show up if boolean 'is_debug' is true. This is made by the -d parameter. So Devs can just execute the script with -d to view all debug messages.
```bash
$ bash /usr/local/bin/script.sh -d
```
### Error function
The err() funktion redirects the Message to STDERR, 
starts the cleanup function and then exits.
You can call err() with "1" as argument to show the help before exiting.
```bash
err "Please use parameter." 1
```

## Changing Colors
Just change the color pallet values at the top of the script as you whish.
```bash
readonly cf="\\033[0m"
readonly red="\\033[0;31m"
readonly green="\\033[0;32m"
readonly yellow="\\033[0;33m"
readonly purple="\\033[0;35m"
```

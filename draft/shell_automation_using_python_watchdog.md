# Shell Automation using Watchdog (Python)

- `pip install watchdog`
- run using `watchmedo`

for my case, it's very useful when i want to *autorun* artisan command, phpunit, and basic shell. 

below code is example of using `watchmedo` command to run `echo 'something changed'` everytime any php file is changed in the directory where `watchmedo` is executed.

```sh
# eg. `watch-sh '*.php' 'say ha'`
watch-sh () {
    COMMAND=$2
    PATTERN=$1
   
    echo "Watching changes on '$PATTERN' to trigger '$COMMAND'.\nPress ctrl+c to exit."

    eval "watchmedo shell-command \
      --patterns='$PATTERN' \
      --recursive \
      --command='$COMMAND' \
      ."
}

```
> see more bash snippet in https://github.com/wzulfikar/lab/tree/master/bash

# solution EX6. 
#!/bin/bash

if (( $# < 3 )); then
    >&2 echo "Illegal number of parameters"
    exit 2
fi

echo Got $# Variables
x=0
 for i in $*; do 
    x=$((x+1))
    size=$(du -s $i | grep -Eo "^[0-9]*")
    if [ $x = $# ]; then
    echo Done Bye Bye
    echo Total Bytes: $sizeall
    exit 1
    fi
    cp -rf $i "${@: -1}"
    sizeall=$((sizeall+size))
 done

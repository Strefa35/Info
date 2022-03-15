# Links:
    http://manpages.ubuntu.com/manpages/focal/man5/core.5.html

## Checks ulimit
    ulimit -c

## Set ulimit to unlimited
    ulimit -c unlimited 
    ulimit -a 

##
    cat /proc/sys/kernel/core_pattern
    
    
## Build C++ program
    g++ -Wall -g program.cpp
    
## Run GDB
    gdb <executable-file> <core-file>
    
    

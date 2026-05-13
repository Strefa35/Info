# Coredump

Reference: <http://manpages.ubuntu.com/manpages/focal/man5/core.5.html>

## Check ulimit

```bash
ulimit -c
ulimit -a
```

## Set ulimit to unlimited

```bash
ulimit -c unlimited
```

## Check core pattern

```bash
cat /proc/sys/kernel/core_pattern
```

## Build C++ program with debug info

```bash
g++ -Wall -g program.cpp
```

## Run GDB

```bash
gdb <executable-file> <core-file>
```

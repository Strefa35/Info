# Linux Commands

## Analyze Text Files

| Command | Description |
|---------|-------------|
| `head`  | Display top N lines |
| `tail`  | Display bottom N lines |
| `cut`   | Display certain columns |
| `sort`  | Organize data in columns |
| `more`  | Page through a file |
| `less`  | Page through a file (with search) |
| `cat`   | Print file contents |
| `tac`   | Print file contents in reverse |

## Prevent overwrites with noclobber

```bash
set -o noclobber
ls /etc >| file1    # force overwrite when noclobber is set
```

## Named pipes

```bash
mkfifo /tmp/fifo1
```

## tee — write to file and stdout simultaneously

```bash
ls /etc | tee filename
```

## Process Management

```
           top
     killall     uptime
  ps    pgrep    pkill
bg   fg   jobs   kill
```

### procps

```bash
dpkg -L procps
```

### uptime

```bash
uptime
```

### Jobs

```bash
jobs
```

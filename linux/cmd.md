# Analyze Text File

  head - display top n lines
  tail - display bottom n lines
  cut  - display  certain columns
  sort - organize data in columns
  
  more
  less - page through the file

  cat
  tac



# Prevent overwrites with noclobber
  set -o
  set -o noclobber - 
  ls /etc >| file1

# Named pipes are created with mkfifo
  mkfifo /tmp/fifo1
  
# tee

  ls /etc | tee filename
  
  
# Top administrator manages processes
                       {   top   }
                 { killall } {  uptime  }
           {    ps   } {  pgrep  } {  pkill  }
    {    bg   } {    fg   } {  jobs   } {   kill  }
    
    
# procps

  dpkg -L procps
  
# uptime


# Jobs

    $ jobs
  
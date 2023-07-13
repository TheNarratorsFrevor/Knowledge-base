

### PS Cheatsheet

  
  

The **ps** stands for process status and it is a handy tool used to retrieve the information about currently running processes on Linux or BSD systems. This cheatsheet collets the most useful **ps** invocations.

Show all processes

`ps aux`

Show all processes including commandline arguments

`ps -AFl`

Show all processes with threads in tree mode

`ps -AlFH`

Show processes in a hierarchy

`ps -e -o pid,args --forest`

Show list of processes owned by a specific user

`ps -U **user** -u **user** u`

Show information for a particular process

`ps -p **pid**
`ps uax | grep **process_name**`

Show all threads for a particular process by id

`ps -p **pid** -L -o pid,tid,pcpu,state,comm`

Get top 5 processes by CPU usage

`ps -e -o pcpu,cpu,nice,state,cputime,args --sort pcpu | sed '/^ 0.0 /d'| tac |head -5`
`ps auxf | sort -nr -k 3 | head -5`

Get top 5 processes by memory usage

`ps -e -orss=,args= | sort -b -k1,1n | pr -TW$COLUMNS| tac | head -5
`ps auxf | sort -nr -k 4 | head -5`

Get security info

`ps -eo euser,ruser,suser,fuser,f,comm,label`
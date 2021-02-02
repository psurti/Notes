https://linux-mm.org/LinuxMM   
https://www.linuxatemyram.com/   

#### IPC/Shared Memory (python and Java)
https://stackoverflow.com/questions/9250648/fast-ipc-socket-communication-in-java-python/9251718   

#### Bare Linux Commands
```shell
# Find all open/server ports without netstat command
declare -a array=($(tail -n +2 /proc/net/tcp | cut -d":" -f"3"|cut -d" " -f"1")) && for port in ${array[@]}; do echo $((0x$port)); done | sort | uniq

# Find command line without ps command
cat /proc/<id>/cmdline

# View console logs without any log file
tail -f /dev/stdout or tail -f /proc/self/fd/1
tail -f /dev/stderr or tail -f /proc/self/fd/2
```

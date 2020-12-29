## Comparing two binary files

```
diff -y <(xxd truststore.jks) <(xxd /home/okaraduman/apps/360t/rtc/int/rtc-digest2/runtime-client/conf/truststore.jks)
```

## size of directory
```
ncdu
```

## list size of directory
```
du -sh *
```

### list size of directory with order
```
du -sk * | sort -n
```

## Passing arguments to grep 
```
grep ".noname" application.properties | awk '{print substr($1,0,index($1,".prod"))}' | xargs -I{} grep {} application2.properties 
```

## Grep two file and diff
```
diff <(grep "vm.args" test1.txt) <(grep "vm.args" test2.txt )
```
## Show cpu usage for each thread
```
top -n 1 -H -p <pid>
```
## Freeing Disk Space
https://itsfoss.com/free-up-space-ubuntu-linux/ 

Get rid of packages that are no longer required
```
sudo apt-get autoremove
```

 Clean up APT cache in Ubuntu
 where cache is
 ```
 sudo du -sh /var/cache/apt 
 ```
 
 clean up
```
sudo apt-get clean
```

Clear systemd journal logs [Intermediate knowledge]
see usage
```
journalctl --disk-usage
```
clean up (older than 3d)
```
sudo journalctl --vacuum-time=3d
```

Uninstall Unused Applications Through the Command Line
list all deb packages
```
dpkg --list
```

remove specific package
```
sudo apt-get purge “package-name”
```

## If Else condition
```
[ "$3" -lt 480 ] -- numeric comparison, compatible with all POSIX shells
[ "$3" \< 480 ] -- string comparison (generally wrong for numbers!), compatible with all POSIX shells
[[ $3 < 480 ]] -- string comparison (generally wrong for numbers!), bash and ksh only
(( $3 < 480 )) -- numeric comparison, bash and ksh only
(( var < 480 )) -- numeric comparison, bash and ksh only, where $var is a variable containing a number
```
*example*
```
if ((2 < 4)); then echo 'ok'; fi
```

## Swap usage
https://blog.sleeplessbeastie.eu/2016/12/26/how-to-display-processes-using-swap-space/
```
find /proc -maxdepth 2 -path "/proc/[0-9]*/status" -readable -exec awk -v FS=":" '{process[$1]=$2;sub(/^[ \t]+/,"",process[$1]);} END {if(process["VmSwap"] && process["VmSwap"] != "0 kB") printf "%10s %-30s %20s\n",process["Pid"],process["Name"],process["VmSwap"]}' '{}' \; | awk '{print $(NF-1),$0}' | sort -hr | head | cut -d " " -f2-
```

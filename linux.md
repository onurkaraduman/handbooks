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

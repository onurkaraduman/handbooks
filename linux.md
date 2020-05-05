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

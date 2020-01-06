## Comparing two binary files

```
diff -y <(xxd truststore.jks) <(xxd /home/okaraduman/apps/360t/rtc/int/rtc-digest2/runtime-client/conf/truststore.jks)
```


## list size of directory
```
du -sh *
```

### list size of directory with order
```
du -sk * | sort -n
```

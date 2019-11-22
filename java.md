*Stream Api*
# The following line of code can have java.util.ConcurrentModificationException. Exception happens in collect method. 
```
List<String> collect = list.stream().collect(Collectors.toList());
```


## SSL Handshake debug log
-Djavax.net.debug=all

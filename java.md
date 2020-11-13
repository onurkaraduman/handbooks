## Stream Api
* The following line of code can have java.util.ConcurrentModificationException. Exception happens in collect method. 
```
List<String> collect = list.stream().collect(Collectors.toList());
```


## SSL Handshake debug log
-Djavax.net.debug=all


### SSl Mutual Authentication
These are the overall steps that take place during SSL handshake:

* Client initiates the request.
* The server sends its own certificate which is found from its keystore.
* The client verifies its certificate if it can be trusted. If the server’s certificate or its CA’s certificate are found in truststore, then the server is authenticated.
* If client authentication is enabled at server side, the server requests’s for client’s certificate.
* The client sends its own certificate which is found from its keystore.
* The server verifies the client’s certificate if it can be trusted. If the client’s certificate or its CA’s certificate are found in its truststore, then the client is authenticated.


## Proxy Authentication

// This property is needed for proxy authentication after java 8
```
if (!PropertiesHelper.isSystemPropertySet("jdk.http.auth.tunneling.disabledSchemes")) {
		PropertiesHelper.setSystemProperty("jdk.http.auth.tunneling.disabledSchemes", "");
```


## Caching
useful links
* https://hazelcast.com/blog/architectural-patterns-for-caching-microservices/
* https://labs.consol.de/de/java-caches/part-4-3-client-server-with-hazelcast/index.html

## Log4j
* https://mkyong.com/logging/log4j-hello-world-example/

## Date Operations
Set next hour, check the following operations: 

```
91	        private Date getBeginningOfNextHour() {
 	 	92	                Calendar c = Calendar.getInstance();
 	 	93	                c.setTime(new Date());
 	 	94	                c.set(Calendar.MINUTE, 0);
 	 	95	                c.set(Calendar.SECOND, 0);
 	 	96	                c.set(Calendar.MILLISECOND, (int) TimeUnit.HOURS.toMillis(rolloverTimeInHours));

```

## Strings
https://dzone.com/articles/java-memory-management
In this case, we actually see that we have two different objects on the heap. If we consider that the computed String will be used quite often, we can force the JVM to add it to the string pool by adding the .intern() method at the end of computed string:
```
String localPrefix = new Integer(297).toString().intern();
```

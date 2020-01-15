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

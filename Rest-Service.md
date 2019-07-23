Testing cors with curl:
curl -H "Origin: http://localhost:3000"   -H "Access-Control-Request-Method: GET"   -H "Access-Control-Request-Headers: X-Requested-With"   -X OPTIONS --verbose   http://localhost:8080

response:
http 403: cors is not activated
http 200: cors is activated

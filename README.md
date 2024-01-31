# ssl-tls

An SSL (Secure Socket Layer) certificate is a digital certificate that establishes a secure and encrypted connection
 between a web browser and a web server. 
 
Until now, pod is exposed using Ingress, but the connection is over HTTP and therefore it is unencrypted. 
Let’s add some security to the server. First,
 create certifiates using openssl, then create kubernetes Secret of type ssl. And finally utilize it in Ingress resource.

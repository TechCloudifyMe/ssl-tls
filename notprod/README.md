## create a key and crt 
```

 $ openssl req \
 -x509 -newkey rsa:4096 -sha256 -nodes \
 -keyout tls.key -out tls.crt \
 -subj "/CN=techcloudifyme.com" -days 365
 
 Generating a 4096 bit RSA private key
 ........++
 ...................................................................................................++
 writing new private key to 'tls.key'
 -----
 
 $ ls
 tls.crt  tls.key
## create a secret using the above crt
```
kubectl create secret tls ingress-tls \
   --cert=tls.crt \
   --key=tls.key
```
## use that secret in ingress yaml file

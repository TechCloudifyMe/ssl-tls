## create a key and crt 
```
openssl req -x509 \
  -new -nodes  \
  -days 365 \
  -key tls.key \
  -out tls.crt \
  -subj "/CN=*.techcloudifyme.com"
```
## create a secret using the above crt
```
kubectl create secret tls ingress-tls \
   --cert=tls.crt \
   --key=tls.key
```
## use that secret in ingress yaml file

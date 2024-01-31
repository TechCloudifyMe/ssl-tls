## create a key and csr using config file
```
openssl req -x509 -newkey rsa:2048 -nodes -keyout tls.key -out tls.csr -config openssl.cnf -sha256 -days 365
```
## send request to CA
## CA will send you crt file
## create a secret using that crt file
```
kubectl create secret tls ingress-tls \
   --cert=tls.crt \
   --key=tls.key
```
## use that secret in ingress yaml file

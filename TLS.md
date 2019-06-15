#### Certificates
https://curl.haxx.se/docs/sslcerts.html

https://www.thomasvitale.com/https-spring-boot-ssl-certificate/

#### How to create a P12 (JKS keystore) with openssl
````
openssl pkcs12 -export -in client\client.crt -inkey client\client.key -chain -CAfile ca\ca.crt 
-name "localhost" -out client.p12
````

#### Using P12 (Java keystore) to authenticate to a TLS server
client.p12 contains the key and the certificate i.e. keystore

ca.crt is the CA authority that is part of the truststore
````
curl -v --cacert ca\ca.crt --cert-type P12 --cert client.p12:changeit https://localhost:8000
````

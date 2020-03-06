#### Certificates
https://github.com/psurti/Notes/tree/master/TLS

https://curl.haxx.se/docs/sslcerts.html

https://www.thomasvitale.com/https-spring-boot-ssl-certificate/

#### How to create a P12 (JKS keystore) with openssl
````
openssl pkcs12 -export -in client\client.crt -inkey client\client.key -chain -CAfile ca\ca.crt 
-name "localhost" -out client.p12
````

#### Using CURL with P12 (Java keystore) to authenticate to a TLS server
client.p12 contains the key and the certificate i.e. keystore

ca.crt is the CA authority that is part of the truststore
````
curl -v --cacert ca\ca.crt --cert-type P12 --cert client.p12:changeit https://localhost:8000
````

#### Where are keys and certs stored in keystore and truststore (2-way)?
```
server.keystore:
 private server key
 public server certificate
 
server.truststore:
  public cient certificate
  public server certificate
  
client.keystore:
  private client key
  public client certificate

client.truststore:
  public server certificate
  public client certificate
```

#### Setup keystore and truststore (1-way)
```
keytool.exe -genkeypair -keyalg RSA -alias localhost -keystore keystore.jks -storepass password123 -validity 360 -storetype pkcs12

keytool.exe -export -alias localhost -file localhost.cer -keystore keystore.jks

keytool.exe -import -v -trustcacerts -alias localhost -file localhost.cer -keystore truststore.jks
```
#### How to extract key and certificate from PKCS12 (Java keystore)?
````
Export certificate using openssl:
openssl pkcs12 -in keystore.p12  -nokeys -out cert.pem

Export unencrypted private key:
openssl pkcs12 -in keystore.p12  -nodes -nocerts -out key.pem
````


#### TLS/SSL Java Properties w/o SpringBoot
https://www.oodlestechnologies.com/blogs/Connect-to-SSL-enabled-RabbitMQ-server-Springboot/  
https://docs.spring.io/spring-cloud-dataflow/docs/1.1.0.M1/reference/html/getting-started-security.html   
https://www.baeldung.com/spring-boot-https-self-signed-certificate   
https://docs.spring.io/spring-boot/docs/current/reference/html/appendix-application-properties.html#server-properties   
https://docs.oracle.com/javase/7/docs/technotes/guides/security/jsse/JSSERefGuide.html#Customization   
https://stackoverflow.com/questions/56655545/how-to-change-java-keystorejks-keystore-and-alias-password-so-that-they-work  
https://www.naschenweng.info/2018/02/01/java-mutual-ssl-authentication-2-way-ssl-authentication/   






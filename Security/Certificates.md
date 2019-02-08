# Certificate management

```bash
openssl s_client -showcerts -connect www.domain.com:443       #List certificate chain


```

# Certificate manipolation
```bash
openssl x509 -in <cert_to_read.crt> -noout -text       # List certificate chain on pem
openssl x509 -in <cert_to_read.crt> -inform pem -out <cert_to_read.der> -outform der # Convert cert from pem to der
```


# Import RootCA
```bash
$JAVA_HOME/jre/bin/keytool -importcert -alias <root_ca_alias> -storepass <storepass> -keystore <trust_store> -file <root_ca_der_cert>
```

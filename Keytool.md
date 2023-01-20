# Keytool

```
openssl pkcs12 -export -in jirp2001.com.br.cer -inkey jirp2001.com.br.key -out z01dev1.com.br.p12

keytool -changealias -alias "1" -destalias "bitcert" -keystore z01dev1.com.br.p12 -keypass SENHA_KEYSTORE_SRC -storepass SENHA_KEYSTORE_SRC

keytool -importkeystore -srckeystore z01dev1.com.br.p12 -srcstoretype pkcs12 -destkeystore /Users/anderson/.sdkman/candidates/java/current/lib/cacerts -deststoretype pkcs12 -noprompt -srcstorepass SENHA_KEYSTORE_SRC -deststorepass SENHA_KEYSTORE_DEST

keytool -importkeystore -srckeystore z01dev1.com.br.pfx -srcstoretype pkcs12 -destkeystore /Users/anderson/.sdkman/candidates/java/current/lib/cacerts -deststoretype JKS -noprompt 

keytool -importkeystore -srckeystore z01dev1.com.br.pfx -srcstoretype pkcs12 -destkeystore /Users/anderson/.sdkman/candidates/java/current/lib/cacerts -deststoretype pkcs12 -noprompt -srcstorepass tefode -deststorepass changeit

keytool -importkeystore -srckeystore z01dev1.com.br.p12 -srcstoretype pkcs12 -destkeystore /Users/anderson/.sdkman/candidates/java/current/lib/cacerts -deststoretype pkcs12 -noprompt -srcstorepass tefode -deststorepass changeit

keytool -list -v -keystore /Users/anderson/.sdkman/candidates/java/current/lib/cacerts -storepass changeit

keytool -delete -alias 1 -keystore /Users/anderson/.sdkman/candidates/java/current/lib/cacerts -storepass changeit

keytool -changealias -alias "1" -destalias "bitcert" -keystore z01dev1.sicoob.com.br.p12 -keypass tefode -storepass SENHA_KEYSTORE_SRC

keytool -list -v -keystore z01dev1.sicoob.com.br.p12 -storepass tefode

openssl pkcs12 -export -in jirp2001.sicoob.com.br.cer -inkey jirp2001.sicoob.com.br.key -out z01dev1.sicoob.com.br.p12

keytool -changealias -alias "1" -destalias "bitcert" -keystore z01dev1.sicoob.com.br.p12 -keypass tefode -storepass SENHA_KEYSTORE_SRC

openssl pkcs12 -export -in jirp2001.sicoob.com.br.cer -inkey jirp2001.sicoob.com.br.key -out z01dev1.sicoob.com.br.pfx 
-srckeypass tefode -destkeypass changeit -noprompt 
```

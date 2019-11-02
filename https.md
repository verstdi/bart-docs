# BART in HTTPS

For developments or tests, BART can be deployed in HTTP. 
It is adviced to configure the application under SSL for production, acceptance or other environments playing with sensitive data.

The very first step to pass to SSL: generate a key.
Here in this example, a self-signed key is generated to avoid any purchase.
For production, it is of course adviced to buy a certificate to a trusted corporate (the process to generate a key in this case is very similar). 

## 1. Generate key (self signed in the example) via the command line:
**{java location}** \bin\keytool -genkeypair -alias **{alias name}** -storetype **{type of key}** -keyalg **{algorithm}** -keysize **{keysize}** -keystore **{certficate name}**.p12 -validity **{validity in days}**


 Example | 
------------ | 
C:\Programmes\Java\jdk1.8.0_231\bin\keytool -genkey -alias bootsecurity -storetype PKCS12 -keyalg RSA -keysize 2048 -keystore bootsecurity.p12 -validity 3650 | 

## 2. Answer to the questions

Example of keytool command interractions:

![Image of command line interactions](https://github.com/verstdi/bart-docs/edit/master/pics/im00001_generate_key.JPG)

## 3. Replace the next files in the application jar file

 Wanted protocol|File to replace | By this content
------------ | ------------ | ------------ 
HTTPS|application.properties | server.port=443(1) <br>server.ssl.enabled=true(2) <br>server.ssl.key-store:src/main/resources/bootsecurity.p12 (3)<br>server.ssl.key-store-password: ***{put here the chosen password during step 2}*** server.ssl.keyStoreType:PKCS12 (4)<br>server.ssl.keyAlias: bootsecurity(5)
HTTP|application.properties | server.port=8080 <br>server.ssl.enabled=false

(1)wanted https port<br>(2)enable ssl(will launch specific components)<br>(3)chosen **{certficate name}**.p12 during the step 2<br>(4)storetype **{type of key}** during the step 2<br>(5)**{alias name}** during the step 2

 Wanted protocol|File to replace | By this file
------------ | ------------ | ------------ 
HTTPS|bootsecurity.p12 | the file having the name **{certficate name}**.p12 obtained during the step 2

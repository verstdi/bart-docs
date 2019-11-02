# BART in HTTPS

For developments or tests, BART can be deployed in HTTP. 
It is adviced to configure the application under SSL for production, acceptance or other environments playing with sensitive data.

The very first step to pass to SSL: generate a key.
Here in this example, a self-signed key is generated to avoid any purchase.
For production, it is of course adviced to buy a certificate to a trusted corporate (the process to generate a key in this case is very similar). 

## 1. Generate key (self signed in the example) via the command line:
**{java location}** \bin\keytool -genkeypair -alias **{alias name}** -storetype **{typ of key}** -keyalg **{algorithm}** -keysize **{keysize}** -keystore **{certficate name}**.p12 -validity **{validity in days}**


 Example | 
------------ | 
C:\Programmes\Java\jdk1.8.0_231\bin\keytool -genkey -alias bootsecurity -storetype PKCS12 -keyalg RSA -keysize 2048 -keystore bootsecurity.p12 -validity 3650 | 

## 2. Answer to the questions

Example of keytool command interractions:

![Image of command line interactions](https://github.com/verstdi/bart-docs/edit/master/pics/im00001_generate_key.JPG)

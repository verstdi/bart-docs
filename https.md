# Generate certificate

## Generate key (self signed in the example) via the command line:
**{java location}** \bin\keytool -genkeypair -alias **{alias name}** -storetype **{typ of key}** -keyalg **{algorithm}** -keysize **{keysize}** -keystore **{certficate name}**.p12 -validity **{validity in days}**


 Example | 
------------ | 
C:\Programmes\Java\jdk1.8.0_231\bin\keytool -genkey -alias bootsecurity -storetype PKCS12 -keyalg RSA -keysize 2048 -keystore bootsecurity.p12 -validity 3650 | 


# bart-docs
Project containing all the documents and useful informations concerning the project BART https://github.com/verstdi/bart
![Image of architecture](https://github.com/verstdi/bart-docs/edit/master/pics/im00002_architecture.png)

# Security
[HTTPS](https://github.com/verstdi/bart-docs/blob/master/https.md) is adviced for production and other sensitive environments.

# Installation
Execute the wanted version of the BART jar file. The arguments "user" and "password" are mandatory

Example |
------------ | 
java -jar bart-0.0.1.jar user=admin password=E%k&11Bxl-40f|

The user and password represents the administrator access, only able to call the rest service "/report".
This user-password must be present at each restart of the application (and must be always the same to no reject current requests)
The password must be provided only to the applications authorized to call the application BART.
The password can be shared via an application for password like KeePass for example and must not be shown to anybody of course.


# bart-docs
Project containing all the documents and useful informations concerning the project BART https://github.com/verstdi/bart
![Image of architecture](https://github.com/verstdi/bart-docs/edit/master/pics/im00002_architecture.png)

# Security
[HTTPS](https://github.com/verstdi/bart-docs/blob/master/https.md) is adviced for production and other sensitive environments.

# Installation
Execute the wanted version of the BART jar file. The arguments "user" and "password" are mandatory and up to you.

Example |
------------ | 
java -jar bart-0.0.1.jar user=admin password=E%k&11Bxl-40f|

The user and password represents the administrator access, only able to call the rest service "/report".
This user-password must be present at each restart of the application (and must be always the same to no reject current requests)
The password must be provided only to the applications authorized to call the application BART.
The password can be shared via an application for password like KeePass for example and must not be shown to anybody of course.

# Add reports to the application
In the downloaded version of jar of the application, add in the folder "/report" all the jasper files and eventual pictures

# Test BART
## Check availability
![Image of check availability](https://github.com/verstdi/bart-docs/edit/master/pics/im00003_check.png)
## Test the example report included in BART
Use a tool permitting to do REST requests.
Put the user-password you've defined for the BART administrator

Put the next json in the request body:

Example |
------------ | 
{
"template":"R0002_SchoolClassExample",
"parameters":[{"key":"school_name","value":"Elementary School"}],
"json":"{\"code\":\"1A\",\"description\":\"Elementary school - class 1A\",\"students\":[{\"firstname\":\"Helena\",\"lastname\":\"Cassidy\"},{\"firstname\":\"Jules\",\"lastname\":\"Smith\"},{\"firstname\":\"Emma\",\"lastname\":\"Kennedy\"},{\"firstname\":\"Bug\",\"lastname\":\"Danny\"},{\"firstname\":\"John\",\"lastname\":\"Doe\"}],\"teachers\":[{\"firstname\":\"Bart\",\"lastname\":\"Van Den Bergh\",\"skills\":[{\"code\":\"MATH\",\"description\":\"Mathematics\"},{\"code\":\"PHYS\",\"description\":\"Physics\"}]},{\"firstname\":\"Emma\",\"lastname\":\"Kennedy\",\"skills\":[{\"code\":\"ENG\",\"description\":\"English\"}]},{\"firstname\":\"Piet\",\"lastname\":\"Dubucq\",\"skills\":[{\"code\":\"GYM\",\"description\":\"Sports\"}]}]}"
}|

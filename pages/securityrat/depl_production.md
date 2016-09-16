---
title: Production Deployment
#keywords: sample
summary: "Description of steps necessary for taking SecurityRAT into production."
sidebar: home_sidebar
permalink: depl_production.html
#simple_map: true
#map_name: usermap
#box_number: 1
folder: product2
---


## Prerequisities

Before installing SecurityRAT, you have to have the following components installed:

* JAVA 8
* Maven
* MySQL
* (recommended) Apache Web Server serving as a reverse proxy and terminating TLS


## Before starting the application :

- checkout the SecurityRAT project
- log into your mysql server and create an empty database for this application
- edit the database in the file `src/main/resources/config/application-prod.yml` according to the examples

```
databaseName: $YourDatabase
username: $DBUserName
password: $DBUserPassword
```

- enable TLS for spring boot if you don't use a separate web server:
   - e.g. generate a self-signed certificate in the root directory of SecurityRAT: `keytool -genkey -alias tomcat -storetype PKCS12 -keyalg RSA -keysize 2048 -keystore keystore.p12 -validity 3650`
   - add the following lines into `application-prod.yml`:
   
```
server:
  ssl:
    key-store: keystore.p12
    key-store-password: $MyPassword
    keyStoreType: PKCS12
    keyAlias: tomcat
```

- edit the authentication type and the Mail server configurarion in the file `src/main/resources/config/application.yml`.

```
authentication:
  type: FORM
	
mail:
  host: localhost # mail server
  port: 25
  username:	#might be needed depending on your mail server
  password:	#might be needed depending on your mail server
  protocol: smtp
  tls: false
  auth: false
  from: securityRAT@localhost # from email address
```

## How to run in prod mode
- fire `mvn -Pprod -DskipTests package`. This will build the following files:
  - `target/securityRAT-${version}.war`
  - `target/securityRAT-${version}.war.original`
- copy the file `target/securityRAT-${version}.war` file to your production server
- in your target directory on the server, create a directory called `config` and copy the files `src/main/resources/config/application-prod.yml` and `src/main/resources/config/application.yml` there
- switch to the target directory and fire `java -jar securityRAT-${version}.war --spring.profiles.active=prod`
- log in to your mysql server and in the `JHI_USER` table rename the 'admin' user login to your CAS username **OR** log in with the credentials `admin` for the username and password (in order to get full rights for your user).
- it is recommended to use a web server (e.g. [Apache](https://httpd.apache.org/) as a proxy, with a proper TLS configuration set etc).
- go to the URL of your server. You should be verified by your previously setup CAS server OR FORM login and can start using the application.
- The constants (under Administration -> constants) must be edited accordingly.
- **it is important to change the `admin` password in `prod mode`.**

{% include links.html %}

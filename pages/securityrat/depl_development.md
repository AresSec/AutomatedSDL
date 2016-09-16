---
title: Development Deployment
#keywords: sample
summary: "This setup is recommended if you want to customize or further develop the SecurityRAT tool."
sidebar: home_sidebar
permalink: depl_development.html
#simple_map: true
#map_name: usermap
#box_number: 1
folder: product2
---



## Prerequisities:
- As this project is originally based on [JHipster](http://jhipster.github.io/), lot of prerequisities are common with this project. The following are necessary:
  - [JAVA 8 (JDK)](http://www.oracle.com/technetwork/java/javase/overview/java8-2100321.html)
  - [Maven](https://maven.apache.org/)
  - [Npm](https://www.npmjs.com)
  - [Bower](http://bower.io/)
  - [Grunt](http://gruntjs.com/)
  - [MySQL Database](https://www.mysql.com/)

## Before starting the application :
- checkout this project
- log into your mysql server and create an empty database for this application
- edit the database in the file `src/main/resources/config/application-[dev|prod].yml` according to the examples

```
databaseName: $YourDatabase
username: $DBUserName
password: $DBUserPassword
```

- enable TLS for spring boot if you don't use a separate web server:
   - e.g. generate a self-signed certificate in the root directory of SecurityRAT: `keytool -genkey -alias tomcat -storetype PKCS12 -keyalg RSA -keysize 2048 -keystore keystore.p12 -validity 3650`
   - add the following lines into `application-dev.yml`:
   
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
  
## How to run
- if you are going to run SecurityRAT and the CAS server on the same machine at least 6GB of RAM are recommended.
- fire `mvn spring-boot:run`. This will automatically create the database structure if it doesnt exist yet.
- log in to your mysql server and in the `JHI_USER` table rename the `admin` user login to your CAS username **OR** log in with the credentials `admin` for the username and password (in order to get full rights for your user).
- go to https://localhost:9000. You should be verified by your previously setup CAS server *OR* FORM login and can start using the application.
- The constants (under Administration -> constants) must be edited accordingly.
{% include links.html %}

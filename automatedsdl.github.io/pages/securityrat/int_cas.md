---
title: Central Authentication Service (CAS)
#keywords: sample
summary: "Steps for deploying SecurityRAT as a CAS (SSO) client."
sidebar: home_sidebar
permalink: int_cas.html
#simple_map: true
#map_name: usermap
#box_number: 1
folder: product2
---


## Central Authentication Service

If you're not familiar with CAS, please refer to these resources: 

* [Wikipedia Article](https://en.wikipedia.org/wiki/Central_Authentication_Service)
* [project homepage](https://www.apereo.org/projects/cas)


## Integration steps

In order to deploy SecurityRAT as a CAS client, just open the configuration file at `src/main/resources/config/application.yml` (depending on whether you want to configure the development or production profile) and edit the following lines:

```
authentication:
  type: CAS # the default setting

cas:
  casLoginUrl: http(s)://localhost:8443/cas #Change to the URL your CAS server listens on
  casLogoutUrl: https://localhost:8443/cas/logout # Change to your CAS server logout URL
  callbackUrl: https://localhost:9000/callback #Change to the correct URL (https) of SecurityRAT
``` 

Restart the application and you're done!


{% include links.html %}

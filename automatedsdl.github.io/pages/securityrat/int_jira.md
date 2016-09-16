---
title: JIRA
#keywords: sample
summary: "Steps for integrating SecurityRAT with JIRA."
sidebar: home_sidebar
permalink: int_jira.html
#simple_map: true
#map_name: usermap
#box_number: 1
folder: product2
---


## JIRA

If you're not familiar with JIRA, please refer to the [project homepage](https://www.atlassian.com/software/jira). 


## Integration use cases

JIRA integration is used in three cases:

* the artifact settings you've defined can be exported to / imported from a JIRA ticket (using a YAML-file attachment)
* the particular requirements can be opened as separate JIRA tickets
* SecurityRAT users can give feedback to particular requirements. This leads to opening a JIRA ticket in a configured queue.  


## Steps for integration

The connection to JIRA is realized solely using the JavaScript side of SecurityRAT. This means that Cross-Origin Resource Sharing (CORS) is used. In order to enable CORS on JIRA side, you need JIRA to include respective headers in HTTP responses: 

```
Access-Control-Allow-Origin: https://$SecurityRAT_URL
Access-Control-Allow-Methods: GET,HEAD,OPTIONS,POST
Access-Control-Allow-Headers: Content-Type, X-Atlassian-Token
Access-Control-Allow-Credentials: true

``` 

Usually you realize this by configuring a HTTP Server serving as a reverse proxy for your JIRA instance. 

{% include warning.html content='Depending on your JIRA version, you might get an error message related to a CSRF token. The issue is documented [here](https://confluence.atlassian.com/jirakb/rest-api-calls-with-a-browser-user-agent-header-may-fail-csrf-checks-802591455.html). The recommended solution is to remove the User Agent header on your proxy server.' %}


{% include links.html %}

---
title: Prevention / Templates
#keywords: sample
#summary: ""
sidebar: home_sidebar
permalink: req_prev.html
#simple_map: true
#map_name: usermap
#box_number: 1
folder: product2
---

## SecurityRAT

**SecurityRAT** ("Security Requirement Automation Tool") is a tool supposed to help you with security challenges in your development projects.

The basic idea is very simple: you specify the properties of an application (usually, we use the name "artifact") that you're developing. Based on these properties, the tool gives you a list of security requirements you should fulfill. 

For every single requirement, you can decide whether it should/will be implemented and add your own comment (or e.g. reasoning why you're not going to implement it if you've decided against it). Once you're done, you can persist the particular requirement set in a JIRA ticket for documentation purposes (the requirement set is attached as a YAML file). 

Afterwards, you can create JIRA tickets for particular requirements in a batch mode and track them with SecurityRAT. The workflow is shown on the image below:

{% include image_center.html file="basic_workflow.png" alt="SecurityRAT Workflow" caption="Basic SecurityRAT workflow" %}

Finally, you can use SecurityRAT to load requirement set persisted in Step 3. SecurityRAT will also load the information to all issues created for this set and display their status. 

For getting more information about the tool in 40 minutes, you can watch this video from the [OWASP AppSecEU 2016 Conference](https://appseceurope2016.sched.org/event/6XQ5/addressing-security-requirements-in-development-projects):

<center><iframe width="560" height="315" src="https://www.youtube.com/embed/6N__PgMSfYU" frameborder="0" allowfullscreen></iframe></center>


The tool itself is available on GitHub: [SecurityRAT](https://github.com/SecurityRAT/SecurityRAT) and the full documentation can be found on GitHub Pages: [SecurityRAT Documentation](https://securityrat.github.io/)

{% include links.html %}

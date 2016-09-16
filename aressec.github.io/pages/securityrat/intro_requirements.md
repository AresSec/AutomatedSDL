---
title: Requirement Data Schema
#keywords: sample
summary: "In order to be able to customize the default requirement set or even to create a new one from scratch according to your needs, this chapter will explain all entities which form a requirement."
sidebar: home_sidebar
permalink: intro_requirements.html
#simple_map: true
#map_name: usermap
#box_number: 1
folder: product2
---


## Requirement Skeletons and Requirement Categories

As the name indicates, the Requirement Skeleton presents something like a core of a requirement and is a central part of the schema. An example could be "Implement brute-force protection".

As there will probably be quite a big number of requirements, it is sensible to group them into categories (e.g. *Authentication*, *Session Management*, etc.).


## Optional Columns and Optional Column Values

A requirement can come with many extra information which you might not want to show in all scenarios or might not be relevant for every target. Think about examples like "Best practise for implementation of this requirement", "Motivation why this requirement is important" or "How to test a successful implementation of the requirement". These would be the Optional Columns. 

Every *Optional Column* contains *Optional Column Values* which are linked to a particular *Requirement Skeleton*.

Example could be:

* Optional Column: *Motivation*
* Optional Column content for Brute Force Protection: *If you omit brute force protection, attacker could use a script guessing passwords of the system users in order to take over their identities.* 


## Status Columns and Status Column Values

While working with you first requirement set, you will probably find out that on an artifact level, it will be handy to specify some extra information for every requirement, even if it is just an indication whether the requirement will be fulfilled or not in the easiest case.

Status Columns are of two types:

* eval: In this case, this Status Column is linked to Status Column Values. An example could be the Status Column "Implemented" and respective values "Yes" and "No".
* text: Free text, e.g comment explaining the implementation of the requirement

## Implementation Type

Implementation type enables you to specify:

* which requirement skeletons are relevant for this implementation type
* which optional and status column are relevant

In the default requiremment set, there are three implementation types:

* **internal:** when the artifact is developed and operated internally
* **exernal:** when the artifact is developed by an external company, but still operated internally
* **cloud:** when the artifact is both developed and operated externally

It contains the following attributes:

| Name | Explanation | Example |
|----|--------|--------|
| Short Name | Short ID of the requirement. | *AU-01* (for the first requirement belonging to the *Authentication* category |
| Description | Universally valid text of the requirement. | *The system has to be protected against brute-force attacks.* |


## Collection Category and Collection Instance

Collection Category is a security relevant parameter which has an impact on which requirement skeletons are relevant. Collection Instance is then a particular value of this parameter. These are the options which you specify in the very beginning when working with SecurityRAT in order to render a relevant set of requirements. 

The following table shows some examples from the default requirement set:

| Collection Category | Collection Instances |
|---|---|
| Criticality | Low, Medium, High |
| Externally Reachable |  Yes, No |
| Authentication | Single Sign-On Client, Local, None |


## Tag Category and Tag Instance

Tag Category and Tag Instance work in a similar way as Collections. The biggest difference is that Tags are never persisted; they are used for filtering requirements in specific situation, e.g. you want to have an overview of which requirements are relevant for a particular project phase, which are supposed to be tested manually etc. 

The following table shows some examples from the default requirement set:

| Tag Category | Tag Instances |
|---|---|
| Requirement Type | Technical, Lifecycle |
| Project Phase |  Initiation, Design, Implementation, Rollout |


## Alternative Sets and Alternative Instances

Alternative Sets are bound to Option Columns and are supposed to enhance their content for particulalar requirements using Alternative Instances in specific situation. Think about an option column "Further specification" - if you're developing the application in a certain language, e.g. JAVA it could be reasonable to show a coding pattern or information which library you should be using. 

In this way, you have the option to say: "Ok, give me all extra information you have for if I'm developing in JAVA, PHP, ..."

Alternative Sets and Instances are not currently used in the default requirement set. 


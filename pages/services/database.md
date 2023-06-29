---
layout: page
permalink: /services/database
---

<!--
Move the markdown title slightly up to
match the proper titles on other pages
-->
<div style="margin-top: -38pt"></div>

# MongoDB database

A database which stores data from the submission and comment services.

We're using the official image from docker hub ([mongo](https://hub.docker.com/_/mongo)) and running it as a single instance (docs [here](https://www.mongodb.com/docs/cloud-manager/tutorial/deploy-standalone/)).
The services need to be able to connect to it in order to function and save objects to it.

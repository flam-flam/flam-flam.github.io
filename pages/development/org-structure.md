---
layout: page
title: Org structure
permalink: /development/org-structure
parent: _development
nav_order: 2
---

Every part of the project is container within its own repository
to make parallel development easier.

## dispatcher-service

[https://github.com/flam-flam/dispatcher-service](https://github.com/flam-flam/dispatcher-service)

Small service that streams reddit posts and comments to configurable endpoints.

## submission-service

[https://github.com/flam-flam/submission-service](https://github.com/flam-flam/submission-service)

Service listening for submission objects via an API endpoint
and saving them to an external database.

## comment-service

[https://github.com/flam-flam/comment-service](https://github.com/flam-flam/comment-service)

Service listening for comment objects via an API endpoint
and saving them to an external database.

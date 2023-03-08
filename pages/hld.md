---
layout: page
title: High level diagram
permalink: /hld
---

There are currently 3 phases defined for the project.

## Phase 1 <- We are here

Working microservices without observability.
Dispatcher is streaming live comments and submissions from Reddit
to the two corresponding services that simply save them to a database.

All services can be run locally in docker.

<img style="max-width: 500px" src="../assets/images/HLD-1.svg" alt="" />


## Phase 2

Added metrics and tracing in the microservices,
using OpenTelemetry to send logs, metrics and traces
to a free Grafana Cloud account.

There is a helm chart to run the services and OTel in k8s.

<img style="max-width: 700px" src="../assets/images/HLD-2.svg" alt="" />


## Phase 3

The grafana stack can be spinned up locally and contains
an anonymously accessible dashboard. The MELT data is only sent to
the local stack instead of the cloud.

Everything can be installed in a k8s cluster using a single helm chart.

<img style="max-width: 900px" src="../assets/images/HLD-3.svg" alt="" />

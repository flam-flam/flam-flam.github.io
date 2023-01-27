---
layout: page
title: High level diagram
permalink: /development/hld
parent: _development
nav_order: 1
---

There are currently 3 stages defined for the project.

## Stage 1

Working microservices without observability.
Dispatcher is streaming live comments and submissions from Reddit
to the two corresponding services that simply save them to a database.

All services can be run locally in docker.

![HLD](../assets/images/HLD-1.svg "Stage 1 HLD")

## Stage 2

Added metrics and tracing in the microservices,
using OpenTelemetry to send logs, metrics and traces
to a free Grafana Cloud account.

There is a helm chart to run the services and OTel in k8s.

![HLD](../assets/images/HLD-2.svg "Stage 2 HLD")

## Stage 3

The grafana stack can be spinned up locally and contains
an anonymously accessible dashboard. The MELT data is only sent to
the local stack instead of the cloud.

Everything can be installed in a k8s cluster using a single helm chart.

![HLD](../assets/images/HLD-3.svg "Stage 3 HLD")

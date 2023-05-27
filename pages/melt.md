---
layout: page
title: What is MELT?
permalink: /melt
---

There are 4 main types of observability data - metrics, events, logs, and traces,
often referred to as MELT data.
They differ in format, handling, and the kind of message they're meant to convey.
Below is a brief breakdown of what they are and their user cases.

[Opentelemetry agent](https://opentelemetry.io/) we're using in this project
can collect all 4 types.

## Metrics

Metric is a number that is measuring the state of some aspect of the system (software _or_ hardware).
It is designed to be shown on a graph as a time series to show how the system is changing over time.
The most obvious use cases are CPU/memory usage, number of HTTP 500 responses the server gave etc.

Metrics are very useful when you need to output numerical data fairly often.
They consist of two main non-numeric pieces of data: name and a list of labels.
For instance, `cpu_usage` would be a name of the metric that contains a numeric
measure of CPU usage - be it percentage or millicpu or whatnot.
The labels can contain other information about the context this particular
number was produced in, like `host=my.server.net` or `os=linux`.
These can be set to anything you need to make it easy to understand what
this metric actually means.

In an web server case you could have a metric called `status_code_count`
that contains counts of particular status codes
with relevant labels like `host=my.server.net`, `app=nginx`, `status_code=(200|400|500)`.
If the value of the metric with `status_code=500` label skyrockets, you can have
a look at the other labels that accompany it and see which app and which server are misbehaving.

The combination of labels are called "dimensions" of a metric.
Each dimension is effectively its own time series,
and each metric has the number of dimensions equal to product of all the label combinations.
As an example, a metrics that has the `host` label with 3 possible values has 3 dimensions.
If you add an `app` label with two possible values and all apps run on all hosts,
then the number of the dimensions goes up to 3x2=6 dimensions.

Observability providers like Splunk or Grafana do have limits on the dimensionality
as each metric time series is stored separately in the backend.
This is a good reason to not store unique values (e.g. guids) in metric dimensions,
as the cost of storing it will balloon very quickly.

## Events

Events are... well, events that occur in the system, notable enough to not be a simple logline.
This is probably the most esoteric observability data type.
They are discreet pieces of structured data (usually JSON) that are emitted when something 
interesting happens.
What is considered interesting is defined by the producers and consumers of this data -
all kind of engineers, from software to business intelligence.

It is different from logs in that it's not normally informing of a point in
a code path that has been reached (e.g. `processing the GET / request`),
but rather a part of business logic that was triggered
(e.g. `User clicked checkout`).
However, events can be stored in the same place as log data, as long as they're
clearly identifiable as events and handled accordingly.
They can also be stored in a message bus that many teams can subscribe to and
process them as they please.

In addition, as the data is normally stored as json, it can contain the same
labels/dimensions as all other data for easy correlation between them all.

## Logs

Logs are pieces of readable text data that are normally used by software engineers.
The contents are arbitrary and a use case depends on what you're doing, but
the generally the logs should inform of the state of the code rather than business events.

There is no standard format - it can be plain text, key value pairs, json - by it
is generally a good idea to keep logs within a single line as
most log aggregators struggle to parse multiline logs (like Loki)
or just use much more resources to do so (like Splunk).

While there isn't a standard, it is generally a good idea to make the logging
as structured as possible as it make extracting any useful data programmatically
much easier.
This is, of course, not

## Traces

Traces are a hierarchical set of data that contains information about a path of
a request as it follows a complex code/network path through the whole system, start to finish.
They're most useful in a microservice environment (distributed traces) where a request
can hop from service to service and measure data on the way about how it performed,
but it can equally be applied to a monolith and measure the performance of each function
it went through.
This type of observability is focused on the software rather than the hardware.

Each trace consists of a set of nested spans that measure how a particular
microservice (or function) performed in that particular instance.
Spans can contain numeric data like `duration` of the time it spent
at a particular stage, like a call to an Auth service, or an underlying database request.
They can also contain a context of the requrest, like which parameters were passed.
This way we get a view across the whole stack of services, and if any of them
stop performing well, we will instantly see which one it is.

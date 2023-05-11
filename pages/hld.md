---
layout: page
title: High level diagram
permalink: /hld
---



All services can be run locally in docker or in a k8s cluster.

Dispatcher is streaming live comments and submissions from Reddit
to the two corresponding services that simply save them to a database.
The grafana stack can be spinned up locally and OpenTelemetry is
sending logs, metrics and traces.

<pre class="mermaid">
    graph TD

    subgraph services-namespace[services namespace]
        dispatcher(dispatcher service) -->|comments| comment(comment-service)
        dispatcher(dispatcher service) -->|submissions| submission(submission-service)
        comment -->|comment| database(MongoDB)
        submission -->|submissions| database(MongoDB)
    end

    subgraph agent-namespace[agent namespace]
        otel[opentelemetry]
    end

    subgraph grafana-namespace[grafana namespace]

        otel ----> |metrics| prom[Prometheus]
        otel ----> |logs| loki[Loki]
        otel ----> |traces| tempo[Tempo]

    end

    services-namespace -->|MELT| otel

    reddit[Reddit API] .-> dispatcher

    classDef k8s-object fill:#326ce5,stroke:#fff,stroke-width:4px,color:#fff;
    classDef cluster fill:#fff,stroke:#bbb,stroke-width:2px,color:#326ce5;
    classDef edgeLabel background-color:#fff,font-size:9pt;

    class dispatcher,comment,submission,database,otel,tempo,loki,prom,grafana-admin,grafana-anonymous,ingress k8s-object;
    class reddit,user cluster;

</pre>

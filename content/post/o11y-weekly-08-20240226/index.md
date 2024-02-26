+++
author = "Oleh Pelekh"
title = "O11y Weekly - 2024-02-26"
date = "2024-02-26"
description = "Stay updated with this week's Observability Digest featuring articles on detecting unauthorized access with Observe's GeoIP, monitoring Windows pods on Amazon EKS using Prometheus and Grafana, proactively addressing security threats with New Relic APM, essential etcd metrics for Kubernetes cluster health from Datadog, and instrumenting Python applications for improved observability with OpenTelemetry."
tags = [
    "o11y"
]
categories = [
    "o11y-weekly"
]
draft = false
+++

- [Solving the Superman Problem: Observe offers GeoIP](https://www.observeinc.com/blog/observe-geoip-visualization/)

    This is an article about using Observe to detect unauthorized access to user accounts. 
    It discusses how to use Observe's Improbable Travel feature to identify login events that 
    are geographically impossible for a single user to perform.

- [Monitoring Windows pods with Prometheus and Grafana](https://aws.amazon.com/blogs/containers/monitoring-windows-pods-with-prometheus-and-grafana/)

    This article describes how to monitor Windows pods on Amazon EKS using Prometheus and Grafana. 

- [A deep dive into zero-day vulnerability alerts with New Relic APM](https://newrelic.com/blog/how-to-relic/a-deep-dive-into-zero-day-vulnerability-alerts-with-new-relic-apm)

    This article shows how New Relic empowers developers to be more proactive in identifying and 
    addressing security threats, especially against unknown vulnerabilities (zero-day attacks). 
    If you're a developer building applications and want to enhance your security posture without extensive scanning, 
    this article is worth reading.

- [Key metrics for monitoring etcd](https://www.datadoghq.com/blog/etcd-key-metrics/)

    This article from Datadog explains the key metrics you need to monitor to ensure the health and performance 
    of your etcd cluster, which is crucial for the smooth operation of Kubernetes clusters. 
    By understanding these metrics, you can detect and address issues like resource bottlenecks, 
    leader election problems, and performance degradation.

- [How to instrument your Python application using OpenTelemetry](https://grafana.com/blog/2024/02/20/how-to-instrument-your-python-application-using-opentelemetry/)

    This article explains how to add monitoring capabilities to your Python application using OpenTelemetry.
    If you're building Python applications and want to improve their observability for troubleshooting and performance 
    optimization, this article can be helpful.

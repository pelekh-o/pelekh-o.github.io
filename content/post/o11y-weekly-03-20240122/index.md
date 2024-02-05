+++
author = "Oleh P"
title = "O11y Weekly - 2024-01-22"
date = "2024-01-21"
description = "Explore Grafana's efforts to redefine observability pricing, alongside practical guides on monitoring Windows services with Amazon CloudWatch, managing telemetry overflow in Kubernetes, monitoring Kubernetes infrastructure with OpenTelemetry, and understanding the critical role of network load balancer monitoring for business continuity"
tags = [
    "o11y"
]
categories = [
    "o11y-weekly"
]
draft = false
+++

- [**Grafana Seeks to Correct Observability’s Historic ‘Terrible Job’**](https://thenewstack.io/grafana-seeks-to-correct-observabilitys-historic-terrible-job/)


    This article highlights Grafana's efforts to revamp observability pricing and accessibility. CEO Raj Dutt recognizes historical industry challenges in balancing value and cost, especially with growing data volumes.

- [**Monitoring Windows services with Amazon CloudWatch**](https://aws.amazon.com/blogs/mt/monitoring-windows-services-with-amazon-cloudwatch-2/)

    The article describes how to monitor Windows services on Amazon EC2 using CloudWatch for operational excellence, including steps to configure CloudWatch with the procstat plugin to collect met

- [**Managing telemetry data overflow in Kubernetes with resource quotas and limits**](https://www.mezmo.com/blog/managing-telemetry-data-overflow-in-kubernetes-with-resource-quotas-and-limits)

    The article explains how to manage telemetry data overflow in Kubernetes clusters using resource quotas and limits. These quotas and limits can be set for namespaces or pods to prevent telemetry data from causing resource issues and ensure important applications have resources during peak loads

- [**Monitoring Kubernetes infrastructure with OpenTelemetry**](https://newrelic.com/blog/how-to-relic/monitoring-kubernetes-infrastructure-with-opentelemetry)

    This New Relic blog explores using OpenTelemetry, not just for apps, but to monitor your Kubernetes infrastructure (nodes, pods, containers) too. They detail pros and cons, setup steps, and how to link this data with your application telemetry for deeper insights.

- [**Why network load balancer monitoring is critical**](https://graylog.org/post/why-network-load-balancer-monitoring-is-critical/)

    This Graylog article highlights the importance of monitoring network load balancers (NLBs) to ensure business continuity and prevent performance issues. It explains what NLBs are, their key components, common configurations, and the benefits of monitoring them to maintain optimal network traffic flow and prevent outages.
---
description: >-
  This article walks through how to configure Quality of Service for Gravitee v4
  APIs
---

# Quality of Service

## Introduction

When working with asynchronous APIs and/or event brokers, quality of service is important. Quality of service defines the guaranteed level of message delivery. For example, a quality of service of "none" means that a given message might be delivered zero, one, or several times. A quality of service of "at-most-once" means that a given message will be delivered zero or one times, with no duplication.

A higher quality of service could lead to lower system performance depending on the endpoint chosen. Please see the following table that describes the different levels of QoS:

<table><thead><tr><th width="223.5">Level</th><th>Description</th></tr></thead><tbody><tr><td>None</td><td>A given message might be delivered zero, one, or many times. This level allows high throughput and good performance but without guaranteed delivery. After failure or disconnection, the client will only receive messages sent after reconnection.</td></tr><tr><td>Auto (0 or N)</td><td>A given message might be delivered zero, one, or many times. This level allows a trade-off between performance and delivery guarantee. Delivery is highly dependent on the capabilities supported by the endpoint connector. In case of failure or disconnection, after reconnection the client will resume, if possible, from a previously saved state, although duplication of messages could potentially exist.</td></tr><tr><td>At-Most-Once (0 or 1)</td><td>A given message might be delivered zero times or once without any duplication. Depending on the capabilities of the entrypoint connector, performance could be degraded.</td></tr><tr><td>At-Least-Once (1 or N)</td><td>A given message is delivered once or many times. This level gives a good balance between guaranteed delivery and performance when compared to At-Most-Once, especially when the entrypoint connector is not able to resume message streams after failure.</td></tr></tbody></table>

The quality of service is set on the entrypoints. A given quality of service may or may not be supported by a given endpoint. Support also depends on the protocol used for the entrypoint. Please see the following table that outlines QoS compatibility:

<table><thead><tr><th width="134">Entrypoint</th><th width="126">MQTT endpoint</th><th width="122">MQTT Advanced Endpoint</th><th width="115">Kafka endpoint</th><th>Kafka Advanced endpoint</th></tr></thead><tbody><tr><td>HTTP POST</td><td>None<br>Auto</td><td>None<br>Auto</td><td>None<br>Auto</td><td>None<br>Auto</td></tr><tr><td>HTTP GET</td><td>Auto</td><td>Auto</td><td>Auto</td><td>Auto<br>At-Least-Once<br>At-Most-Once</td></tr><tr><td>SSE</td><td>None<br>Auto</td><td>None<br>Auto</td><td>None<br>Auto</td><td>None<br>Auto</td></tr><tr><td>SSE Advanced</td><td>None<br>Auto</td><td>None<br>Auto</td><td>None<br>Auto</td><td>None<br>Auto<br>At-Least-Once<br>At-Most-Once</td></tr><tr><td>WebSocket</td><td>None<br>Auto</td><td>None<br>Auto</td><td>None<br>Auto</td><td>None<br>Auto</td></tr><tr><td>Webhook</td><td>At-Least-Once<br>At-Most-Once</td><td>At-Least-Once<br>At-Most-Once</td><td>None<br>Auto</td><td>None<br>Auto<br>At-Least-Once<br>At-Most-Once</td></tr><tr><td>Webhook Advanced</td><td>At-Least-Once<br>At-Most-Once</td><td>At-Least-Once<br>At-Most-Once</td><td>None<br>Auto</td><td>None<br>Auto<br>At-Least-Once<br>At-Most-Once</td></tr></tbody></table>

## Setting quality of service for Gravitee v4 APIs

You can set quality of service levels with the `qos` object in the `entrypoints` object, as shown in the following example. See the Management API [`openapi.json`](https://apim-3-20-x-api.team-apim.gravitee.dev/management/openapi.json) for a list of possible `qos` values you can specify.

```json
"entrypoints": [
                {
                    "type": "sse",
                    "qos": "none",
                    "configuration": {
                        "heartbeatIntervalInMs": 5000,
                        "metadataAsComment": false,
                        "headersAsComment": false
                    }
                }
            ]
```

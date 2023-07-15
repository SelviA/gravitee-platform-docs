---
description: This page provides the technical details of the json-xml policy
---

# Template Policy - Rework Structure

{% hint style="warning" %}
**This feature requires** [**Gravitee's Enterprise Edition**](../../overview/introduction-to-gravitee-api-management-apim/ee-vs-oss.md)**.**
{% endhint %}

## Overview

Functional and implementation information for the json-xml policy is organized into the following sections:

* [Transformations](template-policy-rework-structure.md#transformations)
* [Configuration](template-policy-rework-structure.md#configuration)
* [Compatibility Matrix](template-policy-rework-structure.md#compatibility-matrix)
* [Errors](template-policy-rework-structure.md#errors)
* [Changelogs](template-policy-rework-structure.md#changelogs)

## Transformations

The `json-xml` policy transforms JSON payloads to XML before either sending the payload to the backend system or returning it to the client. To transform XML content to JSON, please see the `xml-json` policy.

{% tabs %}
{% tab title="Proxy API example" %}
{% hint style="info" %}
The proxy API example also applies to v2 APIs.
{% endhint %}

For proxy APIs, the JSON-to-XML policy is most commonly used for transforming JSON data before returning it to the client in the `response` phase.

For example, the Gravitee echo API returns a JSON response when a `GET` request is sent to [https://api.gravitee.io/echo](https://api.gravitee.io/echo). The response is formatted like so:

{% code title="Default response" %}
```json
{
    "bodySize": 0,
    "headers": {
        "Accept": "*/*",
        "Host": "api.gravitee.io",
        "User-Agent": "{{user-agent-info}}",
        "X-Gravitee-Request-Id": "{{generated-request-id}}",
        "X-Gravitee-Transaction-Id": "{{generated-trx-id}}",
        "accept-encoding": "deflate, gzip"
    },
    "query_params": {}
}
```
{% endcode %}

Adding a JSON-to-XML policy on the `response` phase for a proxy API will transform the response output to:

{% code title="Transformed response" %}
```xml
<root>
  <headers>
    <Accept>*/*</Accept>
    <Host>api.gravitee.io</Host>
    <User-Agent>{{user-agent-info}}</User-Agent>
    <X-Gravitee-Request-Id>{{generated-request-id}}</X-Gravitee-Request-Id>
    <X-Gravitee-Transaction-Id>{{generated-trx-id}}</X-Gravitee-Transaction-Id>
    <accept-encoding>deflate, gzip</accept-encoding>
  </headers>
  <query_params/>
  <bodySize>0</bodySize>
</root>
```
{% endcode %}
{% endtab %}

{% tab title="Message API example" %}
{% hint style="warning" %}
ONLY INCLUDE THIS SECTION IF MESSAGES ARE SUPPORTED. Otherwise, use a single example section with one of the following two hints:
{% endhint %}

{% hint style="warning" %}
This example will work for [v2 APIs and v4 proxy APIs.](../../overview/gravitee-api-definitions-and-execution-engines.md)

Currently, this policy can **not** be applied at the message level.
{% endhint %}

{% hint style="warning" %}
This example will work for [v2 APIs, v4 proxy APIs, and for the initial connection request of v4 message APIs](../../overview/gravitee-api-definitions-and-execution-engines.md).

Currently, this policy can **not** be applied at the message level.
{% endhint %}

**Otherwise, provide a message example:**

For message APIs, the JSON-to-XML policy is used to transform the message `content` in either the `publish` or `subscribe` phase.

For example, you can create a message API with an HTTP GET entrypoint and a mock endpoint. Suppose the endpoint is configured to return the message content as follows:

{% code title="Default message" %}
```json
{ \"id\": \"1\", \"name\": \"bob\", \"v\": 2 }
```
{% endcode %}

Adding a JSON-to-XML policy on the subscribe phase will return the payload to the client via the HTTP GET entrypoint as follows (the number of messages returned will vary by the number of messages specified in the Mock endpoint):

{% code title="Transformed messages" %}
```xml
{
    "items": [
        {
            "content": "<root><id>1</id><name>bob</name><v>2</v></root>",
            "id": "0"
        },
        {
            "content": "<root><id>1</id><name>bob</name><v>2</v></root>",
            "id": "1"
        },
        {
            "content": "<root><id>1</id><name>bob</name><v>2</v></root>",
            "id": "2"
        },
        {
            "content": "<root><id>1</id><name>bob</name><v>2</v></root>",
            "id": "3"
        }
    ],
    "pagination": {
        "nextCursor": "3"
    }
}
```
{% endcode %}

The output is the typical return structure for the HTTP GET entrypoint with each message `content` field transformed from JSON to XML.

{% hint style="info" %}
For the HTTP GET entrypoint specifically, the entire payload can be returned as XML by adding the `"Accept": "application/json"` header to the GET request. In this case, the message content is transformed into [CDATA](https://www.w3.org/TR/REC-xml/#sec-cdata-sect) and is therefore not treated as marked-up content for the purpose of the entrypoint using the `Accept` header.
{% endhint %}
{% endtab %}
{% endtabs %}

## Configuration

Policies can be added to flows that are assigned to an API or to a plan. Gravitee supports configuring policies through the Policy Studio in the Management Console or interacting directly with the Management API.

{% tabs %}
{% tab title="Management Console" %}
<mark style="color:yellow;">We should wait to make these once the v4 Policy Studio is finalized</mark>
{% endtab %}

{% tab title="Managment API" %}
When using the Management API, policies are added as flows either directly to an API or to a plan. To learn more about the structure of the Management API, check out the [reference documentation here.](../management-api-reference/)

{% code title="Sample Configuration" %}
```json
{
  "name": "Custom name",
  "description": "Converts data from JSON to XML",
  "policy": "json-xml",
  "configuration": {
    "scope": "RESPONSE",
    "rootElement": "root"
  }
}
```
{% endcode %}
{% endtab %}
{% endtabs %}

### Reference

{% hint style="info" %}
The default option is indicated by **bold** font.
{% endhint %}

<table data-full-width="true"><thead><tr><th width="140">Property</th><th width="104" data-type="checkbox">Required</th><th width="195">Description</th><th width="74" data-type="select">Type</th><th width="120">Options</th></tr></thead><tbody><tr><td>name</td><td>false</td><td>Provide a descriptive name for your policy</td><td></td><td>N/a</td></tr><tr><td>description</td><td>false</td><td>Provide a description for your policy</td><td></td><td>N/a</td></tr><tr><td>rootElement</td><td>true</td><td>XML root element name that encloses content.</td><td></td><td>N/a<br><strong>root</strong></td></tr><tr><td>scope</td><td>true</td><td>The execution scope</td><td></td><td><strong>REQUEST</strong> RESPONSE</td></tr></tbody></table>

### Phases

Policies can be applied to the request or the response of a Gateway API transaction. The request and response are broken up into phases that depend on the [Gateway API version](../../overview/gravitee-api-definitions-and-execution-engines.md). Each policy has different compatibility with the available phases as described in the [Policy Studio documentation](../../guides/policy-design/).

{% tabs %}
{% tab title="v4 API definition" %}
v4 APIs have the following phases:

* `onRequest`: This phase is executed before invoking the backend services for both proxy and message APIs. Policies can act on the headers and the content for proxy APIs.
* `onMessageRequest`: This phase occurs after the `onRequest` phase and allows policies to act on each incoming message before being sent to the backend service. This only applies to message APIs.
* `onResponse`: This phase is executed after invoking the backend services for both proxy and message APIs. Policies can act on the headers and the content for proxy APIs.
* `onMessageResponse`: This phase after the `onResponse` phase and allows policies to act on each outgoing message before being sent to the client application. This only applies to message APIs.

This policy is compatible with the following v4 API phases:

<table data-full-width="false"><thead><tr><th width="138" data-type="checkbox">onRequest</th><th width="134" data-type="checkbox">onResponse</th><th data-type="checkbox">onMessageRequest</th><th data-type="checkbox">onMessageResponse</th></tr></thead><tbody><tr><td>true</td><td>true</td><td>true</td><td>true</td></tr></tbody></table>
{% endtab %}

{% tab title="v2 API definition" %}
v2 APIs have the following phases:

* `onRequest`: This phase only allows policies to work on request headers. It never accesses the request body.
* `onRequestContent`: This phase always occurs after the `onRequest` phase. It allows policies to work at the content level and access the request body.
* `onResponse`: This phase only allows policies to work on response headers. It never accesses the response body.
* `onResponseContent`: This phase always occurs after the `onResponse` phase. It allows policies to work at the content level and access the response body.

This policy supports the following phases:

<table><thead><tr><th width="134" data-type="checkbox">onRequest</th><th width="144" data-type="checkbox">onResponse</th><th width="191" data-type="checkbox">onRequestContent</th><th data-type="checkbox">onResponseContent</th></tr></thead><tbody><tr><td>false</td><td>false</td><td>true</td><td>true</td></tr></tbody></table>
{% endtab %}
{% endtabs %}

## Compatibility matrix

The [changelog for each version of APIM](../../releases-and-changelog/changelog/) provides a list of policies included in the default distribution. The chart below summarizes this information in relation to the `json-xml` policy.

<table data-full-width="false"><thead><tr><th width="161.33333333333331">Plugin Version</th><th width="242">Supported APIM versions</th><th>Included in APIM default distribution</th></tr></thead><tbody><tr><td>2.2</td><td>>=3.20</td><td>>=3.21</td></tr><tr><td>2.1</td><td>^3.0</td><td>>=3.0 &#x3C;3.21</td></tr><tr><td>2.0</td><td>^3.0</td><td>N/a</td></tr></tbody></table>

## Errors

### Error decoding

<table data-full-width="true"><thead><tr><th width="210">Phase</th><th width="171">HTTP status code</th><th width="244">Error template key</th></tr></thead><tbody><tr><td>onRequest</td><td><code>400</code></td><td><strong>JSON_INVALID_PAYLOAD:</strong> Request payload cannot be transformed properly to XML</td></tr><tr><td>onResponse</td><td><code>500</code></td><td><strong>JSON_INVALID_PAYLOAD:</strong><br>Response payload cannot be transformed properly to XML</td></tr><tr><td>onMessageRequest</td><td><code>400</code></td><td><strong>JSON_INVALID_MESSAGE_PAYLOAD:</strong> Incoming message cannot be transformed properly to XML</td></tr><tr><td>onMessageResponse</td><td><code>500</code></td><td><strong>JSON_INVALID_MESSAGE_PAYLOAD:</strong> Outgoing message cannot be transformed properly to XML</td></tr></tbody></table>

### Nested objects

To limit the processing time in the case of a nested object, the default max depth of a nested object has been set to 1000. This default value can be overridden using the environment variable `gravitee_policy_jsonxml_maxdepth`.

## Changelogs

<details>

<summary>2.2</summary>

#### What's New?

* Blazingly fast
* Full ChatGPT and Neuralink integration for quick API mastery

#### Bug fixes

* Fix crashes related to nested objects

#### Breaking Changes

* Only supports APIM versions >4.0

</details>

<details>

<summary>2.1</summary>

#### What's New?

* Blazingly fast
* Full ChatGPT and Neuralink integration for quick API mastery

#### Bug fixes

* Fix crashes related to nested objects

#### Breaking Changes

* Only supports APIM versions >4.0

</details>
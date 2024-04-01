---
description: This article walks through how to configure v4 API entrypoints
---

# Entrypoint Configuration

## Introduction

In Gravitee, Gateway entrypoints define the protocol and configuration settings by which the API consumer accesses the Gateway API. The Gateway entrypoint dictates how the backend API is exposed through the Gateway.

After you've created your Gateway API and selected your entrypoint(s), you can configure them on the **API** page of the Developer Portal.  This article walks through that process for configuring both v4 Message API entrypoints and v4 Proxy API entrypoints.

## Configure v4 message API entrypoints

{% hint style="warning" %}
**Enterprise only**

As of Gravitee 4.1, the ability to create APIs with message API entrypoints is an Enterprise Edition capability. To learn more about Gravitee Enterprise Edition and what's included in various enterprise packages, please:

* [Refer to the EE vs OSS documentation](../../../overview/ee-vs-oss/)
* [Book a demo](https://app.gitbook.com/o/8qli0UVuPJ39JJdq9ebZ/s/rYZ7tzkLjFVST6ex6Jid/)
* [Check out the pricing page](https://www.gravitee.io/pricing)
{% endhint %}

v4 APIs support the following entrypoints:

* **HTTP GET:** Exposes a backend resource via the HTTP GET method
* **HTTP POST:** Exposes a backend resource via the HTTP POST method
* **WebSocket:** Exposes a backend resource via a WebSocket stream
* **Webhook:** Exposes a backend resource via a Webhooks subscription
* **Server-sent events (SSE):** Exposes a backend resource via a unidirectional SSE stream

To access entrypoint configuration, go to the **API** page in the Developer Portal and select your API. Then, under **Entrypoints,** select **General**.

Here, you can choose to enable or disable virtual hosts. Enabling virtual hosts requires you to define your virtual host and optionally enable override access.

<figure><img src="../../../.gitbook/assets/virtual host_on message.png" alt=""><figcaption><p>v4 message API entrypoint configuration</p></figcaption></figure>

Next, depending on which entrypoint(s) your API utilizes, specific entrypoint configuration may differ. Please refer to the following sections for the configuration details of each specific entrypoint.

<details>

<summary>HTTP GET</summary>

If you chose **HTTP GET** as an entrypoint, you will be brought to a page where you can configure:

* **Limit messages count:** Defines the maximum number of messages to retrieve via HTTP GET. The default is 500. To set a custom limit, enter a numeric value in the **Limit messages count** text field.
* **Limit messages duration:** Defines the maximum duration, in milliseconds, to wait to retrieve the expected number of messages (see **Limit messages count**). To set a custom limit, enter a numeric value in the **Limit messages duration** text field. The actual number of retrieved messages could be less than expected if maximum duration is reached before all messages are retrieved.
* **HTTP GET permissions:** Allow or disallow **Allow sending messages headers to client in payload** and **Allow sending messages metadata to client in payload** by toggling these actions ON or OFF.
* **Quality of service:** Use the drop-down menu to choose between the available options. QoS compatibility is detailed [here](quality-of-service.md).

</details>

<details>

<summary>HTTP POST</summary>

If you chose **HTTP POST** as an entrypoint, you will be brought to a page where you can configure:

* **HTTP POST permissions:** Allow or disallow add request Headers to the generated message by toggling **Allow add request Headers to the generated message** ON or OFF.
* **Quality of service:** Use the drop-down menu to choose between the available options. QoS compatibility is detailed [here](quality-of-service.md).

</details>

<details>

<summary>WebSocket</summary>

If you chose **WebSocket** as an entrypoint, you will be brought to a page where you can configure:

* **Publisher configuration:** Choose to either enable or disable the publication capability by toggling **Enable the publication capability** ON or OFF. Disabling it assumes that the application will never publish any message.
* **Subscriber configuration:** Choose to enable or disable the subscription capability by toggling **Enable the subscription capability** ON or OFF. Disabling it assumes that the application will never receive any message.
* **Quality of service:** Use the drop-down menu to choose between the available options. QoS compatibility is detailed [here](quality-of-service.md).

</details>

<details>

<summary>Webhook</summary>

If you chose **Webhook** as an entrypoint, you will be brought to a page where you can configure:

* **HTTP Options**
  * **Connect timeout:** The maximum time, in milliseconds, to connect to the Webhook. Either enter a numeric value or use the arrows to the right of the text field.
  * **Read timeout:** The maximum time, in milliseconds, allotted for the Webhook to complete the request (including response). Either enter a numeric value or use the arrows to the right of the text field.
  * **Idle timeout:** The maximum time, in milliseconds, a connection will stay in the pool without being used. Once this time has elapsed, the unused connection will be closed, freeing the associated resources. Either enter a numeric value or use the arrows to the right of the text field.
* **Proxy Options**
  * Use the drop-down menu to select a proxy option: **No proxy**, **Use proxy configured at system level**, or **Use proxy for client connections**.
    * If you chose **Use proxy for client connections**, define the following:
      * **Proxy type:** Choose between **HTTP**, **SOCKS4** and **SOCKS5**. A [**SOCKS proxy**](https://hailbytes.com/how-to-use-socks4-and-socks5-proxy-servers-for-anonymous-web-browsing/) is a type of proxy server that uses the SOCKS protocol to tunnel traffic through an intermediary server.
      * **Proxy host:** Enter your proxy host in the text field.
      * **Proxy port:** Enter your proxy port in the text field.
      * (Optional) **Proxy username:** Enter your proxy username in the text field.
      * (Optional) **Proxy password:** Enter your proxy password in the text field.
* **Quality of service:** Use the drop-down menu to choose between the available options. QoS compatibility is detailed [here](quality-of-service.md).
* **Enable Dead Letter Queue:** Toggle **Dead Letter Queue** ON to define an external storage where each unsuccessfully pushed message will be stored and configure a replay strategy:
  * Use the drop-down menu to select a pre-existing and supported endpoint or endpoint group to use for the DLQ.

**DLQ Configuration using the API definition**

To configure DLQs and secure callbacks for your Webhook via the API definition:

**1. Set up DLQ**

To enable DLQ, declare another endpoint that will be used to configure the DLQ object in the Webhook entrypoint definition:

```json
{
    "type": "webhook-advanced",
    "dlq": {
        "endpoint": "dlq-endpoint"
    },
    "configuration": {}
}
```

The endpoint used for the dead letter queue:

* Must support PUBLISH mode
* Should be based on a broker that can persist messages, such as Kafka

Once configured and deployed, any message rejected with a 4xx error response by the Webhook will be automatically sent to the DLQ endpoint and the consumption of messages will continue.

**2. Combining DLQ with the retry policy**

If you set up a DLQ, you can utilize the Gravitee Retry policy in order to "retry" delivery of undelivered messages from the DLQ. For more information on the Retry policy, please refer to the Retry policy reference.

**3. Set up secure callbacks**

Callbacks can be secured using basic authentication, JWT, and OAuth2.

To secure a callback, add an `auth` object to the configuration section of your API definition. The following example shows how to configure basic authentication:

```json
{
    "configuration": {
        "entrypointId": "webhook-advanced",
        "callbackUrl": "https://example.com",
        "auth": {
            "type": "basic",
            "basic": {
                "username": "username",
                "password": "a-very-secured-password"
            }
        }
    }
}
```

To use JWT, the `auth` object should look like this:

```json
        "auth": {
            "type": "token",
            "token": {
                "value": "eyJraWQiOiJk..."
            }
        }
```

To use OAuth2, the `auth` object should look like this:

```json
        "auth": {
            "type": "oauth2",
            "oauth2": {
                "endpoint": "https://auth.gravitee.io/my-domain/oauth/token",
                "clientId": "a-client-id",
                "clientSecret": "a-client-secret",
                "scopes": ["roles"]
            }
        }
```

</details>

<details>

<summary>Server-sent events</summary>

If you chose **SSE** as an entrypoint, you will be brought to a page where you can configure:

* **Heartbeat intervals:** Define the interval in which heartbeats are sent to the client by entering a numeric value into the **Define the interval in which heartbeats** **are sent to client** text field or by using the arrow keys. Intervals must be greater than or equal to 2000ms. Each heartbeat will be sent as an empty comment: `''`.
* Choose to allow or disallow sending message metadata to the client as SSE comments by toggling **Allow sending messages metadata to client as SSE comments** ON or OFF.
* Choose to allow or disallow sending message headers to the client as SSE comments by toggling **Allow sending messages headers to client as SSE comments** ON or OFF.
* **Quality of service:** Use the drop-down menu to choose between the available options. QoS compatibility is detailed [here](quality-of-service.md).

</details>

You can also add an entrypoint to your API by clicking **Add an entrypoint.** From here, you must configure the entrypoint using the details specific to that entrypoint (see expandable sections above).

When you are done configuring your entrypoints, make sure to select **Save changes.**

## Configure v4 Proxy API entrypoints

To alter v4 Proxy API entrypoints, select your API, and then select **General** from the **Entrypoints** category in the left-hand nav.&#x20;

<figure><img src="../../../.gitbook/assets/virtual host_on (1).png" alt=""><figcaption><p>v4 proxy API entrypoint configuration</p></figcaption></figure>

From here, you can:&#x20;

* Alter existing entrypoints by changing the context path
* Add a new entrypoint by clicking **Add context path** and then adding a new context path
* Delete existing entrypoints by clicking the <img src="../../../.gitbook/assets/Screen Shot 2023-07-18 at 10.51.56 AM.png" alt="" data-size="line"> icon associated with the entrypoint that you want to delete
* Choose to enable or disable virtual hosts. Enabling virtual hosts requires you to define your virtual host and optionally enable override access.

When you are done, make sure to redeploy the API for your changes to take effect.

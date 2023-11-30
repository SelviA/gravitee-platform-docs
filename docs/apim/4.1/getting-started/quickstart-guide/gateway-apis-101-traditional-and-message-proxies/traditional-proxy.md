---
description: Use Gravitee to proxy your backend API servers
---

# Traditional Proxy

## Overview

A traditional proxy is the classic API Gateway use case. The Gateway will connect with the client and the backend service using the same protocol.

<img src="../../../.gitbook/assets/file.excalidraw (9).svg" alt="Traditional proxy example" class="gitbook-drawing">

Let's continue with the API creation wizard to see how easily a traditional proxy can be created with Gravitee.

<figure><img src="../../../.gitbook/assets/Screenshot 2023-11-09 at 7.52.06 PM.png" alt=""><figcaption><p>Creating a tradtional proxy</p></figcaption></figure>

> * [x] Select **Proxy Upstream Protocol**
> * [x] Click **Select my API Architecture** to continue

## Gateway entrypoints and endpoints

The next step is configuring how the Gateway will communicate with clients and backend servers. This is done through Gateway entrypoints and endpoints:

* **Gateway entrypoint:** Defines the protocol and configuration settings by which the API consumer communicates with the Gateway. In other words, the Gateway entrypoint dictates how the backend API is exposed externally through the Gateway.&#x20;
* **Gateway endpoint:** Defines the protocol and configuration settings by which the Gateway API will fetch data/functionality from, or post data to, the backend API server.

<img src="../../../.gitbook/assets/file.excalidraw (10).svg" alt="Gateway entrypoints and endpoints" class="gitbook-drawing">

### Entrypoints&#x20;

For traditional proxies, the Gateway entrypoint will use the same protocol as your API server. This keeps entrypoint configuration very simple as the only requirement is one or more context-paths. A context-path is the unique route of the Gateway API.

There are two important items to note about the context-path:

* The context-path does not include the fully qualified domain name of the Gateway.&#x20;
* The context-path is stripped before the request is forwarded to the backend service.

<details>

<summary>Example</summary>

Let's say we provided a context-path of `/qs-traditional-api`. Once the API is fully configured and deployed to the Gateway, API consumers can reach the API at `https://apim-gateway-server/qs-traditional-api`. Now, if the consumer sends the following HTTP request to the Gateway:

```
GET https://apim-gateway-server/qs-traditional-api/orders
```

Then the backend API server will receive the following request:

```
GET https://backend-api-server/orders
```

</details>

<figure><img src="../../../.gitbook/assets/Screenshot 2023-11-19 at 8.17.39 PM (2).png" alt=""><figcaption><p>Provide a context-path</p></figcaption></figure>

> * [x] Provide a context-path
> * [x] Select **Validate my entrypoints** to move on to endpoints configuration

### Endpoints

For traditional proxies, there are significantly more configuration options for the Gateway endpoints than entrypoints. However, we will only focus on a few of the options since most of them are standard HTTP configuration options.

<figure><img src="../../../.gitbook/assets/Screenshot 2023-11-10 at 12.21.16 PM.png" alt=""><figcaption><p>Endpoint configuration</p></figcaption></figure>

> * [x] Input `https://api.gravitee.io/echo` as your **Target url**

#### Target URL

The first and most important option is the **Target url**. This is the root-level URL of your backend API server. Continuing our previous [entrypoint example](traditional-proxy.md#example), the target URL would be `https://backend-api-server/`. By default, all resources under this URL would be accessible through the Gateway.&#x20;

<details>

<summary>Example continued</summary>

Let's imagine your backend API server, `https://backend-api-server/`, has two resources: `orders` and `customers`. After setting the Gateway API's target URL to `https://backend-api-server/`, an API consumer would send API requests to the following URLs to reach these resources through the Gateway:&#x20;

* Access the `orders/1` resource at `https://apim-gateway-server/unique-path/orders/1`
* Access the `customers/1` resource at `https://apim-gateway-server/unique-path/customers/1`

</details>

#### Additional endpoint options

As previously mentioned, the majority of the remaining configuration options are standard HTTP configuration options that you would generally pass as HTTP request headers such as managing connection timeouts, pipelining, redirects, etc. We will leave the default value for all of these settings.

{% hint style="info" %}
**SSL Options**

It is worth clarifying that the SSL options shown are for the connection between the Gateway and your backend server. Configuring a custom truststore and keystore here will have no impact on client connections to the Gateway. mTLS between clients and the Gateway are [configured at the Gateway level](../../configuration/the-gravitee-api-gateway/environment-variables-system-properties-and-the-gravitee.yaml-file.md), not the API level.
{% endhint %}

#### Set your Target URL

For this guide, you are using `https://api.gravitee.io/echo` as your Target URL, and therefore, your backend service. This is a very simple public API server that, as the name suggests, echoes back some basic information about your API request like the headers and the size of the request body. Feel free to test out the endpoint directly in your terminal or your browser.

<figure><img src="../../../.gitbook/assets/Screenshot 2023-11-13 at 6.20.00 PM.png" alt=""><figcaption><p>Finish endpoints configuration</p></figcaption></figure>

> * [x] Scroll all the way down and select **Validate my endpoints** to continue to security

## Security

The next step is to configure your API security with plans. In APIM, a plan provides a service and access layer on top of your APIs specifying access limits, subscription validation modes, and other configurations to tailor it to a specific subset of API consumers. All APIs require one or more plans.

We will be focusing on plans in the next part of the Quickstart Guide. So for now, leave the default keyless plan.

<figure><img src="../../../.gitbook/assets/Screenshot 2023-11-13 at 12.30.46 PM.png" alt=""><figcaption><p>Gateway API security</p></figcaption></figure>

> * [x] Leave defaults and select **Validate my plans** to continue to the final step

{% hint style="danger" %}
By default, a keyless plan provides unrestricted access to your backend services. If you’re deploying an API to the Gateway that proxies sensitive information, ensure it does not include a keyless plan.\
\
For production Gateways, keyless plans can be disabled entirely.
{% endhint %}

## Summary

The final step to creating an API is to review and then save your configuration. The API creation wizard presents you with two options:

* **Save API:** This option will save your API but it will not be available on the Gateway. This option is useful if you'd like to complete some more advanced configuration (e.g. adding policies) before starting the API on the Gateway.&#x20;
* **Save & Deploy API:** This option will save your API and immediately start it on the Gateway.

<figure><img src="../../../.gitbook/assets/Screenshot 2023-11-19 at 8.18.01 PM.png" alt=""><figcaption><p>Gateway API summary page</p></figcaption></figure>

> * [x] Select **Save & Deploy API** so we can begin testing immediately

## Manage your API

You will be greeted with a screen confirming the creation of your new API with several shortcuts to help you start managing your API.

<figure><img src="../../../.gitbook/assets/Screenshot 2023-11-16 at 12.51.12 PM.png" alt=""><figcaption><p>API creation confirmation</p></figcaption></figure>

> * [x] Select **Open my API in API Management** to see how to manage your API

This will take you straight to the **General Info** page that contains high-level metadata about your API as well as important actions for managing your API in the **Danger Zone**.

<details>

<summary>Danger Zone Deep Dive</summary>

The **Danger Zone** should be self-descriptive. Be careful with these actions in production.

Each of these actions alters the state of your API. Below is a quick rundown of the different actions. Some of these may not make sense until you complete the entire Quickstart guide so feel free to come back to this later.

* **Stop the API/Start the API:** This action behaves like a toggle, stopping an active API or starting an inactive API. When stopped, all requests to API will result in the client receiving an HTTP `404 Not Found` response status code.
* **Publish the API/Unpublish the API:** This action behaves like a toggle, publishing an unpublished API or unpublishing a published API. Publishing makes the API visible to members in the Developer Portal (also commonly referred to as an API catalog).
* **Make Public/Make Private:** This action behaves like a toggle but only impacts published APIs. By default, published APIs can only be seen in the Developer Portal by members of that API. Making a published API public allows anybody with access to the Developer Portal to see the API.
* **Deprecate:** This action permanently blocks any new subscription requests. However, active subscriptions will continue to function unless the API is stopped or deleted.
* **Delete:** This action permanently deletes an API. To delete an API, it must be stopped and all plans must be deleted.

</details>

From this page, you can manage every aspect of your Gateway API by selecting different tabs on the inner sidebar. We'll be diving into some of these options later in the Quickstart guide.

<figure><img src="../../../.gitbook/assets/Screenshot 2023-11-19 at 8.21.00 PM.png" alt=""><figcaption><p>API General Info page</p></figcaption></figure>

## Test your API

Your first API is now started on the Gateway. And since we are using a keyless plan, you can immediately test it by opening your terminal and sending the request below after modifying the relevant portions:

* `your-gateway-server` should be replaced with the fully qualified domain name of your Gateway's server. Remember, your Gateway will be on a different domain than the Console UI. For example, the default local docker deployment has the Console UI on `localhost:8084` and the Gateway on `localhost:8082`.
* `your-context-path` should be replaced by the context-path of the Gateway API you just deployed. You can always find the context-path under **Entrypoints**.

{% hint style="warning" %}
Ensure you use the proper protocol! For example, the default local docker installation of APIM would use `http` instead of `https` as SSL must be manually enabled.&#x20;
{% endhint %}

{% code overflow="wrap" %}
```sh
curl -X GET -i "https://your-gateway-server/your-context-path" -d 'APIM Quickstart Guide=Hello World'
```
{% endcode %}

You should receive the HTTP **`200 OK`** success status response code along with your headers echoed back and a `"bodySize":33` in the response body.

{% hint style="success" %}
Congrats! You have successfully deployed your first API to the Gateway and sent your first request!
{% endhint %}

## Next Steps

You should now have a basic understanding of Gravitee APIM's most fundamental concept: Gateway APIs. The Quickstart guide will now build on that knowledge by diving into the real power of APIM: Plans and Policies.

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><strong>Plans and Policies 101</strong></td><td></td><td><a href="../plans-and-policies-101.md">plans-and-policies-101.md</a></td></tr></tbody></table>

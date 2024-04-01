---
description: >-
  This article walks through how to understand and edit your v2 API's general
  settings
---

# General Info Settings

{% hint style="info" %}
**v4 vs v2 API configuration**

The Info settings configuration is the same for both v2 and v4 APIs, except for the API Quality section. As of Gravitee APIM 4.0, only v2 APIs support the API Quality feature.
{% endhint %}

## Introduction

Every API in Gravitee has general settings that can be viewed and altered on the **Info** page of an API's **General** section.

## Understanding and editing your v2 API's general settings

To access your API's **Info** page, click on **APIs** in the left nav, select your API, then click on **Info** in the **General** section of the inner left nav. The **Info** page is comprised of three main areas:

* **General details**
  * Name
  * Description
  * API picture
  * API background
  * Owner and creation information
  * The ability to export your API definition, import a new API definition to update your API, duplicate your API, and promote your API
* **API Quality**: This section describes how well your API conforms to set API quality rules. For more information on the Gravitee API Quality feature, please refer to the [API Quality documentation](../../api-measurement-tracking-and-analytics/using-the-api-quality-feature.md).
* **Danger Zone:** this section includes access to mission-critical (and potentially dangerous) actions:
  * **Start the API**: this will deploy the API to all Gateways, or the Gateways specified using [Sharding tags](../../../getting-started/configuration/the-gravitee-api-gateway/configure-sharding-tags-for-your-gravitee-api-gateways.md)
  * **Publish the API**: this will publish the API to the Developer Portal
  * **Make Public**: this will make the API public so that everybody can see it
  * **Delete**: this will delete the API

Any time you make a change to your API, you will need to select the **Save** icon at the bottom of the screen.

---
description: >-
  Gravitee 101 - Learn all the fundamentals to managing your APIs and
  message/event brokers in 30 minutes or less
layout:
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Quickstart Guide

Welcome to the Gravitee API Management (APIM) Quickstart Guide! This guide uses a hands-on approach to quickly introduce you to the core concepts of APIM.

These guides will switch between explaining APIM concepts and directing you to complete actions inside of your APIM instance. To make sure you don't miss any steps, all required actions are listed with an in-product image and instructions that follow the format below:

> * [x] Select **UI element**&#x20;
> * [x] Enter your name under **UI element**

## Prerequisites

Before getting started, you'll need:

1. Basic familiarity with web APIs and/or message brokers
2. Gravitee APIM 4.0 or later up and running

{% hint style="info" %}
If you are new to both web APIs and message brokers, we recommend taking a look at the [Gravitee Essentials guide](https://documentation.gravitee.io/platform-overview/gravitee-essentials/overview) before continuing.
{% endhint %}

The easiest way to start using Gravitee is to register for a [free enterprise trial](../install-guides/free-trial.md). This is Gravitee's SaaS offering and grants you full access to APIM's enterprise features.

If you prefer and/or are required to manage your own installations, check out our [APIM install guides](../install-guides/) for install options to run APIM locally or in your own cloud infrastructure. If you don't have a strong preference, [Quick Install with Docker Compose](../install-guides/install-on-docker/quick-install-with-docker-compose.md) is the fastest self-managed installation for most users.

{% hint style="warning" %}
If you are mostly interested in managing message/event brokers, we highly recommend signing up for the free trial, as an enterprise license is required for all message broker functionality.
{% endhint %}

Regardless of how APIM is deployed, the next step is to access the APIM Console. The APIM Console is the easiest way to manage all of your APIs and the configuration for your Gravitee Gateway.

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><strong>Access APIM Console: Enterprise trial</strong></td><td>How to access the APIM Console in an enterprise trial</td><td></td><td><a href="./#access-apim-console-enterprise-trial">#access-apim-console-enterprise-trial</a></td></tr><tr><td><strong>Access APIM Console: Self-managed installation</strong></td><td>How to access the APIM Console in a self-managed installation</td><td></td><td><a href="./#access-apim-console-self-managed-installation">#access-apim-console-self-managed-installation</a></td></tr></tbody></table>

## Access APIM Console: Enterprise trial

To start an enterprise trial, follow these steps:

1. Navigate to [Gravitee Cockpit ](https://cockpit.gravitee.io/)to register
2. Fill out and submit the registration form
3. Walk through the setup guide to initialize your enterprise trial. In the step shown below, make sure you select **Quick setup**.

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-22 at 11.07.51 AM.png" alt=""><figcaption><p>Starting an enterprise trial</p></figcaption></figure>

> * [x] Register for the free trial
> * [x] Confirm your email
> * [x] Complete the setup, ensuring you select **Quick setup** on the second step

After you complete registration and your enterprise trial has initialized, you will receive an email with a link to access Gravitee Cockpit. Gravitee Cockpit is an environment management solution and the “homepage” for your entire Gravitee platform.

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-13 at 4.50.53 PM.png" alt=""><figcaption><p>Cockpit homescreen</p></figcaption></figure>

> * [x] Access Gravitee Cockpit from the registration email
> * [x] After initialization is complete, access the APIM Console by selecting either of the **Access API Management** buttons (in the red boxes in the image above)

This will take you to your APIM Console homescreen, which should look similar to the following:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-13 at 4.56.10 PM.png" alt=""><figcaption><p>APIM homescreen</p></figcaption></figure>

{% hint style="success" %}
With access to the APIM Console, you'll be ready to dive straight into the Quickstart Guide. You should complete the 101 guides in order, as they build upon each other.
{% endhint %}

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th><th data-hidden data-card-cover data-type="files"></th></tr></thead><tbody><tr><td></td><td>Gateway APIs 101</td><td></td><td><a href="gateway-apis-101-traditional-and-message-proxies/">gateway-apis-101-traditional-and-message-proxies</a></td><td><a href="../../.gitbook/assets/101_course.png">101_course.png</a></td></tr></tbody></table>

## Access APIM Console: Self-managed installation

How you access the APIM Console in a self-managed installation depends on your installation method and covered in that method's installation guide. The example provided below is for a Docker installation, but is similar to any self-managed installation.

For the default local Docker installation, navigate to [`http://localhost:8084`](http://localhost:8084/) in your browser, and you will be greeted with the following screen:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-02 at 12.19.25 PM.png" alt=""><figcaption><p>APIM Console login screen</p></figcaption></figure>

> * [x] Navigate to [`http://localhost:8084`](http://localhost:8084/) in your browser

For a new installation, the default login is `admin` for both **Username** and **Password**. Logging in will take you to your APIM Console homescreen, which should look similar to this:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-02 at 12.20.36 PM.png" alt=""><figcaption><p>APIM Console Dashboard</p></figcaption></figure>

> * [x] Log in to the APIM Console using `admin` for both **Username** and **Password**

{% hint style="success" %}
With access to the APIM Console, you'll be ready to dive straight into the Quickstart Guide. You should complete the 101 guides in order, as they build upon each other.
{% endhint %}

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th><th data-hidden data-card-cover data-type="files"></th></tr></thead><tbody><tr><td></td><td>Gateway APIs 101</td><td></td><td><a href="gateway-apis-101-traditional-and-message-proxies/">gateway-apis-101-traditional-and-message-proxies</a></td><td><a href="../../.gitbook/assets/101_course.png">101_course.png</a></td></tr></tbody></table>

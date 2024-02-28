---
description: >-
  This section of the documentation covers how to administer your users and your
  Gravitee platform.
---

# Administration

### Introduction

Gravitee offers a robust set of platform and user administration capabilities. In this section, we will cover:

* Administering organizations and environments
* Administering users and user groups

### Organizations

In Gravitee, **Organizations** reflect a logical part of your company in a way that makes the most for your setup. For example, an organization could be a region or business unit.

In the context of an APIM installation, it is the level at which shared configurations for environments are managed, such as:

* Users
* Roles
* Identity providers
* Notification templates

Gravitee Organizations can include multiple environments.

#### Managing platform access

As a part of Organization administration, Gravitee offers multiple manners of managing and controlling access to the Gravitee platform. This is done by configuring Identity providers and login/registration settings.

{% hint style="info" %}
**This is different than Gravitee Access Management**

This should _not_ be confused with Gravitee Access Management, which is a fully-featured Identity and Access Management solution that is used for controlling access to applications and APIs. To learn more about the Access Management product, please refer to the [Gravitee Access Management documentation](https://app.gitbook.com/o/8qli0UVuPJ39JJdq9ebZ/s/hbYbONLnkQLHGL1EpwKa/).
{% endhint %}

### Environments

In Gravitee, **Environments** are flexible and act as the workspace in which users can manage their APIs, applications, and subscriptions. An environment handles its own categories, groups, documentation pages, and quality rules.

Examples of environments:

* Technical environments such as DEV / TEST / PRODUCTION
* Functional environments such as PRIVATE APIS / PUBLIC APIS / PARTNERSHIP

### Users and user groups

In Gravitee, a **User** is just a user of the Gravitee platform. You can create **User groups,** which are defined by a set of permissions and roles as they pertain to configuring and managing Organizations, Environments, APIs, and Applications in Gravitee. These four levels are referred to as **Scopes.**

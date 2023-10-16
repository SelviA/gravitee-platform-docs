---
description: >-
  This page contains the changelog entries for AM 4.1 and any future minor or
  patch AM 4.1.x releases
---

# AM 4.1.x

## Gravitee Access Management 4.1 - September 28, 2023

For more in-depth information on what's new, please refer to the [Gravitee AM 4.1 release notes](../release-notes/).

<details>

<summary>What's new</summary>

**Enterprise Edition**

The MFA Challenge policy is now available to apply an MFA step during actions such as reset password or unlock account.&#x20;

**Twilio phone factor enhancement**

The MFA phone call factor can now use Twilio's sendDigits function to direct a call to an extension before playing the message with the MFA code.

**Account linking**

The new Account Linking feature automatically links user accounts with identical user attributes to bypass re-enrollment during authentication.

**Session management**

Consent to a new session cookie option prevents logout following a period of idling and extends the session expiration.

</details>

<details>

<summary>Breaking changes</summary>

* AM 4.1 requires Java 17 as the runtime
* The versions of the R2DBC drivers must be compatible with R2DBC-SPI 1.0 (i.e., the driver version must start with 1.x). Versions used:
  * postgresql: **1.0.2.RELEASE**\
    mariadb: **1.1.2**\
    mysql: **1.0.2**\
    mssql: **1.0.0.RELEASE**
  * **WARNING** ⚠️ **DO NOT** use the **1.0.2.RELEASE** for **mssql / SQLServer** as this version seems to be buggy (see [r2dbc/r2dbc-mssql#276](https://github.com/r2dbc/r2dbc-mssql/issues/276))
*   Default RDMS timeout and connection pool size values have changed:

    * New values:

    ```
        initialSize: 1
        maxSize: 50
        maxIdleTime: 30000
        maxLifeTime: -1
        maxAcquireTime: 3000
        maxCreateConnectionTime: 5000
    ```

    * Previous values:

    ```
        initialSize: 0
        maxSize: 10
        maxIdleTime: 30000
        maxLifeTime: 0 # not valid anymore with R2BC 1.x
        maxAcquireTime: 0 # not valid anymore with R2BC 1.x
        maxCreateConnectionTime: 0 # not valid anymore with R2BC 1.x
    ```

</details>

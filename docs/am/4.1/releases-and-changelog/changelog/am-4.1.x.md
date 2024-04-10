---
description: >-
  This page contains the changelog entries for AM 4.1.x and any future minor or
  patch AM 4.1.x releases
---

# AM 4.1.x

## Gravitee Access Management 4.1.18 - April 5, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Disable Application [#9584](https://github.com/gravitee-io/issues/issues/9584)

**Other**

* Expired records present in table ciba\_auth\_requests. Cron is not taken into account. [#9499](https://github.com/gravitee-io/issues/issues/9499)
* Logs too verbose in AM when GeoIP plugin is not available [#9633](https://github.com/gravitee-io/issues/issues/9633)
* Support SAML mixing response binding protocol [#9648](https://github.com/gravitee-io/issues/issues/9648)

</details>

## Gravitee Access Management 4.1.17 - March 28, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Login - MFA challenge should be prompted when prompt=login is used [#9497](https://github.com/gravitee-io/issues/issues/9497)
* Revert: Passwordless authentication doesn't take the IDP status into account (#9494) [#9615](https://github.com/gravitee-io/issues/issues/9615)
* User unable to authenticate when linked to different identities [#9616](https://github.com/gravitee-io/issues/issues/9616)
* Addition of WebAuthn Credentials info into the context [#9620](https://github.com/gravitee-io/issues/issues/9620)

**Console**

* No space between source IP and user agent in audit logs [#9458](https://github.com/gravitee-io/issues/issues/9458)
* User agent showing 'undefined' in audit logs [#9459](https://github.com/gravitee-io/issues/issues/9459)
* Fetch user group doesn't persist [#9609](https://github.com/gravitee-io/issues/issues/9609)

**Other**

* Linked accounts are not listed in the UI when using SQL database [#9610](https://github.com/gravitee-io/issues/issues/9610)

</details>

## Gravitee Access Management 4.1.16 - March 15, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Redirect executed with jwt-bearer grant\_type [#9505](https://github.com/gravitee-io/issues/issues/9505)
* Invalid Phone Number [#9519](https://github.com/gravitee-io/issues/issues/9519)

</details>

## Gravitee Access Management 4.1.15 - February 29, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Passwordless authentication doesn't take the IDP status into account [#9494](https://github.com/gravitee-io/issues/issues/9494)
* State parameter encoded twice with response\_mode set to form\_post [#9528](https://github.com/gravitee-io/issues/issues/9528)
* Passwordless registration appearing for users who have already authenticated with step up [#9568](https://github.com/gravitee-io/issues/issues/9568)

</details>

## Gravitee Access Management 4.1.14 - February 19, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Unable to finalize SAML authentication using HTTP-POST binding [#9485](https://github.com/gravitee-io/issues/issues/9485)
* Security Domain may not be loaded on Gateway startup [#9496](https://github.com/gravitee-io/issues/issues/9496)
* Custom email not being sent when resending account registered verification email [#9500](https://github.com/gravitee-io/issues/issues/9500)

**Console**

* Missing read password policy role [#8924](https://github.com/gravitee-io/issues/issues/8924)

**Other**

* Do not log stack trace when user has to provide password after webauthn authentication [#9503](https://github.com/gravitee-io/issues/issues/9503)
* SAML 2.0 Identity Provider requires AM dependency update [#9515](https://github.com/gravitee-io/issues/issues/9515)

</details>

## Gravitee Access Management 4.1.13 - February 9, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Invalid form parameter when ResponseMode is set to form\_post [#9179](https://github.com/gravitee-io/issues/issues/9179)
* SCIM search operator PR doesn't work as expected [#9265](https://github.com/gravitee-io/issues/issues/9265)
* WebAuthn: "Force authenticator integrity" - LastCheckedAt systematically updated at each webauthn login [#9327](https://github.com/gravitee-io/issues/issues/9327)

</details>

## Gravitee Access Management 4.1.12 - January 30, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Apply timeout on blockingGet in ManagementAPI filters [#9476](https://github.com/gravitee-io/issues/issues/9476)
* Authentication flow rejected due to redirect\_uri when PAR is used [#9478](https://github.com/gravitee-io/issues/issues/9478)
* MFA challenge should be prompted before registering a passwordless device [#9479](https://github.com/gravitee-io/issues/issues/9479)

</details>

## Gravitee Access Management 4.1.11 - January 30, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Passwordless not working for iOS v17.2.1 [#9470](https://github.com/gravitee-io/issues/issues/9470)
* Flow - Add WebAuthn credential register flow (improvement)

</details>

## Gravitee Access Management 4.1.10 - January 17, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Avoid BodyHandler processing for GET request [#9352](https://github.com/gravitee-io/issues/issues/9352)
* WebAuthnCredentialId is null into the EL context [#9455](https://github.com/gravitee-io/issues/issues/9455)

**Other**

* AEConnector not initialized properly since AM 4.1 [#9454](https://github.com/gravitee-io/issues/issues/9454)

</details>

## Gravitee Access Management 4.1.9 - December 22, 2023

<details>

<summary>Bug fixes</summary>

**Gateway**

* Session expired problem - X-XRF-TOKEN [#9398](https://github.com/gravitee-io/issues/issues/9398)
* 500 response received on creating user with /scim endpoint with duplicate externalId [#9421](https://github.com/gravitee-io/issues/issues/9421)
* Exclude null value from SCIM UserMapper [#9427](https://github.com/gravitee-io/issues/issues/9427)

**Management API**

* Unable to list users [#9125](https://github.com/gravitee-io/issues/issues/9125)

**Other**

* Connection leak into JdbcIdentityProvider [#9426](https://github.com/gravitee-io/issues/issues/9426)

</details>

## Gravitee Access Management 4.1.8 - December 11, 2023

<details>

<summary>Bug fixes</summary>

**Gateway**

* Original Parameters lost during redirect using SAML Handler [#9393](https://github.com/gravitee-io/issues/issues/9393)
* Avoid logging GeoIP error stackstrace [#9401](https://github.com/gravitee-io/issues/issues/9401)

**Other**

* Invalid value in Issuer for Response [#9409](https://github.com/gravitee-io/issues/issues/9409)
* MessageDigest Encoder is not ThreadSafe [#9413](https://github.com/gravitee-io/issues/issues/9413)
* Configuration files are being overwritten during YUM update [#9368](https://github.com/gravitee-io/issues/issues/9368)

</details>

## Gravitee Access Management 4.1.7 - November 22, 2023

<details>

<summary>Bug fixes</summary>

**Gateway**

* Don't keep FranceConnect Session active [#9382](https://github.com/gravitee-io/issues/issues/9382)

</details>

## Gravitee Access Management 4.1.6 - November 17, 2023

<details>

<summary>Bug fixes</summary>

**Gateway**

* Make the IDToken accessible in the UserMapper [#9381](https://github.com/gravitee-io/issues/issues/9381)
* Deadlock during generate AccessToken [#9238](https://github.com/gravitee-io/issues/issues/9238)
* Excessive number of ExpiredJWTException errors in Gravitee logs [#9261](https://github.com/gravitee-io/issues/issues/9261)

</details>

## Gravitee Access Management 4.1.5 - November 8, 2023

<details>

<summary>What's new</summary>

* Addition of Consent settings into the Chart values
* Improve FranceConnect IDP to accept additional query parameters

</details>

<details>

<summary>Bug fixes</summary>

**Other**

* Upgrade Groovy policy [#9229](https://github.com/gravitee-io/issues/issues/9229)
* EnrollmentMFA policy doesn't manage the `useVariableFactorSecurity` setting [#9365](https://github.com/gravitee-io/issues/issues/9365)

</details>

## Gravitee Access Management 4.1.4 - November 3, 2023

<details>

<summary>Bug fixes</summary>

**Gateway**

* Use SingleSignOut with linked accounts [#9358](https://github.com/gravitee-io/issues/issues/9358)

</details>

## Gravitee Access Management 4.1.3 - October 27, 2023

<details>

<summary>Bug fixes</summary>

**Gateway**

* Application error when using an undefined translation [#9237](https://github.com/gravitee-io/issues/issues/9237)
* Registration confirmation Javascript error (anti-XSRF token) [#9276](https://github.com/gravitee-io/issues/issues/9276)
* Quotes are lost in Gravitee AM forms [#9326](https://github.com/gravitee-io/issues/issues/9326)
* When a resource plugin has been removed from the installation, other resources may not be loaded [#9344](https://github.com/gravitee-io/issues/issues/9344)
* On error during CONNECT flow redirection is not processed [#9346](https://github.com/gravitee-io/issues/issues/9346)
* User created using SCIM is disabled when password is missing [#9347](https://github.com/gravitee-io/issues/issues/9347)

**Management API**

* Management API hangs completely [#9339](https://github.com/gravitee-io/issues/issues/9339)

**Other**

* EnrollMFA should be able to update the factor [#9350](https://github.com/gravitee-io/issues/issues/9350)

</details>

## Gravitee Access Management 4.1.2 - October 19, 2023

<details>

<summary>Bug fixes</summary>

**Gateway**

* Twilio Phone Extension with Self-Service API [#9289](https://github.com/gravitee-io/issues/issues/9289)

**Other**

* EnrichProfile reset factor defined by EnrollMFA policy [#9161](https://github.com/gravitee-io/issues/issues/9161)

</details>

## Gravitee Access Management 4.1.1 - October 16, 2023

<details>

<summary>Bug fixes</summary>

**Gateway**

* Align XSRF token TTL to the user session TTL [#9282](https://github.com/gravitee-io/issues/issues/9282)

**Management API**

* Wrong values returned by Gravitee AM Management API [#9141](https://github.com/gravitee-io/issues/issues/9141)
* AM Management API should start even with missing or unknown Identity Provider plugins [#9230](https://github.com/gravitee-io/issues/issues/9230)

**Other**

* MS SqlServer 10.2 onwards driver support [#9178](https://github.com/gravitee-io/issues/issues/9178)
* Upgrade script for 3.21.6 does not work as expected [#9288](https://github.com/gravitee-io/issues/issues/9288)
* Update Mongo script to create indices [#9291](https://github.com/gravitee-io/issues/issues/9291)

</details>

## Gravitee Access Management 4.1.0 - September 28, 2023

For more in-depth information on what's new, please refer to the [Gravitee AM 4.1 release notes](../release-notes/).

<details>

<summary>What's new</summary>

**Enterprise Edition**

The MFA Challenge policy is now available to apply an MFA step during actions such as reset password or unlock account.

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
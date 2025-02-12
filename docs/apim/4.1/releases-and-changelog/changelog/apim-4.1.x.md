---
description: >-
  This page contains the changelog entries for APIM 4.1.x and any future patch
  APIM 4.1.x releases
---

# APIM 4.1.x

## Gravitee API Management 4.1.15 - May 10, 2024

<details>

<summary>Bug fixes</summary>

**Management API**

* Portal global API search is returning a 500 "maxClauseCount is set to 1024" [#9730](https://github.com/gravitee-io/issues/issues/9730)

**Other**

* \[gravitee-policy-ratelimit] Thread Blocked on AsyncRateLimitRepository [#9717](https://github.com/gravitee-io/issues/issues/9717)

</details>

<details>

<summary>Improvements</summary>

**Helm Charts**

* Enhance the experience of deploying Gateway with Redis SSL using Helm Chart [#9726](https://github.com/gravitee-io/issues/issues/9726)

**Other**

* \[gravitee-entrypoint-webhook] Support 500 responses for DLQ [#9722](https://github.com/gravitee-io/issues/issues/9722)

</details>

## Gravitee API Management 4.1.14 - April 26, 2024

<details>

<summary>Bug fixes</summary>

**Management API**

* Error in OpenApi spec [#9665](https://github.com/gravitee-io/issues/issues/9665)
* Unable to update the service account email through API [#9682](https://github.com/gravitee-io/issues/issues/9682)

**Console**

* Cannot create Backend-to-Backend Application from UI Console [#9636](https://github.com/gravitee-io/issues/issues/9636)

**Portal**

* Problem of swagger interpretation with redocly [#9673](https://github.com/gravitee-io/issues/issues/9673)

**Other**

* \[gravitee-policy-cache] Cache Policy Always Caches the First Response [#9534](https://github.com/gravitee-io/issues/issues/9534)
* \[gravitee-policy-cache] Cache Policy Does Not Correctly Return Images [#9585](https://github.com/gravitee-io/issues/issues/9585)
* \[gravitee-policy-cache] Time to live setting not working [#9692](https://github.com/gravitee-io/issues/issues/9692)

</details>

## Gravitee API Management 4.1.13 - April 11, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Secret Provider Setup [#9586](https://github.com/gravitee-io/issues/issues/9586)
* 431 (Request Header Fields Too Large) when submitting large JWT to gRPC API [#9652](https://github.com/gravitee-io/issues/issues/9652)

**Management API**

* Installation collection can have more than one entry [#9641](https://github.com/gravitee-io/issues/issues/9641)

**Console**

* Performance issue with the analytics dashboard [#9658](https://github.com/gravitee-io/issues/issues/9658)

**Portal**

* Cannot Scroll in Markdown Documents [#9634](https://github.com/gravitee-io/issues/issues/9634)
* Showing Gravitee.io in Dev Portal browser tab only while the page loads [#9663](https://github.com/gravitee-io/issues/issues/9663)

**Other**

* Fail to enable the service on SUSE [#9501](https://github.com/gravitee-io/issues/issues/9501)
* Upgrade 3.20.22 to 4.2.2 - File report missing node metrics [#9589](https://github.com/gravitee-io/issues/issues/9589)
* \[gravitee-policy-cache] Concurrency issue with v4 emulation engine [#9635](https://github.com/gravitee-io/issues/issues/9635)
* \[gravitee-resource-auth-provider-http] Timeout when body parsing is failing [#9640](https://github.com/gravitee-io/issues/issues/9640)
* API List showing type as "Undefined" for v4 APIs in Postgres env [#9643](https://github.com/gravitee-io/issues/issues/9643)
* Authentication Provider table column too small [#9664](https://github.com/gravitee-io/issues/issues/9664)

</details>

## Gravitee API Management 4.1.12 - March 29, 2024

<details>

<summary>Bug fixes</summary>

**Management API**

* Update import remove all members when a group is defined as a PO [#9596](https://github.com/gravitee-io/issues/issues/9596)
* Gravitee 4.2 OpenAPI issues [#9632](https://github.com/gravitee-io/issues/issues/9632)

**Other**

* \[gravitee-policy-ipfiltering] DNS Lookup fails with some DNS servers [#9592](https://github.com/gravitee-io/issues/issues/9592)
* \[gravitee-resource-auth-provider-http] Timeout when authentication condition is failing [#9611](https://github.com/gravitee-io/issues/issues/9611)
* Liquibase changelog 4.0.20-dashboards adding NOT NULL column without default value [#9626](https://github.com/gravitee-io/issues/issues/9626)
* APIM DashboardTypeUpgrader raises an error when used with DocumentDB [#9631](https://github.com/gravitee-io/issues/issues/9631)

</details>

<details>

<summary>Improvements</summary>

**Management API**

* Allow to configure KeepAliveTimeout for HTTP endpoint [#9541](https://github.com/gravitee-io/issues/issues/9541)

</details>

## Gravitee API Management 4.1.11 - March 22, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Improve HealthCheck service for v2 APIs [#9543](https://github.com/gravitee-io/issues/issues/9543)

**Management API**

* Condition field in JDBC dbs is too short [#9595](https://github.com/gravitee-io/issues/issues/9595)

**Console**

* \[shared API key] API key mode not displayed on application screen [#9612](https://github.com/gravitee-io/issues/issues/9612)

**Other**

* Flow Id is lost when updating API with UI, causing it to regenerate new flow [#9597](https://github.com/gravitee-io/issues/issues/9597)
* API v4 proxy - problem with client SSL certificate

</details>

<details>

<summary>Improvements</summary>

**Portal**

* Do not allow user to change their email through the portal [#9617](https://github.com/gravitee-io/issues/issues/9617)

</details>

## Gravitee API Management 4.1.10 - March 1, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Override HTTP Method [#9526](https://github.com/gravitee-io/issues/issues/9526)

**Management API**

* Shared API Key Does Not Always Bind to Subscriptions When Concurrent Requests Are Made [#9502](https://github.com/gravitee-io/issues/issues/9502)
* NullPointer Exception when importing an API with group as PO and members [#9507](https://github.com/gravitee-io/issues/issues/9507)
* APIM: Creating application with "@" in name automatically converts it to "@" [#9514](https://github.com/gravitee-io/issues/issues/9514)
* API description required with POST /apis/ on mAPI v2 [#9527](https://github.com/gravitee-io/issues/issues/9527)
* Importing an API with a group as PO but no PO user in this group should not be possible [#9587](https://github.com/gravitee-io/issues/issues/9587)

**Console**

* No longer possible to compare "published" and "to deploy" status [#9491](https://github.com/gravitee-io/issues/issues/9491)
* Re: Error when clicking on top failed API in platform dashbaord [#9498](https://github.com/gravitee-io/issues/issues/9498)
* Remove last user in group shows error [#9517](https://github.com/gravitee-io/issues/issues/9517)
* \[endpoints] updating name or deleting group used as DLQ prevent updating API [#9535](https://github.com/gravitee-io/issues/issues/9535)
* \[endpoints] creating an endpoint group should display endpoint configuration [#9582](https://github.com/gravitee-io/issues/issues/9582)

**Portal**

* Documentation menu hidden [#9590](https://github.com/gravitee-io/issues/issues/9590)

</details>

## Gravitee API Management 4.1.9 - February 16, 2024

<details>

<summary>Bug fixes</summary>

**Management API**

* Excluded groups on plan are not displayed after being imported or promoted to a new environment [#9116](https://github.com/gravitee-io/issues/issues/9116)
* Private APIs on the Portal are wrongly displayed [#9513](https://github.com/gravitee-io/issues/issues/9513)
* Modifying API definition causes loss of endpoint configuration [#9520](https://github.com/gravitee-io/issues/issues/9520)

**Console**

* When validating a JWT subscription, I'm asked to customize an APIkey [#9489](https://github.com/gravitee-io/issues/issues/9489)

**Portal**

* Documentation gets encoded after deployment [#9490](https://github.com/gravitee-io/issues/issues/9490)
* Customization problems in the Developer Portal [#9495](https://github.com/gravitee-io/issues/issues/9495)
* Subscriptions Not Visible in Portal If There Is a Push Plan [#9511](https://github.com/gravitee-io/issues/issues/9511)

**Other**

* "Propagate client Accept-Encoding header" option missing in V4 [#9475](https://github.com/gravitee-io/issues/issues/9475)
* \[policy-request-validation] Un-required OpenAPI fields added as required in Validate Request policy [#9509](https://github.com/gravitee-io/issues/issues/9509)

</details>

## Gravitee API Management 4.1.8 - February 2, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Unable to populate attributes using the Assign Attributes policy due to enabled v4 Engine [#9420](https://github.com/gravitee-io/issues/issues/9420)
* Conditional logging [#9486](https://github.com/gravitee-io/issues/issues/9486)
* Timeout when connecting to WebSocket API using header Connection:Upgrade,Keep-Alive [#9487](https://github.com/gravitee-io/issues/issues/9487)

</details>

<details>

<summary>Improvements</summary>

**Gateway**

* Add API ID in healthcheck logs [#9493](https://github.com/gravitee-io/issues/issues/9493)

</details>

## Gravitee API Management 4.1.7 - January 19, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Sometimes path-mapping is not working [#9450](https://github.com/gravitee-io/issues/issues/9450)
* Management API does not encode a value in the URL used in a pipe [#9461](https://github.com/gravitee-io/issues/issues/9461)
* gRPC backend received unexpected headers [#9463](https://github.com/gravitee-io/issues/issues/9463)

**Management API**

* Unable to switch to gRPC endpoint type from the Console UI [#9456](https://github.com/gravitee-io/issues/issues/9456)
* Updating an API reset the gRPC type of the endpoint [#9464](https://github.com/gravitee-io/issues/issues/9464)
* Can't create 2 virtualhosts having the same path but different host [#9466](https://github.com/gravitee-io/issues/issues/9466)

**Console**

* Can't create 2 virtualhosts having the same path but different host [#9466](https://github.com/gravitee-io/issues/issues/9466)
* Navigation in a multi-environments console is messed up [#9467](https://github.com/gravitee-io/issues/issues/9467)

**Portal**

* Docs not loaded instantly [#9452](https://github.com/gravitee-io/issues/issues/9452)

**Helm Charts**

* Backward incompatibility during Helm upgrade with old `values.yml` [#9446](https://github.com/gravitee-io/issues/issues/9446)

</details>

<details>

<summary>Improvements</summary>

**Gateway**

* Access request host property in Expression Language [#9453](https://github.com/gravitee-io/issues/issues/9453)

</details>

## Gravitee API Management 4.1.6 - December 21, 2023

<details>

<summary>Bug fixes</summary>

**Gateway**

* Healthcheck service never stopped when using Service Discovery [#9437](https://github.com/gravitee-io/issues/issues/9437)

**Management API**

* API Does Not Deploy if a Common Flow Exists with Multiple Entrypoints Selected [#9415](https://github.com/gravitee-io/issues/issues/9415)
* Cannot delete API with too many events [#9439](https://github.com/gravitee-io/issues/issues/9439)

**Console**

* Inconsistency on "Inheritance" flag for endpoints/groups between frontend and backend [#9407](https://github.com/gravitee-io/issues/issues/9407)
* Flow Name Display Does Not Match Gateway Behavior [#9416](https://github.com/gravitee-io/issues/issues/9416)
* Log view too wide [#9429](https://github.com/gravitee-io/issues/issues/9429)

**Portal**

* Tickets Inaccessible When an API with Open Tickets Is Deleted [#9422](https://github.com/gravitee-io/issues/issues/9422)
* Cannot Scroll in Markdown Documentation in Portal [#9424](https://github.com/gravitee-io/issues/issues/9424)
* Synchronization inconsistency on ALL APIs page on Portal [#9432](https://github.com/gravitee-io/issues/issues/9432)
* Sign up doesn't work anymore [#9440](https://github.com/gravitee-io/issues/issues/9440)

**Other**

* Make some non-migrated policies available on REQUEST phase for message APIs [#9430](https://github.com/gravitee-io/issues/issues/9430)

</details>

<details>

<summary>Improvements</summary>

**Other**

* \[JDBC] Improve Flows loading [#9436](https://github.com/gravitee-io/issues/issues/9436)

</details>

## Gravitee API Management 4.1.5 - December 7, 2023

<details>

<summary>Bug fixes</summary>

**Gateway**

* EL: Request's local address is evaluated in place of remote address [#9408](https://github.com/gravitee-io/issues/issues/9408)

**Management API**

* Can't stop a deprecated API [#9406](https://github.com/gravitee-io/issues/issues/9406)

**Console**

* Deploy banner not displayed when updating details of a plan [#9380](https://github.com/gravitee-io/issues/issues/9380)
* Error in Swagger documentation both in Portal and Console [#9391](https://github.com/gravitee-io/issues/issues/9391)
* Bad management of required file in OpenAPI [#9414](https://github.com/gravitee-io/issues/issues/9414)

**Portal**

* Error in Swagger documentation both in Portal and Console [#9391](https://github.com/gravitee-io/issues/issues/9391)

**Helm Charts**

* Alert Engine: System mail notification [#9402](https://github.com/gravitee-io/issues/issues/9402)
* License deleted after Helm upgrade [#9411](https://github.com/gravitee-io/issues/issues/9411)

**Other**

* Transform Query Parameters policy [#9383](https://github.com/gravitee-io/issues/issues/9383)

</details>

<details>

<summary>Improvements</summary>

**Management API**

* Add a resource in management API v1 to fetch API subscribers with pagination info [#9410](https://github.com/gravitee-io/issues/issues/9410)

**Portal**

* Update chore dependencies of Gravitee Portal [#9418](https://github.com/gravitee-io/issues/issues/9418)

</details>

## Gravitee API Management 4.1.4 - November 24, 2023

<details>

<summary>Bug fixes</summary>

**Management API**

* Application `api_key_mode` is automatically and incorrectly set to EXCLUSIVE mode without owner consent [#9348](https://github.com/gravitee-io/issues/issues/9348)
* Environment rights: API "update" right is not enough to edit the entrypoint [#9372](https://github.com/gravitee-io/issues/issues/9372)
* APIM: Flows table / name column / extend column size [#9377](https://github.com/gravitee-io/issues/issues/9377)
* Cannot Import API Definition with Automatic Group Association [#9385](https://github.com/gravitee-io/issues/issues/9385)

**Console**

* API subscription fails with insufficient rights error [#9341](https://github.com/gravitee-io/issues/issues/9341)
* History not available if too many deployments [#9359](https://github.com/gravitee-io/issues/issues/9359)
* APIM Console doc links point to old documentation site [#9386](https://github.com/gravitee-io/issues/issues/9386)

**Portal**

* API subscription fails with insufficient rights error [#9341](https://github.com/gravitee-io/issues/issues/9341)
* The "All rights reserved" mention on Portal is using an old date [#9384](https://github.com/gravitee-io/issues/issues/9384)

**Other**

* Configuration files are being overwritten during Yum update [#9368](https://github.com/gravitee-io/issues/issues/9368)
* Transform Headers policy should be case insensitive [#9378](https://github.com/gravitee-io/issues/issues/9378)
* Generate JWT policy Key Resolver wrong value [#9389](https://github.com/gravitee-io/issues/issues/9389)
* OAuth2 introspection and userinfo should send a 503 when technical exception instead of 401 [#9390](https://github.com/gravitee-io/issues/issues/9390)

</details>

<details>

<summary>Improvements</summary>

**Gateway**

* Health Check: Allow to use response time in assertion [#9388](https://github.com/gravitee-io/issues/issues/9388)

**Helm Charts**

* Allow to configure Gateway timeouts in the Helm Chart [#9392](https://github.com/gravitee-io/issues/issues/9392)

</details>

## Gravitee API Management 4.1.3 - November 10, 2023

<details>

<summary>Bug fixes</summary>

**Gateway**

* Gateways not able to send bulk index data to ES8 [#9361](https://github.com/gravitee-io/issues/issues/9361)
* When using push plan there is no log when subscription Webhook ends in error [#9363](https://github.com/gravitee-io/issues/issues/9363)

**Management API**

* Email related to closed, paused, and resumed subscription of API\_KEY plan are sent with an empty body [#9355](https://github.com/gravitee-io/issues/issues/9355)
* JDBC deadlocks on Command table when running multiple Management APIs [#9356](https://github.com/gravitee-io/issues/issues/9356)
* Error running `graviteeio-apim-rest-api-4.1.2` [#9360](https://github.com/gravitee-io/issues/issues/9360)
* Unable to access Alerts screen when there are millions of AlertEvents [#9362](https://github.com/gravitee-io/issues/issues/9362)
* Unable to deploy an API with a huge API definition and a lot of existing deployments [#9364](https://github.com/gravitee-io/issues/issues/9364)
* Security: Enforce password policy for users [#9374](https://github.com/gravitee-io/issues/issues/9374)

**Other**

* GKO: API state does not get updated [#9338](https://github.com/gravitee-io/issues/issues/9338)
* \[RabbitMQ] message not logged when Rabbit's message does not define correlationId [#9353](https://github.com/gravitee-io/issues/issues/9353)
* Groovy policy with On-request script not working in v4 engine emulation mode [#9367](https://github.com/gravitee-io/issues/issues/9367)
* Generate JWT not working with APIM 4.x [#9371](https://github.com/gravitee-io/issues/issues/9371)
* Missing “generate JWT policy” on a v4 message API entrypoint Request phase [#9373](https://github.com/gravitee-io/issues/issues/9373)

</details>

## Gravitee API Management 4.1.2 - October 27, 2023

<details>

<summary>Bug fixes</summary>

**Management API**

* Can't create Backend-to-Backend applications [#9157](https://github.com/gravitee-io/issues/issues/9157)
* Can't assign a group to a Backend-to-Backend application [#9158](https://github.com/gravitee-io/issues/issues/9158)
* Invalid CORS Allow Origin Can Be Imported To Create New API [#9212](https://github.com/gravitee-io/issues/issues/9212)
* Unable to create custom email notification template [#9284](https://github.com/gravitee-io/issues/issues/9284)
* Attached Media is lost when the API Documentation is renamed [#9285](https://github.com/gravitee-io/issues/issues/9285)
* User email address policy treats valid email address as invalid [#9293](https://github.com/gravitee-io/issues/issues/9293)
* Endpoint Configuration Resets to Default after Redeployment [#9296](https://github.com/gravitee-io/issues/issues/9296)
* Alert template not automatically applied to new APIs [#9323](https://github.com/gravitee-io/issues/issues/9323)
* Unable to import OpenAPI spec with unused `variables` in `servers` definition [#9329](https://github.com/gravitee-io/issues/issues/9329)
* User with quotes in last name isn't properly sanitized [#9336](https://github.com/gravitee-io/issues/issues/9336)
* Listening Hosts are mandatory in Virtual Hosts mode [#9343](https://github.com/gravitee-io/issues/issues/9343)
* The OpenAPI schema to close a plan has incorrect response code [#9351](https://github.com/gravitee-io/issues/issues/9351)

**Console**

* Unable to Update API with Open API YAML File [#9202](https://github.com/gravitee-io/issues/issues/9202)
* Unable to edit flows once saved with an invalid configuration [#9274](https://github.com/gravitee-io/issues/issues/9274)
* No Backend-to-Backend application type available [#9334](https://github.com/gravitee-io/issues/issues/9334)

**Portal**

* Custom wide logo is too small in the Portal header [#9337](https://github.com/gravitee-io/issues/issues/9337)

**Other**

* IP Filtering policy blacklist does not work if there is a space in the IP address [#9083](https://github.com/gravitee-io/issues/issues/9083)
* Domain name (host) in whitelist does not work in IP Filtering policy [#9198](https://github.com/gravitee-io/issues/issues/9198)
* JWS policy doesn't work with Java 17 [#9211](https://github.com/gravitee-io/issues/issues/9211)
* Data Logging Masking policy [#9215](https://github.com/gravitee-io/issues/issues/9215)
* Jaeger not working with APIM 4+ [#9331](https://github.com/gravitee-io/issues/issues/9331)
* Quotify the namespace defined in ServiceAccount to avoid errors [#9345](https://github.com/gravitee-io/issues/issues/9345)

</details>

## Gravitee API Management 4.1.1 - October 13, 2023

<details>

<summary>Bug fixes</summary>

**Gateway**

* Health check doesn't support endpoint with EL [#8700](https://github.com/gravitee-io/issues/issues/8700)
* `resource-filtering` policy does not work with debug mode [#9267](https://github.com/gravitee-io/issues/issues/9267)
* Gateways take proxy configuration but should not [#9278](https://github.com/gravitee-io/issues/issues/9278)

**Management API**

* Emails related to closed, paused, and resumed subscription of PUSH plan are not sent [#9281](https://github.com/gravitee-io/issues/issues/9281)
* Unable to update health checks on endpoints with REST API v2 [#9283](https://github.com/gravitee-io/issues/issues/9283)

**Console**

* "Configure logging mode" link not working [#9213](https://github.com/gravitee-io/issues/issues/9213)
* "Add members" button does not work for group admin [#9241](https://github.com/gravitee-io/issues/issues/9241)
* Unable to remove expiration date of an API Key [#9248](https://github.com/gravitee-io/issues/issues/9248)
* Non-admin users can't see API Keys of APIs they created [#9268](https://github.com/gravitee-io/issues/issues/9268)
* Console: Add date time picker instead of only date for subscription date field [#9271](https://github.com/gravitee-io/issues/issues/9271)
* Log Content Not Visible in V2 API Logs [#9290](https://github.com/gravitee-io/issues/issues/9290)

**Other**

* User claim in OAuth2 resource is ignored [#9168](https://github.com/gravitee-io/issues/issues/9168)
* Typo in the documentation of `cache-policy` [#9262](https://github.com/gravitee-io/issues/issues/9262)

</details>

## Gravitee API Management 4.1.0 - September 28, 2023

For more in-depth information on what's new, please refer to the [Gravitee APIM 4.1 release notes](../release-notes/apim-4.1.md).

<details>

<summary>What's new</summary>

**Installing APIM on Kubernetes**

* Helm Chart configuration now supports DB-less mode

**v4 API Configuration**

* Webhook entrypoint configuration supports Dead Letter Queue
* Enhanced single endpoint and endpoint group management
* Default single endpoint and endpoint group settings inheritance to streamline configuration
* Enhancements to user and group access, including transfer of ownership

**Creating v4 APIs**

* A v4 API can be created by importing an existing Gravitee v4 API definition in JSON format
* v4 API duplication is now supported

**Logging**

* Comprehensive connection logs to analyze the usage of v4 message APIs
* Customizable data capture and message content details

</details>

<details>

<summary>Breaking Changes</summary>

No breaking changes

</details>

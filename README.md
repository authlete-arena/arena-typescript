# authlete-arena

Developer-friendly & type-safe Typescript SDK specifically catered to leverage *authlete-arena* API.

[![Built by Speakeasy](https://img.shields.io/badge/Built_by-SPEAKEASY-374151?style=for-the-badge&labelColor=f3f4f6)](https://www.speakeasy.com/?utm_source=authlete-arena&utm_campaign=typescript)
[![License: MIT](https://img.shields.io/badge/LICENSE_//_MIT-3b5bdb?style=for-the-badge&labelColor=eff6ff)](https://opensource.org/licenses/MIT)


<br /><br />
> [!IMPORTANT]
> This SDK is not yet ready for production use. To complete setup please follow the steps outlined in your [workspace](https://app.speakeasy.com/org/authlete/sdk-workspace). Delete this section before > publishing to a package manager.

<!-- Start Summary [summary] -->
## Summary


<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [authlete-arena](#authlete-arena)
  * [SDK Installation](#sdk-installation)
  * [Requirements](#requirements)
  * [SDK Example Usage](#sdk-example-usage)
  * [Authentication](#authentication)
  * [Available Resources and Operations](#available-resources-and-operations)
  * [Standalone functions](#standalone-functions)
  * [Retries](#retries)
  * [Error Handling](#error-handling)
  * [Custom HTTP Client](#custom-http-client)
  * [Debugging](#debugging)
* [Development](#development)
  * [Maturity](#maturity)
  * [Contributions](#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start SDK Installation [installation] -->
## SDK Installation

> [!TIP]
> To finish publishing your SDK to npm and others you must [run your first generation action](https://www.speakeasy.com/docs/github-setup#step-by-step-guide).


The SDK can be installed with either [npm](https://www.npmjs.com/), [pnpm](https://pnpm.io/), [bun](https://bun.sh/) or [yarn](https://classic.yarnpkg.com/en/) package managers.

### NPM

```bash
npm add <UNSET>
```

### PNPM

```bash
pnpm add <UNSET>
```

### Bun

```bash
bun add <UNSET>
```

### Yarn

```bash
yarn add <UNSET>
```

> [!NOTE]
> This package is published as an ES Module (ESM) only. For applications using
> CommonJS, use `await import()` to import and use this package.
<!-- End SDK Installation [installation] -->

<!-- Start Requirements [requirements] -->
## Requirements

For supported JavaScript runtimes, please consult [RUNTIMES.md](RUNTIMES.md).
<!-- End Requirements [requirements] -->

<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await arena.getWellKnownOauthProtectedResource({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
  });

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security schemes globally:

| Name     | Type   | Scheme      | Environment Variable |
| -------- | ------ | ----------- | -------------------- |
| `bearer` | http   | HTTP Bearer | `ARENA_BEARER`       |
| `dpop`   | apiKey | API key     | `ARENA_DPOP`         |

You can set the security parameters through the `security` optional parameter when initializing the SDK client instance. The selected scheme will be used by default to authenticate with the API for all operations that support it. For example:
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.getWellKnownOauthProtectedResource({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
  });

  console.log(result);
}

run();

```
<!-- End Authentication [security] -->

<!-- Start Available Resources and Operations [operations] -->
## Available Resources and Operations

<details open>
<summary>Available methods</summary>

### [Arena SDK](docs/sdks/arena/README.md)

* [getWellKnownOauthProtectedResource](docs/sdks/arena/README.md#getwellknownoauthprotectedresource) - OAuth 2.0 Protected Resource Metadata
* [getJwks](docs/sdks/arena/README.md#getjwks) - JWK Set Document
* [getOpenapi](docs/sdks/arena/README.md#getopenapi) - Retrieve the OpenAPI document of this web application.
* [getProbeDatabase](docs/sdks/arena/README.md#getprobedatabase) - Database probe.
* [getProbeLiveness](docs/sdks/arena/README.md#getprobeliveness) - Liveness probe for Kubernetes.
* [getProbeReadiness](docs/sdks/arena/README.md#getprobereadiness) - Readiness probe for Kubernetes.
* [getProbeStartup](docs/sdks/arena/README.md#getprobestartup) - Startup probe for Kubernetes.
* [postSsfTransmitter](docs/sdks/arena/README.md#postssftransmitter) - Create a transmitter.
* [getSsfTransmitterTransmitterId](docs/sdks/arena/README.md#getssftransmittertransmitterid) - Retrieve information about the transmitter.
* [putSsfTransmitterTransmitterId](docs/sdks/arena/README.md#putssftransmittertransmitterid) - Update the transmitter.
* [deleteSsfTransmitterTransmitterId](docs/sdks/arena/README.md#deletessftransmittertransmitterid) - Delete the transmitter.
* [patchSsfTransmitterTransmitterId](docs/sdks/arena/README.md#patchssftransmittertransmitterid) - Apply a patch to the transmitter.
* [postSsfTransmitterTransmitterIdDelegateJwks](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatejwks) - JWK Set Document Endpoint
* [postSsfTransmitterTransmitterIdDelegateStreamCreate](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamcreate) - Stream Create (HTTP POST to the configuration endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamRead](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamread) - Stream Read (HTTP GET to the configuration endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamUpdate](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamupdate) - Stream Update (HTTP PATCH to the configuration endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamReplace](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamreplace) - Stream Replace (HTTP PUT to the configuration endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamDelete](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamdelete) - Stream Delete (HTTP DELETE to the configuration endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamVerify](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamverify) - Stream Verify (HTTP POST to the verification endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamPollStreamId](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreampollstreamid) - Stream Poll (HTTP POST to the poll endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamStatusRead](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamstatusread) - Stream Status Read (HTTP GET to the status endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamStatusUpdate](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamstatusupdate) - Stream Status Update (HTTP POST to the status endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamSubjectAdd](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamsubjectadd) - Stream Subject Add (HTTP POST to the add subject endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamSubjectRemove](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamsubjectremove) - Stream Subject Remove (HTTP POST to the remove subject endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamSubjectList](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamsubjectlist) - Stream Subject List (HTTP GET to the list subjects endpoint)
* [postSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResource](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatewellknownoauthprotectedresource) - Protected Resource Metadata Endpoint (/.well-known/oauth-protected-resource)
* [postSsfTransmitterTransmitterIdDelegateWellKnownSsfConfiguration](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatewellknownssfconfiguration) - Transmitter Metadata Endpoint (/.well-known/ssf-configuration)
* [postSsfTransmitterTransmitterIdEventRegister](docs/sdks/arena/README.md#postssftransmittertransmitterideventregister) - Register an event.
* [getSsfTransmitterTransmitterIdStreamList](docs/sdks/arena/README.md#getssftransmittertransmitteridstreamlist) - List streams.
* [getSsfTransmitterTransmitterIdStreamStreamId](docs/sdks/arena/README.md#getssftransmittertransmitteridstreamstreamid) - Retrieve information about the stream.
* [deleteSsfTransmitterTransmitterIdStreamStreamId](docs/sdks/arena/README.md#deletessftransmittertransmitteridstreamstreamid) - Delete the stream.
* [postSsfTransmitterTransmitterIdStreamStreamIdVerify](docs/sdks/arena/README.md#postssftransmittertransmitteridstreamstreamidverify) - Register a verification event into the stream.
* [getSsfTransmitterTransmitterIdStreamStreamIdEventList](docs/sdks/arena/README.md#getssftransmittertransmitteridstreamstreamideventlist) - List stream events.
* [getSsfTransmitterTransmitterIdStreamStreamIdEventEventJti](docs/sdks/arena/README.md#getssftransmittertransmitteridstreamstreamideventeventjti) - Retrieve information about the event.
* [deleteSsfTransmitterTransmitterIdStreamStreamIdEventEventJti](docs/sdks/arena/README.md#deletessftransmittertransmitteridstreamstreamideventeventjti) - Delete the event.

</details>
<!-- End Available Resources and Operations [operations] -->

<!-- Start Standalone functions [standalone-funcs] -->
## Standalone functions

All the methods listed above are available as standalone functions. These
functions are ideal for use in applications running in the browser, serverless
runtimes or other environments where application bundle size is a primary
concern. When using a bundler to build your application, all unused
functionality will be either excluded from the final bundle or tree-shaken away.

To read more about standalone functions, check [FUNCTIONS.md](./FUNCTIONS.md).

<details>

<summary>Available standalone functions</summary>

- [`deleteSsfTransmitterTransmitterId`](docs/sdks/arena/README.md#deletessftransmittertransmitterid) - Delete the transmitter.
- [`deleteSsfTransmitterTransmitterIdStreamStreamId`](docs/sdks/arena/README.md#deletessftransmittertransmitteridstreamstreamid) - Delete the stream.
- [`deleteSsfTransmitterTransmitterIdStreamStreamIdEventEventJti`](docs/sdks/arena/README.md#deletessftransmittertransmitteridstreamstreamideventeventjti) - Delete the event.
- [`getJwks`](docs/sdks/arena/README.md#getjwks) - JWK Set Document
- [`getOpenapi`](docs/sdks/arena/README.md#getopenapi) - Retrieve the OpenAPI document of this web application.
- [`getProbeDatabase`](docs/sdks/arena/README.md#getprobedatabase) - Database probe.
- [`getProbeLiveness`](docs/sdks/arena/README.md#getprobeliveness) - Liveness probe for Kubernetes.
- [`getProbeReadiness`](docs/sdks/arena/README.md#getprobereadiness) - Readiness probe for Kubernetes.
- [`getProbeStartup`](docs/sdks/arena/README.md#getprobestartup) - Startup probe for Kubernetes.
- [`getSsfTransmitterTransmitterId`](docs/sdks/arena/README.md#getssftransmittertransmitterid) - Retrieve information about the transmitter.
- [`getSsfTransmitterTransmitterIdStreamList`](docs/sdks/arena/README.md#getssftransmittertransmitteridstreamlist) - List streams.
- [`getSsfTransmitterTransmitterIdStreamStreamId`](docs/sdks/arena/README.md#getssftransmittertransmitteridstreamstreamid) - Retrieve information about the stream.
- [`getSsfTransmitterTransmitterIdStreamStreamIdEventEventJti`](docs/sdks/arena/README.md#getssftransmittertransmitteridstreamstreamideventeventjti) - Retrieve information about the event.
- [`getSsfTransmitterTransmitterIdStreamStreamIdEventList`](docs/sdks/arena/README.md#getssftransmittertransmitteridstreamstreamideventlist) - List stream events.
- [`getWellKnownOauthProtectedResource`](docs/sdks/arena/README.md#getwellknownoauthprotectedresource) - OAuth 2.0 Protected Resource Metadata
- [`patchSsfTransmitterTransmitterId`](docs/sdks/arena/README.md#patchssftransmittertransmitterid) - Apply a patch to the transmitter.
- [`postSsfTransmitter`](docs/sdks/arena/README.md#postssftransmitter) - Create a transmitter.
- [`postSsfTransmitterTransmitterIdDelegateJwks`](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatejwks) - JWK Set Document Endpoint
- [`postSsfTransmitterTransmitterIdDelegateStreamCreate`](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamcreate) - Stream Create (HTTP POST to the configuration endpoint)
- [`postSsfTransmitterTransmitterIdDelegateStreamDelete`](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamdelete) - Stream Delete (HTTP DELETE to the configuration endpoint)
- [`postSsfTransmitterTransmitterIdDelegateStreamPollStreamId`](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreampollstreamid) - Stream Poll (HTTP POST to the poll endpoint)
- [`postSsfTransmitterTransmitterIdDelegateStreamRead`](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamread) - Stream Read (HTTP GET to the configuration endpoint)
- [`postSsfTransmitterTransmitterIdDelegateStreamReplace`](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamreplace) - Stream Replace (HTTP PUT to the configuration endpoint)
- [`postSsfTransmitterTransmitterIdDelegateStreamStatusRead`](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamstatusread) - Stream Status Read (HTTP GET to the status endpoint)
- [`postSsfTransmitterTransmitterIdDelegateStreamStatusUpdate`](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamstatusupdate) - Stream Status Update (HTTP POST to the status endpoint)
- [`postSsfTransmitterTransmitterIdDelegateStreamSubjectAdd`](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamsubjectadd) - Stream Subject Add (HTTP POST to the add subject endpoint)
- [`postSsfTransmitterTransmitterIdDelegateStreamSubjectList`](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamsubjectlist) - Stream Subject List (HTTP GET to the list subjects endpoint)
- [`postSsfTransmitterTransmitterIdDelegateStreamSubjectRemove`](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamsubjectremove) - Stream Subject Remove (HTTP POST to the remove subject endpoint)
- [`postSsfTransmitterTransmitterIdDelegateStreamUpdate`](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamupdate) - Stream Update (HTTP PATCH to the configuration endpoint)
- [`postSsfTransmitterTransmitterIdDelegateStreamVerify`](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatestreamverify) - Stream Verify (HTTP POST to the verification endpoint)
- [`postSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResource`](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatewellknownoauthprotectedresource) - Protected Resource Metadata Endpoint (/.well-known/oauth-protected-resource)
- [`postSsfTransmitterTransmitterIdDelegateWellKnownSsfConfiguration`](docs/sdks/arena/README.md#postssftransmittertransmitteriddelegatewellknownssfconfiguration) - Transmitter Metadata Endpoint (/.well-known/ssf-configuration)
- [`postSsfTransmitterTransmitterIdEventRegister`](docs/sdks/arena/README.md#postssftransmittertransmitterideventregister) - Register an event.
- [`postSsfTransmitterTransmitterIdStreamStreamIdVerify`](docs/sdks/arena/README.md#postssftransmittertransmitteridstreamstreamidverify) - Register a verification event into the stream.
- [`putSsfTransmitterTransmitterId`](docs/sdks/arena/README.md#putssftransmittertransmitterid) - Update the transmitter.

</details>
<!-- End Standalone functions [standalone-funcs] -->

<!-- Start Retries [retries] -->
## Retries

Some of the endpoints in this SDK support retries.  If you use the SDK without any configuration, it will fall back to the default retry strategy provided by the API.  However, the default retry strategy can be overridden on a per-operation basis, or across the entire SDK.

To change the default retry strategy for a single API call, simply provide a retryConfig object to the call:
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await arena.getWellKnownOauthProtectedResource({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
  }, {
    retries: {
      strategy: "backoff",
      backoff: {
        initialInterval: 1,
        maxInterval: 50,
        exponent: 1.1,
        maxElapsedTime: 100,
      },
      retryConnectionErrors: false,
    },
  });

  console.log(result);
}

run();

```

If you'd like to override the default retry strategy for all operations that support retries, you can provide a retryConfig at SDK initialization:
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  retryConfig: {
    strategy: "backoff",
    backoff: {
      initialInterval: 1,
      maxInterval: 50,
      exponent: 1.1,
      maxElapsedTime: 100,
    },
    retryConnectionErrors: false,
  },
});

async function run() {
  const result = await arena.getWellKnownOauthProtectedResource({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
  });

  console.log(result);
}

run();

```
<!-- End Retries [retries] -->

<!-- Start Error Handling [errors] -->
## Error Handling

[`ArenaError`](./src/models/errors/arena-error.ts) is the base class for all HTTP error responses. It has the following properties:

| Property            | Type       | Description                                                                             |
| ------------------- | ---------- | --------------------------------------------------------------------------------------- |
| `error.message`     | `string`   | Error message                                                                           |
| `error.statusCode`  | `number`   | HTTP response status code eg `404`                                                      |
| `error.headers`     | `Headers`  | HTTP response headers                                                                   |
| `error.body`        | `string`   | HTTP body. Can be empty string if no body is returned.                                  |
| `error.rawResponse` | `Response` | Raw HTTP response                                                                       |
| `error.data$`       |            | Optional. Some errors may contain structured data. [See Error Classes](#error-classes). |

### Example
```typescript
import { Arena } from "authlete-arena";
import * as errors from "authlete-arena/models/errors";

const arena = new Arena({
  serverURL: "https://api.example.com",
});

async function run() {
  try {
    const result = await arena.getOpenapi({
      xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    });

    console.log(result);
  } catch (error) {
    // The base class for HTTP error responses
    if (error instanceof errors.ArenaError) {
      console.log(error.message);
      console.log(error.statusCode);
      console.log(error.body);
      console.log(error.headers);

      // Depending on the method different errors may be thrown
      if (error instanceof errors.GetOpenapiBadRequestError) {
        console.log(error.data$.result); // operations.GetOpenapiResult
      }
    }
  }
}

run();

```

### Error Classes
**Primary error:**
* [`ArenaError`](./src/models/errors/arena-error.ts): The base class for HTTP error responses.

<details><summary>Less common errors (38)</summary>

<br />

**Network errors:**
* [`ConnectionError`](./src/models/errors/http-client-errors.ts): HTTP client was unable to make a request to a server.
* [`RequestTimeoutError`](./src/models/errors/http-client-errors.ts): HTTP request timed out due to an AbortSignal signal.
* [`RequestAbortedError`](./src/models/errors/http-client-errors.ts): HTTP request was aborted by the client.
* [`InvalidRequestError`](./src/models/errors/http-client-errors.ts): Any input used to create a request is invalid.
* [`UnexpectedClientError`](./src/models/errors/http-client-errors.ts): Unrecognised or unexpected error.


**Inherit from [`ArenaError`](./src/models/errors/arena-error.ts)**:
* [`GetOpenapiBadRequestError`](./src/models/errors/get-openapi-bad-request-error.ts): An error response indicating the value of the `format` request parameter is not supported. Status code `400`. Applicable to 1 of 35 methods.*
* [`PatchSsfTransmitterTransmitterIdBadRequestError`](./src/models/errors/patch-ssf-transmitter-transmitter-id-bad-request-error.ts): The patch was rejected. Status code `400`. Applicable to 1 of 35 methods.*
* [`PostSsfTransmitterTransmitterIdStreamStreamIdVerifyBadRequestError`](./src/models/errors/post-ssf-transmitter-transmitter-id-stream-stream-id-verify-bad-request-error.ts): A verification event cannot be registered because the stream is disabled. Status code `400`. Applicable to 1 of 35 methods.*
* [`GetSsfTransmitterTransmitterIdNotFoundError`](./src/models/errors/get-ssf-transmitter-transmitter-id-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`PutSsfTransmitterTransmitterIdNotFoundError`](./src/models/errors/put-ssf-transmitter-transmitter-id-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`DeleteSsfTransmitterTransmitterIdNotFoundError`](./src/models/errors/delete-ssf-transmitter-transmitter-id-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`PatchSsfTransmitterTransmitterIdNotFoundError`](./src/models/errors/patch-ssf-transmitter-transmitter-id-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`PostSsfTransmitterTransmitterIdDelegateJwksNotFoundError`](./src/models/errors/post-ssf-transmitter-transmitter-id-delegate-jwks-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`PostSsfTransmitterTransmitterIdDelegateStreamCreateNotFoundError`](./src/models/errors/post-ssf-transmitter-transmitter-id-delegate-stream-create-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`PostSsfTransmitterTransmitterIdDelegateStreamReadNotFoundError`](./src/models/errors/post-ssf-transmitter-transmitter-id-delegate-stream-read-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`PostSsfTransmitterTransmitterIdDelegateStreamUpdateNotFoundError`](./src/models/errors/post-ssf-transmitter-transmitter-id-delegate-stream-update-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`PostSsfTransmitterTransmitterIdDelegateStreamReplaceNotFoundError`](./src/models/errors/post-ssf-transmitter-transmitter-id-delegate-stream-replace-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`PostSsfTransmitterTransmitterIdDelegateStreamDeleteNotFoundError`](./src/models/errors/post-ssf-transmitter-transmitter-id-delegate-stream-delete-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`PostSsfTransmitterTransmitterIdDelegateStreamVerifyNotFoundError`](./src/models/errors/post-ssf-transmitter-transmitter-id-delegate-stream-verify-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`PostSsfTransmitterTransmitterIdDelegateStreamPollStreamIdNotFoundError`](./src/models/errors/post-ssf-transmitter-transmitter-id-delegate-stream-poll-stream-id-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`PostSsfTransmitterTransmitterIdDelegateStreamStatusReadNotFoundError`](./src/models/errors/post-ssf-transmitter-transmitter-id-delegate-stream-status-read-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`PostSsfTransmitterTransmitterIdDelegateStreamStatusUpdateNotFoundError`](./src/models/errors/post-ssf-transmitter-transmitter-id-delegate-stream-status-update-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`PostSsfTransmitterTransmitterIdDelegateStreamSubjectAddNotFoundError`](./src/models/errors/post-ssf-transmitter-transmitter-id-delegate-stream-subject-add-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`PostSsfTransmitterTransmitterIdDelegateStreamSubjectRemoveNotFoundError`](./src/models/errors/post-ssf-transmitter-transmitter-id-delegate-stream-subject-remove-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`PostSsfTransmitterTransmitterIdDelegateStreamSubjectListNotFoundError`](./src/models/errors/post-ssf-transmitter-transmitter-id-delegate-stream-subject-list-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`PostSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResourceNotFoundError`](./src/models/errors/post-ssf-transmitter-transmitter-id-delegate-well-known-oauth-protected-resource-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`PostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationNotFoundError`](./src/models/errors/post-ssf-transmitter-transmitter-id-delegate-well-known-ssf-configuration-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`PostSsfTransmitterTransmitterIdEventRegisterNotFoundError`](./src/models/errors/post-ssf-transmitter-transmitter-id-event-register-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`GetSsfTransmitterTransmitterIdStreamListNotFoundError`](./src/models/errors/get-ssf-transmitter-transmitter-id-stream-list-not-found-error.ts): There is no transmitter with the transmitter ID. Status code `404`. Applicable to 1 of 35 methods.*
* [`GetSsfTransmitterTransmitterIdStreamStreamIdNotFoundError`](./src/models/errors/get-ssf-transmitter-transmitter-id-stream-stream-id-not-found-error.ts): There is no transmitter with the transmitter ID, or there is no stream with the stream ID that belongs to the transmitter. Status code `404`. Applicable to 1 of 35 methods.*
* [`DeleteSsfTransmitterTransmitterIdStreamStreamIdNotFoundError`](./src/models/errors/delete-ssf-transmitter-transmitter-id-stream-stream-id-not-found-error.ts): There is no transmitter with the transmitter ID, or there is no stream with the stream ID that belong to the transmitter. Status code `404`. Applicable to 1 of 35 methods.*
* [`PostSsfTransmitterTransmitterIdStreamStreamIdVerifyNotFoundError`](./src/models/errors/post-ssf-transmitter-transmitter-id-stream-stream-id-verify-not-found-error.ts): There is no transmitter with the transmitter ID, or there is no stream with the stream ID that belongs to the transmitter. Status code `404`. Applicable to 1 of 35 methods.*
* [`GetSsfTransmitterTransmitterIdStreamStreamIdEventListNotFoundError`](./src/models/errors/get-ssf-transmitter-transmitter-id-stream-stream-id-event-list-not-found-error.ts): There is no transmitter with the transmitter ID, or there is no stream with the stream ID that belongs to the transmitter. Status code `404`. Applicable to 1 of 35 methods.*
* [`GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiNotFoundError`](./src/models/errors/get-ssf-transmitter-transmitter-id-stream-stream-id-event-event-jti-not-found-error.ts): There is no transmitter with the transmitter ID, there is no stream with the stream ID that belongs to the transmitter, or there is no event with the JTI. Status code `404`. Applicable to 1 of 35 methods.*
* [`DeleteSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiNotFoundError`](./src/models/errors/delete-ssf-transmitter-transmitter-id-stream-stream-id-event-event-jti-not-found-error.ts): There is no transmitter with the transmitter ID, there is no stream with the stream ID that belongs to the transmitter, or there is no event with the JTI. Status code `404`. Applicable to 1 of 35 methods.*
* [`GetProbeDatabaseServiceUnavailableError`](./src/models/errors/get-probe-database-service-unavailable-error.ts): An error response indicating that the database connection is down. Status code `503`. Applicable to 1 of 35 methods.*
* [`GetProbeStartupServiceUnavailableError`](./src/models/errors/get-probe-startup-service-unavailable-error.ts): An error response indicating that this web application failed to start up. Status code `503`. Applicable to 1 of 35 methods.*
* [`ResponseValidationError`](./src/models/errors/response-validation-error.ts): Type mismatch between the data returned from the server and the structure expected by the SDK. See `error.rawValue` for the raw value and `error.pretty()` for a nicely formatted multi-line string.

</details>

\* Check [the method documentation](#available-resources-and-operations) to see if the error is applicable.
<!-- End Error Handling [errors] -->

<!-- Start Custom HTTP Client [http-client] -->
## Custom HTTP Client

The TypeScript SDK makes API calls using an `HTTPClient` that wraps the native
[Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API). This
client is a thin wrapper around `fetch` and provides the ability to attach hooks
around the request lifecycle that can be used to modify the request or handle
errors and response.

The `HTTPClient` constructor takes an optional `fetcher` argument that can be
used to integrate a third-party HTTP client or when writing tests to mock out
the HTTP client and feed in fixtures.

The following example shows how to:
- route requests through a proxy server using [undici](https://www.npmjs.com/package/undici)'s ProxyAgent
- use the `"beforeRequest"` hook to add a custom header and a timeout to requests
- use the `"requestError"` hook to log errors

```typescript
import { Arena } from "authlete-arena";
import { ProxyAgent } from "undici";
import { HTTPClient } from "authlete-arena/lib/http";

const dispatcher = new ProxyAgent("http://proxy.example.com:8080");

const httpClient = new HTTPClient({
  // 'fetcher' takes a function that has the same signature as native 'fetch'.
  fetcher: (input, init) =>
    // 'dispatcher' is specific to undici and not part of the standard Fetch API.
    fetch(input, { ...init, dispatcher } as RequestInit),
});

httpClient.addHook("beforeRequest", (request) => {
  const nextRequest = new Request(request, {
    signal: request.signal || AbortSignal.timeout(5000)
  });

  nextRequest.headers.set("x-custom-header", "custom value");

  return nextRequest;
});

httpClient.addHook("requestError", (error, request) => {
  console.group("Request Error");
  console.log("Reason:", `${error}`);
  console.log("Endpoint:", `${request.method} ${request.url}`);
  console.groupEnd();
});

const sdk = new Arena({ httpClient: httpClient });
```
<!-- End Custom HTTP Client [http-client] -->

<!-- Start Debugging [debug] -->
## Debugging

You can setup your SDK to emit debug logs for SDK requests and responses.

You can pass a logger that matches `console`'s interface as an SDK option.

> [!WARNING]
> Beware that debug logging will reveal secrets, like API tokens in headers, in log messages printed to a console or files. It's recommended to use this feature only during local development and not in production.

```typescript
import { Arena } from "authlete-arena";

const sdk = new Arena({ debugLogger: console });
```

You can also enable a default debug logger by setting an environment variable `ARENA_DEBUG` to true.
<!-- End Debugging [debug] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

# Development

## Maturity

This SDK is in beta, and there may be breaking changes between versions without a major version update. Therefore, we recommend pinning usage
to a specific package version. This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

## Contributions

While we value open-source contributions to this SDK, this library is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation. 
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release. 

### SDK Created by [Speakeasy](https://www.speakeasy.com/?utm_source=authlete-arena&utm_campaign=typescript)

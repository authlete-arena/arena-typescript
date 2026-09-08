# Arena SDK

## Overview

### Available Operations

* [getWellKnownOauthProtectedResource](#getwellknownoauthprotectedresource) - OAuth 2.0 Protected Resource Metadata
* [getJwks](#getjwks) - JWK Set Document
* [getOpenapi](#getopenapi) - Retrieve the OpenAPI document of this web application.
* [getProbeDatabase](#getprobedatabase) - Database probe.
* [getProbeLiveness](#getprobeliveness) - Liveness probe for Kubernetes.
* [getProbeReadiness](#getprobereadiness) - Readiness probe for Kubernetes.
* [getProbeStartup](#getprobestartup) - Startup probe for Kubernetes.
* [postSsfTransmitter](#postssftransmitter) - Create a transmitter.
* [getSsfTransmitterTransmitterId](#getssftransmittertransmitterid) - Retrieve information about the transmitter.
* [putSsfTransmitterTransmitterId](#putssftransmittertransmitterid) - Update the transmitter.
* [deleteSsfTransmitterTransmitterId](#deletessftransmittertransmitterid) - Delete the transmitter.
* [patchSsfTransmitterTransmitterId](#patchssftransmittertransmitterid) - Apply a patch to the transmitter.
* [postSsfTransmitterTransmitterIdDelegateJwks](#postssftransmittertransmitteriddelegatejwks) - JWK Set Document Endpoint
* [postSsfTransmitterTransmitterIdDelegateStreamCreate](#postssftransmittertransmitteriddelegatestreamcreate) - Stream Create (HTTP POST to the configuration endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamRead](#postssftransmittertransmitteriddelegatestreamread) - Stream Read (HTTP GET to the configuration endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamUpdate](#postssftransmittertransmitteriddelegatestreamupdate) - Stream Update (HTTP PATCH to the configuration endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamReplace](#postssftransmittertransmitteriddelegatestreamreplace) - Stream Replace (HTTP PUT to the configuration endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamDelete](#postssftransmittertransmitteriddelegatestreamdelete) - Stream Delete (HTTP DELETE to the configuration endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamVerify](#postssftransmittertransmitteriddelegatestreamverify) - Stream Verify (HTTP POST to the verification endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamPollStreamId](#postssftransmittertransmitteriddelegatestreampollstreamid) - Stream Poll (HTTP POST to the poll endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamStatusRead](#postssftransmittertransmitteriddelegatestreamstatusread) - Stream Status Read (HTTP GET to the status endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamStatusUpdate](#postssftransmittertransmitteriddelegatestreamstatusupdate) - Stream Status Update (HTTP POST to the status endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamSubjectAdd](#postssftransmittertransmitteriddelegatestreamsubjectadd) - Stream Subject Add (HTTP POST to the add subject endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamSubjectRemove](#postssftransmittertransmitteriddelegatestreamsubjectremove) - Stream Subject Remove (HTTP POST to the remove subject endpoint)
* [postSsfTransmitterTransmitterIdDelegateStreamSubjectList](#postssftransmittertransmitteriddelegatestreamsubjectlist) - Stream Subject List (HTTP GET to the list subjects endpoint)
* [postSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResource](#postssftransmittertransmitteriddelegatewellknownoauthprotectedresource) - Protected Resource Metadata Endpoint (/.well-known/oauth-protected-resource)
* [postSsfTransmitterTransmitterIdDelegateWellKnownSsfConfiguration](#postssftransmittertransmitteriddelegatewellknownssfconfiguration) - Transmitter Metadata Endpoint (/.well-known/ssf-configuration)
* [postSsfTransmitterTransmitterIdEventRegister](#postssftransmittertransmitterideventregister) - Register an event.
* [getSsfTransmitterTransmitterIdStreamList](#getssftransmittertransmitteridstreamlist) - List streams.
* [getSsfTransmitterTransmitterIdStreamStreamId](#getssftransmittertransmitteridstreamstreamid) - Retrieve information about the stream.
* [deleteSsfTransmitterTransmitterIdStreamStreamId](#deletessftransmittertransmitteridstreamstreamid) - Delete the stream.
* [postSsfTransmitterTransmitterIdStreamStreamIdVerify](#postssftransmittertransmitteridstreamstreamidverify) - Register a verification event into the stream.
* [getSsfTransmitterTransmitterIdStreamStreamIdEventList](#getssftransmittertransmitteridstreamstreamideventlist) - List stream events.
* [getSsfTransmitterTransmitterIdStreamStreamIdEventEventJti](#getssftransmittertransmitteridstreamstreamideventeventjti) - Retrieve information about the event.
* [deleteSsfTransmitterTransmitterIdStreamStreamIdEventEventJti](#deletessftransmittertransmitteridstreamstreamideventeventjti) - Delete the event.

## getWellKnownOauthProtectedResource

This API publishes the protected resource metadata of this server in a manner conformant to [RFC 9728: OAuth 2.0 Protected Resource Metadata](https://www.rfc-editor.org/rfc/rfc9728.html).


RFC 9728: OAuth 2.0 Protected Resource Metadata
<https://www.rfc-editor.org/rfc/rfc9728.html>

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/.well-known/oauth-protected-resource" method="get" path="/.well-known/oauth-protected-resource" -->
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

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { getWellKnownOauthProtectedResource } from "authlete-arena/funcs/get-well-known-oauth-protected-resource.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await getWellKnownOauthProtectedResource(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("getWellKnownOauthProtectedResource failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetWellKnownOauthProtectedResourceRequest](../../models/operations/get-well-known-oauth-protected-resource-request.md)                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetWellKnownOauthProtectedResourceResponse](../../models/operations/get-well-known-oauth-protected-resource-response.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ArenaDefaultError | 4XX, 5XX                 | \*/\*                    |

## getJwks

This API publishes the JWK Set document of this server in a manner conformant to [RFC 7517: JSON Web Key (JWK)](https://www.rfc-editor.org/rfc/rfc7517.html).


RFC 7517: JSON Web Key (JWK)
<https://www.rfc-editor.org/rfc/rfc7517.html>

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/jwks" method="get" path="/jwks" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await arena.getJwks({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { getJwks } from "authlete-arena/funcs/get-jwks.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await getJwks(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("getJwks failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetJwksRequest](../../models/operations/get-jwks-request.md)                                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetJwksResponse](../../models/operations/get-jwks-response.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ArenaDefaultError | 4XX, 5XX                 | \*/\*                    |

## getOpenapi

This API publishes the OpenAPI document of this web application in a manner conformant to the [MicroProfile OpenAPI Specification](https://microprofile.io/).


MicroProfile OpenAPI Specification
<https://microprofile.io/>

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/openapi" method="get" path="/openapi" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await arena.getOpenapi({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { getOpenapi } from "authlete-arena/funcs/get-openapi.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await getOpenapi(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("getOpenapi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetOpenapiRequest](../../models/operations/get-openapi-request.md)                                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetOpenapiResponse](../../models/operations/get-openapi-response.md)\>**

### Errors

| Error Type                       | Status Code                      | Content Type                     |
| -------------------------------- | -------------------------------- | -------------------------------- |
| errors.GetOpenapiBadRequestError | 400                              | application/json                 |
| errors.ArenaDefaultError         | 4XX, 5XX                         | \*/\*                            |

## getProbeDatabase

This API is intended to check whether the database connection is alive or down.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/probe/database" method="get" path="/probe/database" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await arena.getProbeDatabase({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { getProbeDatabase } from "authlete-arena/funcs/get-probe-database.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await getProbeDatabase(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("getProbeDatabase failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetProbeDatabaseRequest](../../models/operations/get-probe-database-request.md)                                                                                    | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetProbeDatabaseResponse](../../models/operations/get-probe-database-response.md)\>**

### Errors

| Error Type                                     | Status Code                                    | Content Type                                   |
| ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| errors.GetProbeDatabaseServiceUnavailableError | 503                                            | application/json                               |
| errors.ArenaDefaultError                       | 4XX, 5XX                                       | \*/\*                                          |

## getProbeLiveness

This API is intended to serve as a Kubernetes liveness probe. Refer to [Liveness, Readiness, and Startup Probes](https://kubernetes.io/docs/concepts/configuration/liveness-readiness-startup-probes/) for details.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/probe/liveness" method="get" path="/probe/liveness" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await arena.getProbeLiveness({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { getProbeLiveness } from "authlete-arena/funcs/get-probe-liveness.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await getProbeLiveness(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("getProbeLiveness failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetProbeLivenessRequest](../../models/operations/get-probe-liveness-request.md)                                                                                    | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetProbeLivenessResponse](../../models/operations/get-probe-liveness-response.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ArenaDefaultError | 4XX, 5XX                 | \*/\*                    |

## getProbeReadiness

This API is intended to serve as a Kubernetes readiness probe. Refer to [Liveness, Readiness, and Startup Probes](https://kubernetes.io/docs/concepts/configuration/liveness-readiness-startup-probes/) for details.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/probe/readiness" method="get" path="/probe/readiness" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await arena.getProbeReadiness({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { getProbeReadiness } from "authlete-arena/funcs/get-probe-readiness.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await getProbeReadiness(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("getProbeReadiness failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetProbeReadinessRequest](../../models/operations/get-probe-readiness-request.md)                                                                                  | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetProbeReadinessResponse](../../models/operations/get-probe-readiness-response.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ArenaDefaultError | 4XX, 5XX                 | \*/\*                    |

## getProbeStartup

This API is intended to serve as a Kubernetes startup probe. Refer to [Liveness, Readiness, and Startup Probes](https://kubernetes.io/docs/concepts/configuration/liveness-readiness-startup-probes/) for details.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/probe/startup" method="get" path="/probe/startup" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await arena.getProbeStartup({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { getProbeStartup } from "authlete-arena/funcs/get-probe-startup.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await getProbeStartup(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("getProbeStartup failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetProbeStartupRequest](../../models/operations/get-probe-startup-request.md)                                                                                      | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetProbeStartupResponse](../../models/operations/get-probe-startup-response.md)\>**

### Errors

| Error Type                                    | Status Code                                   | Content Type                                  |
| --------------------------------------------- | --------------------------------------------- | --------------------------------------------- |
| errors.GetProbeStartupServiceUnavailableError | 503                                           | application/json                              |
| errors.ArenaDefaultError                      | 4XX, 5XX                                      | \*/\*                                         |

## postSsfTransmitter

Create a transmitter.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter" method="post" path="/ssf/transmitter" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.postSsfTransmitter({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    body: {
      metadata: {
        specVersion: "1_0",
        issuer: "https://transmitter.example.com",
        jwksUri: "https://transmitter.example.com/ssf/jwks",
        deliveryMethodsSupported: [
          "urn:ietf:rfc:8935",
          "urn:ietf:rfc:8936",
        ],
        configurationEndpoint: "https://transmitter.example.com/ssf/configuration",
        statusEndpoint: "https://transmitter.example.com/ssf/status",
        addSubjectEndpoint: "https://transmitter.example.com/ssf/add_subject",
        removeSubjectEndpoint: "https://transmitter.example.com/ssf/remove_subject",
        verificationEndpoint: "https://transmitter.example.com/ssf/verification",
        criticalSubjectMembers: [
          "tenant",
          "user",
        ],
        authorizationSchemes: [
          {
            specUrn: "urn:ietf:rfc:6749",
          },
          {
            specUrn: "urn:ietf:rfc:8705",
          },
          {
            specUrn: "urn:ietf:rfc:9449",
          },
        ],
      },
      settings: {
        name: "Transmitter Name",
        description: "Transmitter Description",
        maxClockSkewSeconds: 30,
        authorizationServers: [
          "http://host.docker.internal:13100",
          "https://as.example.com",
        ],
        introspectionConfigurations: [
          {
            scheme: "Basic",
            userId: "rs0",
            password: "rs0-secret",
            issuer: "https://trial.authlete.net",
          },
        ],
        eventsSupported: [
          "https://schemas.openid.net/secevent/caep/event-type/session-revoked",
          "https://schemas.openid.net/secevent/caep/event-type/token-claims-change",
          "https://schemas.openid.net/secevent/caep/event-type/credential-change",
          "https://schemas.openid.net/secevent/caep/event-type/assurance-level-change",
          "https://schemas.openid.net/secevent/caep/event-type/device-compliance-change",
          "https://schemas.openid.net/secevent/caep/event-type/session-established",
          "https://schemas.openid.net/secevent/caep/event-type/session-presented",
          "https://schemas.openid.net/secevent/caep/event-type/risk-level-change",
          "https://schemas.openid.net/secevent/risc/event-type/account-credential-change-required",
          "https://schemas.openid.net/secevent/risc/event-type/account-purged",
          "https://schemas.openid.net/secevent/risc/event-type/account-disabled",
          "https://schemas.openid.net/secevent/risc/event-type/account-enabled",
          "https://schemas.openid.net/secevent/risc/event-type/identifier-changed",
          "https://schemas.openid.net/secevent/risc/event-type/identifier-recycled",
          "https://schemas.openid.net/secevent/risc/event-type/credential-compromise",
          "https://schemas.openid.net/secevent/risc/event-type/opt-in",
          "https://schemas.openid.net/secevent/risc/event-type/opt-out-initiated",
          "https://schemas.openid.net/secevent/risc/event-type/opt-out-cancelled",
          "https://schemas.openid.net/secevent/risc/event-type/opt-out-effective",
          "https://schemas.openid.net/secevent/risc/event-type/recovery-activated",
          "https://schemas.openid.net/secevent/risc/event-type/recovery-information-changed",
          "https://schemas.openid.net/secevent/risc/event-type/sessions-revoked",
          "https://schemas.openid.net/secevent/ssf/event-type/verification",
          "https://schemas.openid.net/secevent/ssf/event-type/stream-updated",
          "urn:ietf:params:scim:event:feed:add",
          "urn:ietf:params:scim:event:feed:remove",
          "urn:ietf:params:scim:event:prov:create:notice",
          "urn:ietf:params:scim:event:prov:create:full",
          "urn:ietf:params:scim:event:prov:patch:notice",
          "urn:ietf:params:scim:event:prov:patch:full",
          "urn:ietf:params:scim:event:prov:put:notice",
          "urn:ietf:params:scim:event:prov:put:full",
          "urn:ietf:params:scim:event:prov:delete",
          "urn:ietf:params:scim:event:prov:activate",
          "urn:ietf:params:scim:event:prov:deactivate",
          "urn:ietf:params:scim:event:misc:asyncresp",
        ],
        minVerificationIntervalDefault: 0,
        inactivityTimeoutDefault: 0,
        pollEndpoint: "https://transmitter.example.com/ssf/poll/STREAM_ID",
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { postSsfTransmitter } from "authlete-arena/funcs/post-ssf-transmitter.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await postSsfTransmitter(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    body: {
      metadata: {
        specVersion: "1_0",
        issuer: "https://transmitter.example.com",
        jwksUri: "https://transmitter.example.com/ssf/jwks",
        deliveryMethodsSupported: [
          "urn:ietf:rfc:8935",
          "urn:ietf:rfc:8936",
        ],
        configurationEndpoint: "https://transmitter.example.com/ssf/configuration",
        statusEndpoint: "https://transmitter.example.com/ssf/status",
        addSubjectEndpoint: "https://transmitter.example.com/ssf/add_subject",
        removeSubjectEndpoint: "https://transmitter.example.com/ssf/remove_subject",
        verificationEndpoint: "https://transmitter.example.com/ssf/verification",
        criticalSubjectMembers: [
          "tenant",
          "user",
        ],
        authorizationSchemes: [
          {
            specUrn: "urn:ietf:rfc:6749",
          },
          {
            specUrn: "urn:ietf:rfc:8705",
          },
          {
            specUrn: "urn:ietf:rfc:9449",
          },
        ],
      },
      settings: {
        name: "Transmitter Name",
        description: "Transmitter Description",
        maxClockSkewSeconds: 30,
        authorizationServers: [
          "http://host.docker.internal:13100",
          "https://as.example.com",
        ],
        introspectionConfigurations: [
          {
            scheme: "Basic",
            userId: "rs0",
            password: "rs0-secret",
            issuer: "https://trial.authlete.net",
          },
        ],
        eventsSupported: [
          "https://schemas.openid.net/secevent/caep/event-type/session-revoked",
          "https://schemas.openid.net/secevent/caep/event-type/token-claims-change",
          "https://schemas.openid.net/secevent/caep/event-type/credential-change",
          "https://schemas.openid.net/secevent/caep/event-type/assurance-level-change",
          "https://schemas.openid.net/secevent/caep/event-type/device-compliance-change",
          "https://schemas.openid.net/secevent/caep/event-type/session-established",
          "https://schemas.openid.net/secevent/caep/event-type/session-presented",
          "https://schemas.openid.net/secevent/caep/event-type/risk-level-change",
          "https://schemas.openid.net/secevent/risc/event-type/account-credential-change-required",
          "https://schemas.openid.net/secevent/risc/event-type/account-purged",
          "https://schemas.openid.net/secevent/risc/event-type/account-disabled",
          "https://schemas.openid.net/secevent/risc/event-type/account-enabled",
          "https://schemas.openid.net/secevent/risc/event-type/identifier-changed",
          "https://schemas.openid.net/secevent/risc/event-type/identifier-recycled",
          "https://schemas.openid.net/secevent/risc/event-type/credential-compromise",
          "https://schemas.openid.net/secevent/risc/event-type/opt-in",
          "https://schemas.openid.net/secevent/risc/event-type/opt-out-initiated",
          "https://schemas.openid.net/secevent/risc/event-type/opt-out-cancelled",
          "https://schemas.openid.net/secevent/risc/event-type/opt-out-effective",
          "https://schemas.openid.net/secevent/risc/event-type/recovery-activated",
          "https://schemas.openid.net/secevent/risc/event-type/recovery-information-changed",
          "https://schemas.openid.net/secevent/risc/event-type/sessions-revoked",
          "https://schemas.openid.net/secevent/ssf/event-type/verification",
          "https://schemas.openid.net/secevent/ssf/event-type/stream-updated",
          "urn:ietf:params:scim:event:feed:add",
          "urn:ietf:params:scim:event:feed:remove",
          "urn:ietf:params:scim:event:prov:create:notice",
          "urn:ietf:params:scim:event:prov:create:full",
          "urn:ietf:params:scim:event:prov:patch:notice",
          "urn:ietf:params:scim:event:prov:patch:full",
          "urn:ietf:params:scim:event:prov:put:notice",
          "urn:ietf:params:scim:event:prov:put:full",
          "urn:ietf:params:scim:event:prov:delete",
          "urn:ietf:params:scim:event:prov:activate",
          "urn:ietf:params:scim:event:prov:deactivate",
          "urn:ietf:params:scim:event:misc:asyncresp",
        ],
        minVerificationIntervalDefault: 0,
        inactivityTimeoutDefault: 0,
        pollEndpoint: "https://transmitter.example.com/ssf/poll/STREAM_ID",
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("postSsfTransmitter failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PostSsfTransmitterRequest](../../models/operations/post-ssf-transmitter-request.md)                                                                                | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.PostSsfTransmitterResponse](../../models/operations/post-ssf-transmitter-response.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ArenaDefaultError | 4XX, 5XX                 | \*/\*                    |

## getSsfTransmitterTransmitterId

Retrieve information about the transmitter.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/ssf/transmitter/{transmitter_id}" method="get" path="/ssf/transmitter/{transmitter_id}" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.getSsfTransmitterTransmitterId({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { getSsfTransmitterTransmitterId } from "authlete-arena/funcs/get-ssf-transmitter-transmitter-id.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await getSsfTransmitterTransmitterId(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("getSsfTransmitterTransmitterId failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetSsfTransmitterTransmitterIdRequest](../../models/operations/get-ssf-transmitter-transmitter-id-request.md)                                                      | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetSsfTransmitterTransmitterIdResponse](../../models/operations/get-ssf-transmitter-transmitter-id-response.md)\>**

### Errors

| Error Type                                         | Status Code                                        | Content Type                                       |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| errors.GetSsfTransmitterTransmitterIdNotFoundError | 404                                                | application/json                                   |
| errors.ArenaDefaultError                           | 4XX, 5XX                                           | \*/\*                                              |

## putSsfTransmitterTransmitterId

Update the transmitter.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="put_/ssf/transmitter/{transmitter_id}" method="put" path="/ssf/transmitter/{transmitter_id}" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.putSsfTransmitterTransmitterId({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      metadata: {
        specVersion: "1_0",
        issuer: "https://transmitter.example.com",
        jwksUri: "https://transmitter.example.com/ssf/jwks",
        deliveryMethodsSupported: [
          "urn:ietf:rfc:8935",
          "urn:ietf:rfc:8936",
        ],
        configurationEndpoint: "https://transmitter.example.com/ssf/configuration",
        statusEndpoint: "https://transmitter.example.com/ssf/status",
        addSubjectEndpoint: "https://transmitter.example.com/ssf/add_subject",
        removeSubjectEndpoint: "https://transmitter.example.com/ssf/remove_subject",
        verificationEndpoint: "https://transmitter.example.com/ssf/verification",
        criticalSubjectMembers: [
          "tenant",
          "user",
        ],
        authorizationSchemes: [
          {
            specUrn: "urn:ietf:rfc:6749",
          },
          {
            specUrn: "urn:ietf:rfc:8705",
          },
          {
            specUrn: "urn:ietf:rfc:9449",
          },
        ],
      },
      settings: {
        name: "Transmitter Name",
        description: "Transmitter Description",
        maxClockSkewSeconds: 30,
        authorizationServers: [
          "http://host.docker.internal:13100",
          "https://as.example.com",
        ],
        introspectionConfigurations: [
          {
            scheme: "Basic",
            userId: "rs0",
            password: "rs0-secret",
            issuer: "https://trial.authlete.net",
          },
        ],
        eventsSupported: [
          "https://schemas.openid.net/secevent/caep/event-type/session-revoked",
          "https://schemas.openid.net/secevent/caep/event-type/token-claims-change",
          "https://schemas.openid.net/secevent/caep/event-type/credential-change",
          "https://schemas.openid.net/secevent/caep/event-type/assurance-level-change",
          "https://schemas.openid.net/secevent/caep/event-type/device-compliance-change",
          "https://schemas.openid.net/secevent/caep/event-type/session-established",
          "https://schemas.openid.net/secevent/caep/event-type/session-presented",
          "https://schemas.openid.net/secevent/caep/event-type/risk-level-change",
          "https://schemas.openid.net/secevent/risc/event-type/account-credential-change-required",
          "https://schemas.openid.net/secevent/risc/event-type/account-purged",
          "https://schemas.openid.net/secevent/risc/event-type/account-disabled",
          "https://schemas.openid.net/secevent/risc/event-type/account-enabled",
          "https://schemas.openid.net/secevent/risc/event-type/identifier-changed",
          "https://schemas.openid.net/secevent/risc/event-type/identifier-recycled",
          "https://schemas.openid.net/secevent/risc/event-type/credential-compromise",
          "https://schemas.openid.net/secevent/risc/event-type/opt-in",
          "https://schemas.openid.net/secevent/risc/event-type/opt-out-initiated",
          "https://schemas.openid.net/secevent/risc/event-type/opt-out-cancelled",
          "https://schemas.openid.net/secevent/risc/event-type/opt-out-effective",
          "https://schemas.openid.net/secevent/risc/event-type/recovery-activated",
          "https://schemas.openid.net/secevent/risc/event-type/recovery-information-changed",
          "https://schemas.openid.net/secevent/risc/event-type/sessions-revoked",
          "https://schemas.openid.net/secevent/ssf/event-type/verification",
          "https://schemas.openid.net/secevent/ssf/event-type/stream-updated",
          "urn:ietf:params:scim:event:feed:add",
          "urn:ietf:params:scim:event:feed:remove",
          "urn:ietf:params:scim:event:prov:create:notice",
          "urn:ietf:params:scim:event:prov:create:full",
          "urn:ietf:params:scim:event:prov:patch:notice",
          "urn:ietf:params:scim:event:prov:patch:full",
          "urn:ietf:params:scim:event:prov:put:notice",
          "urn:ietf:params:scim:event:prov:put:full",
          "urn:ietf:params:scim:event:prov:delete",
          "urn:ietf:params:scim:event:prov:activate",
          "urn:ietf:params:scim:event:prov:deactivate",
          "urn:ietf:params:scim:event:misc:asyncresp",
        ],
        minVerificationIntervalDefault: 0,
        inactivityTimeoutDefault: 0,
        pollEndpoint: "https://transmitter.example.com/ssf/poll/STREAM_ID",
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { putSsfTransmitterTransmitterId } from "authlete-arena/funcs/put-ssf-transmitter-transmitter-id.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await putSsfTransmitterTransmitterId(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      metadata: {
        specVersion: "1_0",
        issuer: "https://transmitter.example.com",
        jwksUri: "https://transmitter.example.com/ssf/jwks",
        deliveryMethodsSupported: [
          "urn:ietf:rfc:8935",
          "urn:ietf:rfc:8936",
        ],
        configurationEndpoint: "https://transmitter.example.com/ssf/configuration",
        statusEndpoint: "https://transmitter.example.com/ssf/status",
        addSubjectEndpoint: "https://transmitter.example.com/ssf/add_subject",
        removeSubjectEndpoint: "https://transmitter.example.com/ssf/remove_subject",
        verificationEndpoint: "https://transmitter.example.com/ssf/verification",
        criticalSubjectMembers: [
          "tenant",
          "user",
        ],
        authorizationSchemes: [
          {
            specUrn: "urn:ietf:rfc:6749",
          },
          {
            specUrn: "urn:ietf:rfc:8705",
          },
          {
            specUrn: "urn:ietf:rfc:9449",
          },
        ],
      },
      settings: {
        name: "Transmitter Name",
        description: "Transmitter Description",
        maxClockSkewSeconds: 30,
        authorizationServers: [
          "http://host.docker.internal:13100",
          "https://as.example.com",
        ],
        introspectionConfigurations: [
          {
            scheme: "Basic",
            userId: "rs0",
            password: "rs0-secret",
            issuer: "https://trial.authlete.net",
          },
        ],
        eventsSupported: [
          "https://schemas.openid.net/secevent/caep/event-type/session-revoked",
          "https://schemas.openid.net/secevent/caep/event-type/token-claims-change",
          "https://schemas.openid.net/secevent/caep/event-type/credential-change",
          "https://schemas.openid.net/secevent/caep/event-type/assurance-level-change",
          "https://schemas.openid.net/secevent/caep/event-type/device-compliance-change",
          "https://schemas.openid.net/secevent/caep/event-type/session-established",
          "https://schemas.openid.net/secevent/caep/event-type/session-presented",
          "https://schemas.openid.net/secevent/caep/event-type/risk-level-change",
          "https://schemas.openid.net/secevent/risc/event-type/account-credential-change-required",
          "https://schemas.openid.net/secevent/risc/event-type/account-purged",
          "https://schemas.openid.net/secevent/risc/event-type/account-disabled",
          "https://schemas.openid.net/secevent/risc/event-type/account-enabled",
          "https://schemas.openid.net/secevent/risc/event-type/identifier-changed",
          "https://schemas.openid.net/secevent/risc/event-type/identifier-recycled",
          "https://schemas.openid.net/secevent/risc/event-type/credential-compromise",
          "https://schemas.openid.net/secevent/risc/event-type/opt-in",
          "https://schemas.openid.net/secevent/risc/event-type/opt-out-initiated",
          "https://schemas.openid.net/secevent/risc/event-type/opt-out-cancelled",
          "https://schemas.openid.net/secevent/risc/event-type/opt-out-effective",
          "https://schemas.openid.net/secevent/risc/event-type/recovery-activated",
          "https://schemas.openid.net/secevent/risc/event-type/recovery-information-changed",
          "https://schemas.openid.net/secevent/risc/event-type/sessions-revoked",
          "https://schemas.openid.net/secevent/ssf/event-type/verification",
          "https://schemas.openid.net/secevent/ssf/event-type/stream-updated",
          "urn:ietf:params:scim:event:feed:add",
          "urn:ietf:params:scim:event:feed:remove",
          "urn:ietf:params:scim:event:prov:create:notice",
          "urn:ietf:params:scim:event:prov:create:full",
          "urn:ietf:params:scim:event:prov:patch:notice",
          "urn:ietf:params:scim:event:prov:patch:full",
          "urn:ietf:params:scim:event:prov:put:notice",
          "urn:ietf:params:scim:event:prov:put:full",
          "urn:ietf:params:scim:event:prov:delete",
          "urn:ietf:params:scim:event:prov:activate",
          "urn:ietf:params:scim:event:prov:deactivate",
          "urn:ietf:params:scim:event:misc:asyncresp",
        ],
        minVerificationIntervalDefault: 0,
        inactivityTimeoutDefault: 0,
        pollEndpoint: "https://transmitter.example.com/ssf/poll/STREAM_ID",
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("putSsfTransmitterTransmitterId failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PutSsfTransmitterTransmitterIdRequest](../../models/operations/put-ssf-transmitter-transmitter-id-request.md)                                                      | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.PutSsfTransmitterTransmitterIdResponse](../../models/operations/put-ssf-transmitter-transmitter-id-response.md)\>**

### Errors

| Error Type                                         | Status Code                                        | Content Type                                       |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| errors.PutSsfTransmitterTransmitterIdNotFoundError | 404                                                | application/json                                   |
| errors.ArenaDefaultError                           | 4XX, 5XX                                           | \*/\*                                              |

## deleteSsfTransmitterTransmitterId

Delete the transmitter.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="delete_/ssf/transmitter/{transmitter_id}" method="delete" path="/ssf/transmitter/{transmitter_id}" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.deleteSsfTransmitterTransmitterId({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { deleteSsfTransmitterTransmitterId } from "authlete-arena/funcs/delete-ssf-transmitter-transmitter-id.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await deleteSsfTransmitterTransmitterId(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("deleteSsfTransmitterTransmitterId failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.DeleteSsfTransmitterTransmitterIdRequest](../../models/operations/delete-ssf-transmitter-transmitter-id-request.md)                                                | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.DeleteSsfTransmitterTransmitterIdResponse](../../models/operations/delete-ssf-transmitter-transmitter-id-response.md)\>**

### Errors

| Error Type                                            | Status Code                                           | Content Type                                          |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| errors.DeleteSsfTransmitterTransmitterIdNotFoundError | 404                                                   | application/json                                      |
| errors.ArenaDefaultError                              | 4XX, 5XX                                              | \*/\*                                                 |

## patchSsfTransmitterTransmitterId

Apply a patch to the transmitter.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="patch_/ssf/transmitter/{transmitter_id}" method="patch" path="/ssf/transmitter/{transmitter_id}" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.patchSsfTransmitterTransmitterId({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      patch: [
        {
          op: "replace",
          path: "/settings/name",
          value: "My Transmitter",
        },
      ],
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { patchSsfTransmitterTransmitterId } from "authlete-arena/funcs/patch-ssf-transmitter-transmitter-id.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await patchSsfTransmitterTransmitterId(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      patch: [
        {
          op: "replace",
          path: "/settings/name",
          value: "My Transmitter",
        },
      ],
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("patchSsfTransmitterTransmitterId failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PatchSsfTransmitterTransmitterIdRequest](../../models/operations/patch-ssf-transmitter-transmitter-id-request.md)                                                  | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.PatchSsfTransmitterTransmitterIdResponse](../../models/operations/patch-ssf-transmitter-transmitter-id-response.md)\>**

### Errors

| Error Type                                             | Status Code                                            | Content Type                                           |
| ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| errors.PatchSsfTransmitterTransmitterIdBadRequestError | 400                                                    | application/json                                       |
| errors.PatchSsfTransmitterTransmitterIdNotFoundError   | 404                                                    | application/json                                       |
| errors.ArenaDefaultError                               | 4XX, 5XX                                               | \*/\*                                                  |

## postSsfTransmitterTransmitterIdDelegateJwks

This API assembles the transmitter's JWK Set document in the format required for publication at the `jwks_uri` specified in the transmitter's metadata.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/jwks" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/jwks" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.postSsfTransmitterTransmitterIdDelegateJwks({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "GET",
        uri: "https://transmitter.example.com/ssf/jwks",
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { postSsfTransmitterTransmitterIdDelegateJwks } from "authlete-arena/funcs/post-ssf-transmitter-transmitter-id-delegate-jwks.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await postSsfTransmitterTransmitterIdDelegateJwks(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "GET",
        uri: "https://transmitter.example.com/ssf/jwks",
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("postSsfTransmitterTransmitterIdDelegateJwks failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PostSsfTransmitterTransmitterIdDelegateJwksRequestRequest](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-jwks-request-request.md)           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.PostSsfTransmitterTransmitterIdDelegateJwksResponseResponse](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-jwks-response-response.md)\>**

### Errors

| Error Type                                                      | Status Code                                                     | Content Type                                                    |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| errors.PostSsfTransmitterTransmitterIdDelegateJwksNotFoundError | 404                                                             | application/json                                                |
| errors.ArenaDefaultError                                        | 4XX, 5XX                                                        | \*/\*                                                           |

## postSsfTransmitterTransmitterIdDelegateStreamCreate

This API processes a stream creation request, which is an HTTP POST request to the configuration endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/create" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/create" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.postSsfTransmitterTransmitterIdDelegateStreamCreate({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "POST",
        uri: "https://transmitter.example.com/ssf/configuration",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
        body: "{\n  \"events_requested\": [\n    \"https://schemas.openid.net/secevent/risc/event-type/account-disabled\",\n    \"https://schemas.openid.net/secevent/risc/event-type/account-enabled\",\n    \"https://schemas.openid.net/secevent/risc/event-type/credential-compromise\",\n    \"https://schemas.openid.net/secevent/ssf/event-type/verification\"\n  ],\n  \"delivery\": {\n    \"method\": \"urn:ietf:rfc:8935\",\n    \"endpoint_url\": \"http://host.docker.internal:17000/ssf/push/STREAM_ID\",\n    \"authorization_header\": \"Basic TU1/4whBU8FmZTJCDuTSqMfJPkAHjnCa9WdfPdbedh4=\"\n  },\n  \"description\": \"SSF Receiver\",\n  \"default_subjects\": \"NONE\"\n}\n",
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { postSsfTransmitterTransmitterIdDelegateStreamCreate } from "authlete-arena/funcs/post-ssf-transmitter-transmitter-id-delegate-stream-create.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await postSsfTransmitterTransmitterIdDelegateStreamCreate(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "POST",
        uri: "https://transmitter.example.com/ssf/configuration",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
        body: "{\n  \"events_requested\": [\n    \"https://schemas.openid.net/secevent/risc/event-type/account-disabled\",\n    \"https://schemas.openid.net/secevent/risc/event-type/account-enabled\",\n    \"https://schemas.openid.net/secevent/risc/event-type/credential-compromise\",\n    \"https://schemas.openid.net/secevent/ssf/event-type/verification\"\n  ],\n  \"delivery\": {\n    \"method\": \"urn:ietf:rfc:8935\",\n    \"endpoint_url\": \"http://host.docker.internal:17000/ssf/push/STREAM_ID\",\n    \"authorization_header\": \"Basic TU1/4whBU8FmZTJCDuTSqMfJPkAHjnCa9WdfPdbedh4=\"\n  },\n  \"description\": \"SSF Receiver\",\n  \"default_subjects\": \"NONE\"\n}\n",
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("postSsfTransmitterTransmitterIdDelegateStreamCreate failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                             | Type                                                                                                                                                                                  | Required                                                                                                                                                                              | Description                                                                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                             | [operations.PostSsfTransmitterTransmitterIdDelegateStreamCreateRequestRequest](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-create-request-request.md) | :heavy_check_mark:                                                                                                                                                                    | The request object to use for the request.                                                                                                                                            |
| `options`                                                                                                                                                                             | RequestOptions                                                                                                                                                                        | :heavy_minus_sign:                                                                                                                                                                    | Used to set various options for making HTTP requests.                                                                                                                                 |
| `options.fetchOptions`                                                                                                                                                                | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                               | :heavy_minus_sign:                                                                                                                                                                    | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed.        |
| `options.retries`                                                                                                                                                                     | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                         | :heavy_minus_sign:                                                                                                                                                                    | Enables retrying HTTP requests under certain failure conditions.                                                                                                                      |

### Response

**Promise\<[operations.PostSsfTransmitterTransmitterIdDelegateStreamCreateResponseResponse](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-create-response-response.md)\>**

### Errors

| Error Type                                                              | Status Code                                                             | Content Type                                                            |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| errors.PostSsfTransmitterTransmitterIdDelegateStreamCreateNotFoundError | 404                                                                     | application/json                                                        |
| errors.ArenaDefaultError                                                | 4XX, 5XX                                                                | \*/\*                                                                   |

## postSsfTransmitterTransmitterIdDelegateStreamRead

This API processes a stream read request, which is an HTTP GET request to the configuration endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/read" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/read" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.postSsfTransmitterTransmitterIdDelegateStreamRead({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "GET",
        uri: "https://transmitter.example.com/ssf/configuration?stream_id=stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { postSsfTransmitterTransmitterIdDelegateStreamRead } from "authlete-arena/funcs/post-ssf-transmitter-transmitter-id-delegate-stream-read.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await postSsfTransmitterTransmitterIdDelegateStreamRead(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "GET",
        uri: "https://transmitter.example.com/ssf/configuration?stream_id=stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("postSsfTransmitterTransmitterIdDelegateStreamRead failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                         | Type                                                                                                                                                                              | Required                                                                                                                                                                          | Description                                                                                                                                                                       |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                         | [operations.PostSsfTransmitterTransmitterIdDelegateStreamReadRequestRequest](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-read-request-request.md) | :heavy_check_mark:                                                                                                                                                                | The request object to use for the request.                                                                                                                                        |
| `options`                                                                                                                                                                         | RequestOptions                                                                                                                                                                    | :heavy_minus_sign:                                                                                                                                                                | Used to set various options for making HTTP requests.                                                                                                                             |
| `options.fetchOptions`                                                                                                                                                            | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                           | :heavy_minus_sign:                                                                                                                                                                | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed.    |
| `options.retries`                                                                                                                                                                 | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                     | :heavy_minus_sign:                                                                                                                                                                | Enables retrying HTTP requests under certain failure conditions.                                                                                                                  |

### Response

**Promise\<[operations.PostSsfTransmitterTransmitterIdDelegateStreamReadResponseResponse](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-read-response-response.md)\>**

### Errors

| Error Type                                                            | Status Code                                                           | Content Type                                                          |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| errors.PostSsfTransmitterTransmitterIdDelegateStreamReadNotFoundError | 404                                                                   | application/json                                                      |
| errors.ArenaDefaultError                                              | 4XX, 5XX                                                              | \*/\*                                                                 |

## postSsfTransmitterTransmitterIdDelegateStreamUpdate

This API processes a stream update request, which is an HTTP PATCH request to the configuration endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/update" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/update" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.postSsfTransmitterTransmitterIdDelegateStreamUpdate({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "PATCH",
        uri: "https://transmitter.example.com/ssf/configuration",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
        body: "{\n  \"stream_id\": \"stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt\",\n  \"events_requested\": [\n    \"https://schemas.openid.net/secevent/risc/event-type/account-disabled\",\n    \"https://schemas.openid.net/secevent/risc/event-type/account-enabled\",\n    \"https://schemas.openid.net/secevent/risc/event-type/credential-compromise\",\n    \"https://schemas.openid.net/secevent/ssf/event-type/verification\"\n  ],\n  \"delivery\": {\n    \"method\": \"urn:ietf:rfc:8935\",\n    \"endpoint_url\": \"http://host.docker.internal:17000/ssf/push/STREAM_ID\",\n    \"authorization_header\": \"Basic TU1/4whBU8FmZTJCDuTSqMfJPkAHjnCa9WdfPdbedh4=\"\n  },\n  \"description\": \"SSF Receiver\"\n}\n",
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { postSsfTransmitterTransmitterIdDelegateStreamUpdate } from "authlete-arena/funcs/post-ssf-transmitter-transmitter-id-delegate-stream-update.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await postSsfTransmitterTransmitterIdDelegateStreamUpdate(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "PATCH",
        uri: "https://transmitter.example.com/ssf/configuration",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
        body: "{\n  \"stream_id\": \"stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt\",\n  \"events_requested\": [\n    \"https://schemas.openid.net/secevent/risc/event-type/account-disabled\",\n    \"https://schemas.openid.net/secevent/risc/event-type/account-enabled\",\n    \"https://schemas.openid.net/secevent/risc/event-type/credential-compromise\",\n    \"https://schemas.openid.net/secevent/ssf/event-type/verification\"\n  ],\n  \"delivery\": {\n    \"method\": \"urn:ietf:rfc:8935\",\n    \"endpoint_url\": \"http://host.docker.internal:17000/ssf/push/STREAM_ID\",\n    \"authorization_header\": \"Basic TU1/4whBU8FmZTJCDuTSqMfJPkAHjnCa9WdfPdbedh4=\"\n  },\n  \"description\": \"SSF Receiver\"\n}\n",
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("postSsfTransmitterTransmitterIdDelegateStreamUpdate failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                             | Type                                                                                                                                                                                  | Required                                                                                                                                                                              | Description                                                                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                             | [operations.PostSsfTransmitterTransmitterIdDelegateStreamUpdateRequestRequest](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-update-request-request.md) | :heavy_check_mark:                                                                                                                                                                    | The request object to use for the request.                                                                                                                                            |
| `options`                                                                                                                                                                             | RequestOptions                                                                                                                                                                        | :heavy_minus_sign:                                                                                                                                                                    | Used to set various options for making HTTP requests.                                                                                                                                 |
| `options.fetchOptions`                                                                                                                                                                | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                               | :heavy_minus_sign:                                                                                                                                                                    | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed.        |
| `options.retries`                                                                                                                                                                     | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                         | :heavy_minus_sign:                                                                                                                                                                    | Enables retrying HTTP requests under certain failure conditions.                                                                                                                      |

### Response

**Promise\<[operations.PostSsfTransmitterTransmitterIdDelegateStreamUpdateResponseResponse](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-update-response-response.md)\>**

### Errors

| Error Type                                                              | Status Code                                                             | Content Type                                                            |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| errors.PostSsfTransmitterTransmitterIdDelegateStreamUpdateNotFoundError | 404                                                                     | application/json                                                        |
| errors.ArenaDefaultError                                                | 4XX, 5XX                                                                | \*/\*                                                                   |

## postSsfTransmitterTransmitterIdDelegateStreamReplace

This API processes a stream replace request, which is an HTTP PUT request to the configuration endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/replace" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/replace" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.postSsfTransmitterTransmitterIdDelegateStreamReplace({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "PUT",
        uri: "https://transmitter.example.com/ssf/configuration",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
        body: "{\n  \"stream_id\": \"stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt\",\n  \"events_requested\": [\n    \"https://schemas.openid.net/secevent/risc/event-type/account-disabled\",\n    \"https://schemas.openid.net/secevent/risc/event-type/account-enabled\",\n    \"https://schemas.openid.net/secevent/risc/event-type/credential-compromise\",\n    \"https://schemas.openid.net/secevent/ssf/event-type/verification\"\n  ],\n  \"delivery\": {\n    \"method\": \"urn:ietf:rfc:8935\",\n    \"endpoint_url\": \"http://host.docker.internal:17000/ssf/push/STREAM_ID\",\n    \"authorization_header\": \"Basic TU1/4whBU8FmZTJCDuTSqMfJPkAHjnCa9WdfPdbedh4=\"\n  },\n  \"description\": \"SSF Receiver\"\n}\n",
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { postSsfTransmitterTransmitterIdDelegateStreamReplace } from "authlete-arena/funcs/post-ssf-transmitter-transmitter-id-delegate-stream-replace.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await postSsfTransmitterTransmitterIdDelegateStreamReplace(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "PUT",
        uri: "https://transmitter.example.com/ssf/configuration",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
        body: "{\n  \"stream_id\": \"stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt\",\n  \"events_requested\": [\n    \"https://schemas.openid.net/secevent/risc/event-type/account-disabled\",\n    \"https://schemas.openid.net/secevent/risc/event-type/account-enabled\",\n    \"https://schemas.openid.net/secevent/risc/event-type/credential-compromise\",\n    \"https://schemas.openid.net/secevent/ssf/event-type/verification\"\n  ],\n  \"delivery\": {\n    \"method\": \"urn:ietf:rfc:8935\",\n    \"endpoint_url\": \"http://host.docker.internal:17000/ssf/push/STREAM_ID\",\n    \"authorization_header\": \"Basic TU1/4whBU8FmZTJCDuTSqMfJPkAHjnCa9WdfPdbedh4=\"\n  },\n  \"description\": \"SSF Receiver\"\n}\n",
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("postSsfTransmitterTransmitterIdDelegateStreamReplace failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                               | Type                                                                                                                                                                                    | Required                                                                                                                                                                                | Description                                                                                                                                                                             |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                               | [operations.PostSsfTransmitterTransmitterIdDelegateStreamReplaceRequestRequest](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-replace-request-request.md) | :heavy_check_mark:                                                                                                                                                                      | The request object to use for the request.                                                                                                                                              |
| `options`                                                                                                                                                                               | RequestOptions                                                                                                                                                                          | :heavy_minus_sign:                                                                                                                                                                      | Used to set various options for making HTTP requests.                                                                                                                                   |
| `options.fetchOptions`                                                                                                                                                                  | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                                 | :heavy_minus_sign:                                                                                                                                                                      | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed.          |
| `options.retries`                                                                                                                                                                       | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                           | :heavy_minus_sign:                                                                                                                                                                      | Enables retrying HTTP requests under certain failure conditions.                                                                                                                        |

### Response

**Promise\<[operations.PostSsfTransmitterTransmitterIdDelegateStreamReplaceResponseResponse](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-replace-response-response.md)\>**

### Errors

| Error Type                                                               | Status Code                                                              | Content Type                                                             |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| errors.PostSsfTransmitterTransmitterIdDelegateStreamReplaceNotFoundError | 404                                                                      | application/json                                                         |
| errors.ArenaDefaultError                                                 | 4XX, 5XX                                                                 | \*/\*                                                                    |

## postSsfTransmitterTransmitterIdDelegateStreamDelete

This API processes a stream deletion request, which is an HTTP DELETE request to the configuration endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/delete" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/delete" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.postSsfTransmitterTransmitterIdDelegateStreamDelete({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "DELETE",
        uri: "https://transmitter.example.com/ssf/configuration?stream_id=STREAM_ID",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { postSsfTransmitterTransmitterIdDelegateStreamDelete } from "authlete-arena/funcs/post-ssf-transmitter-transmitter-id-delegate-stream-delete.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await postSsfTransmitterTransmitterIdDelegateStreamDelete(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "DELETE",
        uri: "https://transmitter.example.com/ssf/configuration?stream_id=STREAM_ID",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("postSsfTransmitterTransmitterIdDelegateStreamDelete failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                             | Type                                                                                                                                                                                  | Required                                                                                                                                                                              | Description                                                                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                             | [operations.PostSsfTransmitterTransmitterIdDelegateStreamDeleteRequestRequest](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-delete-request-request.md) | :heavy_check_mark:                                                                                                                                                                    | The request object to use for the request.                                                                                                                                            |
| `options`                                                                                                                                                                             | RequestOptions                                                                                                                                                                        | :heavy_minus_sign:                                                                                                                                                                    | Used to set various options for making HTTP requests.                                                                                                                                 |
| `options.fetchOptions`                                                                                                                                                                | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                               | :heavy_minus_sign:                                                                                                                                                                    | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed.        |
| `options.retries`                                                                                                                                                                     | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                         | :heavy_minus_sign:                                                                                                                                                                    | Enables retrying HTTP requests under certain failure conditions.                                                                                                                      |

### Response

**Promise\<[operations.PostSsfTransmitterTransmitterIdDelegateStreamDeleteResponseResponse](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-delete-response-response.md)\>**

### Errors

| Error Type                                                              | Status Code                                                             | Content Type                                                            |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| errors.PostSsfTransmitterTransmitterIdDelegateStreamDeleteNotFoundError | 404                                                                     | application/json                                                        |
| errors.ArenaDefaultError                                                | 4XX, 5XX                                                                | \*/\*                                                                   |

## postSsfTransmitterTransmitterIdDelegateStreamVerify

This API processes a verification request, which is an HTTP POST request to the verification endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/verify" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/verify" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.postSsfTransmitterTransmitterIdDelegateStreamVerify({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "POST",
        uri: "https://transmitter.example.com/ssf/verification",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
        body: "{\n  \"stream_id\": \"stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt\",\n  \"state\": \"FjpSK9qVTF\"\n}\n",
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { postSsfTransmitterTransmitterIdDelegateStreamVerify } from "authlete-arena/funcs/post-ssf-transmitter-transmitter-id-delegate-stream-verify.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await postSsfTransmitterTransmitterIdDelegateStreamVerify(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "POST",
        uri: "https://transmitter.example.com/ssf/verification",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
        body: "{\n  \"stream_id\": \"stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt\",\n  \"state\": \"FjpSK9qVTF\"\n}\n",
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("postSsfTransmitterTransmitterIdDelegateStreamVerify failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                             | Type                                                                                                                                                                                  | Required                                                                                                                                                                              | Description                                                                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                             | [operations.PostSsfTransmitterTransmitterIdDelegateStreamVerifyRequestRequest](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-verify-request-request.md) | :heavy_check_mark:                                                                                                                                                                    | The request object to use for the request.                                                                                                                                            |
| `options`                                                                                                                                                                             | RequestOptions                                                                                                                                                                        | :heavy_minus_sign:                                                                                                                                                                    | Used to set various options for making HTTP requests.                                                                                                                                 |
| `options.fetchOptions`                                                                                                                                                                | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                               | :heavy_minus_sign:                                                                                                                                                                    | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed.        |
| `options.retries`                                                                                                                                                                     | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                         | :heavy_minus_sign:                                                                                                                                                                    | Enables retrying HTTP requests under certain failure conditions.                                                                                                                      |

### Response

**Promise\<[operations.PostSsfTransmitterTransmitterIdDelegateStreamVerifyResponseResponse](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-verify-response-response.md)\>**

### Errors

| Error Type                                                              | Status Code                                                             | Content Type                                                            |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| errors.PostSsfTransmitterTransmitterIdDelegateStreamVerifyNotFoundError | 404                                                                     | application/json                                                        |
| errors.ArenaDefaultError                                                | 4XX, 5XX                                                                | \*/\*                                                                   |

## postSsfTransmitterTransmitterIdDelegateStreamPollStreamId

This API processes a poll request, which is an HTTP POST request to the poll endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/poll/{stream_id}" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/poll/{stream_id}" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.postSsfTransmitterTransmitterIdDelegateStreamPollStreamId({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    streamId: "stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "POST",
        uri: "https://transmitter.example.com/ssf/poll/stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
        body: "{\n  \"returnImmediately\": true\n}\n",
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { postSsfTransmitterTransmitterIdDelegateStreamPollStreamId } from "authlete-arena/funcs/post-ssf-transmitter-transmitter-id-delegate-stream-poll-stream-id.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await postSsfTransmitterTransmitterIdDelegateStreamPollStreamId(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    streamId: "stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "POST",
        uri: "https://transmitter.example.com/ssf/poll/stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
        body: "{\n  \"returnImmediately\": true\n}\n",
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("postSsfTransmitterTransmitterIdDelegateStreamPollStreamId failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                                           | Type                                                                                                                                                                                                | Required                                                                                                                                                                                            | Description                                                                                                                                                                                         |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                                           | [operations.PostSsfTransmitterTransmitterIdDelegateStreamPollStreamIdRequestRequest](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-poll-stream-id-request-request.md) | :heavy_check_mark:                                                                                                                                                                                  | The request object to use for the request.                                                                                                                                                          |
| `options`                                                                                                                                                                                           | RequestOptions                                                                                                                                                                                      | :heavy_minus_sign:                                                                                                                                                                                  | Used to set various options for making HTTP requests.                                                                                                                                               |
| `options.fetchOptions`                                                                                                                                                                              | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                                             | :heavy_minus_sign:                                                                                                                                                                                  | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed.                      |
| `options.retries`                                                                                                                                                                                   | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                                                  | Enables retrying HTTP requests under certain failure conditions.                                                                                                                                    |

### Response

**Promise\<[operations.PostSsfTransmitterTransmitterIdDelegateStreamPollStreamIdResponseResponse](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-poll-stream-id-response-response.md)\>**

### Errors

| Error Type                                                                    | Status Code                                                                   | Content Type                                                                  |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| errors.PostSsfTransmitterTransmitterIdDelegateStreamPollStreamIdNotFoundError | 404                                                                           | application/json                                                              |
| errors.ArenaDefaultError                                                      | 4XX, 5XX                                                                      | \*/\*                                                                         |

## postSsfTransmitterTransmitterIdDelegateStreamStatusRead

This API processes a stream status read request, which is an HTTP GET request to the status endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/status/read" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/status/read" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.postSsfTransmitterTransmitterIdDelegateStreamStatusRead({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "GET",
        uri: "https://transmitter.example.com/ssf/status?stream_id=stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { postSsfTransmitterTransmitterIdDelegateStreamStatusRead } from "authlete-arena/funcs/post-ssf-transmitter-transmitter-id-delegate-stream-status-read.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await postSsfTransmitterTransmitterIdDelegateStreamStatusRead(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "GET",
        uri: "https://transmitter.example.com/ssf/status?stream_id=stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("postSsfTransmitterTransmitterIdDelegateStreamStatusRead failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                                      | Type                                                                                                                                                                                           | Required                                                                                                                                                                                       | Description                                                                                                                                                                                    |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                                      | [operations.PostSsfTransmitterTransmitterIdDelegateStreamStatusReadRequestRequest](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-status-read-request-request.md) | :heavy_check_mark:                                                                                                                                                                             | The request object to use for the request.                                                                                                                                                     |
| `options`                                                                                                                                                                                      | RequestOptions                                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                                        | :heavy_minus_sign:                                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed.                 |
| `options.retries`                                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                                               |

### Response

**Promise\<[operations.PostSsfTransmitterTransmitterIdDelegateStreamStatusReadResponseResponse](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-status-read-response-response.md)\>**

### Errors

| Error Type                                                                  | Status Code                                                                 | Content Type                                                                |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| errors.PostSsfTransmitterTransmitterIdDelegateStreamStatusReadNotFoundError | 404                                                                         | application/json                                                            |
| errors.ArenaDefaultError                                                    | 4XX, 5XX                                                                    | \*/\*                                                                       |

## postSsfTransmitterTransmitterIdDelegateStreamStatusUpdate

This API processes a stream status update request, which is an HTTP POST request to the status endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/status/update" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/status/update" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.postSsfTransmitterTransmitterIdDelegateStreamStatusUpdate({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "POST",
        uri: "https://transmitter.example.com/ssf/status",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
        body: "{\n  \"stream_id\": \"stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt\",\n  \"status\": \"enabled\",\n  \"reason\": \"The initial status\"\n}\n",
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { postSsfTransmitterTransmitterIdDelegateStreamStatusUpdate } from "authlete-arena/funcs/post-ssf-transmitter-transmitter-id-delegate-stream-status-update.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await postSsfTransmitterTransmitterIdDelegateStreamStatusUpdate(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "POST",
        uri: "https://transmitter.example.com/ssf/status",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
        body: "{\n  \"stream_id\": \"stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt\",\n  \"status\": \"enabled\",\n  \"reason\": \"The initial status\"\n}\n",
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("postSsfTransmitterTransmitterIdDelegateStreamStatusUpdate failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                                          | Type                                                                                                                                                                                               | Required                                                                                                                                                                                           | Description                                                                                                                                                                                        |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                                          | [operations.PostSsfTransmitterTransmitterIdDelegateStreamStatusUpdateRequestRequest](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-status-update-request-request.md) | :heavy_check_mark:                                                                                                                                                                                 | The request object to use for the request.                                                                                                                                                         |
| `options`                                                                                                                                                                                          | RequestOptions                                                                                                                                                                                     | :heavy_minus_sign:                                                                                                                                                                                 | Used to set various options for making HTTP requests.                                                                                                                                              |
| `options.fetchOptions`                                                                                                                                                                             | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                                            | :heavy_minus_sign:                                                                                                                                                                                 | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed.                     |
| `options.retries`                                                                                                                                                                                  | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                                      | :heavy_minus_sign:                                                                                                                                                                                 | Enables retrying HTTP requests under certain failure conditions.                                                                                                                                   |

### Response

**Promise\<[operations.PostSsfTransmitterTransmitterIdDelegateStreamStatusUpdateResponseResponse](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-status-update-response-response.md)\>**

### Errors

| Error Type                                                                    | Status Code                                                                   | Content Type                                                                  |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| errors.PostSsfTransmitterTransmitterIdDelegateStreamStatusUpdateNotFoundError | 404                                                                           | application/json                                                              |
| errors.ArenaDefaultError                                                      | 4XX, 5XX                                                                      | \*/\*                                                                         |

## postSsfTransmitterTransmitterIdDelegateStreamSubjectAdd

This API processes a subject add request, which is an HTTP POST request to the add subject endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/subject/add" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/subject/add" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.postSsfTransmitterTransmitterIdDelegateStreamSubjectAdd({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "POST",
        uri: "https://transmitter.example.com/ssf/add_subject",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
        body: "{\n  \"stream_id\": \"stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt\",\n  \"subject\": {\n    \"format\": \"email\",\n    \"email\": \"user@example.com\"\n  }\n}\n",
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { postSsfTransmitterTransmitterIdDelegateStreamSubjectAdd } from "authlete-arena/funcs/post-ssf-transmitter-transmitter-id-delegate-stream-subject-add.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await postSsfTransmitterTransmitterIdDelegateStreamSubjectAdd(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "POST",
        uri: "https://transmitter.example.com/ssf/add_subject",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
        body: "{\n  \"stream_id\": \"stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt\",\n  \"subject\": {\n    \"format\": \"email\",\n    \"email\": \"user@example.com\"\n  }\n}\n",
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("postSsfTransmitterTransmitterIdDelegateStreamSubjectAdd failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                                      | Type                                                                                                                                                                                           | Required                                                                                                                                                                                       | Description                                                                                                                                                                                    |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                                      | [operations.PostSsfTransmitterTransmitterIdDelegateStreamSubjectAddRequestRequest](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-subject-add-request-request.md) | :heavy_check_mark:                                                                                                                                                                             | The request object to use for the request.                                                                                                                                                     |
| `options`                                                                                                                                                                                      | RequestOptions                                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                                        | :heavy_minus_sign:                                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed.                 |
| `options.retries`                                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                                               |

### Response

**Promise\<[operations.PostSsfTransmitterTransmitterIdDelegateStreamSubjectAddResponseResponse](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-subject-add-response-response.md)\>**

### Errors

| Error Type                                                                  | Status Code                                                                 | Content Type                                                                |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| errors.PostSsfTransmitterTransmitterIdDelegateStreamSubjectAddNotFoundError | 404                                                                         | application/json                                                            |
| errors.ArenaDefaultError                                                    | 4XX, 5XX                                                                    | \*/\*                                                                       |

## postSsfTransmitterTransmitterIdDelegateStreamSubjectRemove

This API processes a subject remove request, which is an HTTP POST request to the remove subject endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/subject/remove" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/subject/remove" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.postSsfTransmitterTransmitterIdDelegateStreamSubjectRemove({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "POST",
        uri: "https://transmitter.example.com/ssf/remove_subject",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
        body: "{\n  \"stream_id\": \"stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt\",\n  \"subject\": {\n    \"format\": \"email\",\n    \"email\": \"user@example.com\"\n  }\n}\n",
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { postSsfTransmitterTransmitterIdDelegateStreamSubjectRemove } from "authlete-arena/funcs/post-ssf-transmitter-transmitter-id-delegate-stream-subject-remove.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await postSsfTransmitterTransmitterIdDelegateStreamSubjectRemove(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "POST",
        uri: "https://transmitter.example.com/ssf/remove_subject",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
        body: "{\n  \"stream_id\": \"stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt\",\n  \"subject\": {\n    \"format\": \"email\",\n    \"email\": \"user@example.com\"\n  }\n}\n",
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("postSsfTransmitterTransmitterIdDelegateStreamSubjectRemove failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                                            | Type                                                                                                                                                                                                 | Required                                                                                                                                                                                             | Description                                                                                                                                                                                          |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                                            | [operations.PostSsfTransmitterTransmitterIdDelegateStreamSubjectRemoveRequestRequest](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-subject-remove-request-request.md) | :heavy_check_mark:                                                                                                                                                                                   | The request object to use for the request.                                                                                                                                                           |
| `options`                                                                                                                                                                                            | RequestOptions                                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                                                   | Used to set various options for making HTTP requests.                                                                                                                                                |
| `options.fetchOptions`                                                                                                                                                                               | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                                              | :heavy_minus_sign:                                                                                                                                                                                   | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed.                       |
| `options.retries`                                                                                                                                                                                    | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                                        | :heavy_minus_sign:                                                                                                                                                                                   | Enables retrying HTTP requests under certain failure conditions.                                                                                                                                     |

### Response

**Promise\<[operations.PostSsfTransmitterTransmitterIdDelegateStreamSubjectRemoveResponseResponse](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-subject-remove-response-response.md)\>**

### Errors

| Error Type                                                                     | Status Code                                                                    | Content Type                                                                   |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| errors.PostSsfTransmitterTransmitterIdDelegateStreamSubjectRemoveNotFoundError | 404                                                                            | application/json                                                               |
| errors.ArenaDefaultError                                                       | 4XX, 5XX                                                                       | \*/\*                                                                          |

## postSsfTransmitterTransmitterIdDelegateStreamSubjectList

This API processes a subject list request, which is an HTTP GET request to the list subjects endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/subject/list" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/subject/list" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.postSsfTransmitterTransmitterIdDelegateStreamSubjectList({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "GET",
        uri: "https://transmitter.example.com/ssf/list_subjects?stream_id=stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { postSsfTransmitterTransmitterIdDelegateStreamSubjectList } from "authlete-arena/funcs/post-ssf-transmitter-transmitter-id-delegate-stream-subject-list.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await postSsfTransmitterTransmitterIdDelegateStreamSubjectList(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "GET",
        uri: "https://transmitter.example.com/ssf/list_subjects?stream_id=stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
        headers: [
          [
            "Authorization",
            "Bearer eyJ0eXAiOiJhdCtqd3QiLCJhbGciOiJFUzI1NiIsImtpZCI6InZ5SUNGbFhVUXlqSE9RUHFSV01laml5UG9uZ3hRbkdibXAydGRKOWMwaHMifQ.eyJzdWIiOiJzc2YtdXNlciIsImNsaWVudF9pZCI6InNzZi1yZWNlaXZlciIsInNjb3BlIjoic3NmOmFkbWluIiwiaWF0IjoxNzQ2NTAwNDAwLCJhdXRob3JpemF0aW9uX2RldGFpbHMiOlt7InR5cGUiOiJjZWRhci1wb2xpY3kiLCJwb2xpY3kiOiJwZXJtaXQocHJpbmNpcGFsLGFjdGlvbixyZXNvdXJjZSk7In0seyJ0eXBlIjoiY2VkYXItcG9saWN5IiwicG9saWN5IjoiZm9yYmlkKHByaW5jaXBhbCxhY3Rpb249PVNTRjo6U3RyZWFtOjpBY3Rpb246OlwiZGVsZXRlXCIscmVzb3VyY2U9PVNTRjo6U3RyZWFtOjpcInN0ajNvZHBjZmcxOXU2cTYydDJoN2swdWszdDdzcmtkYWk2ZTBjY2Q3amQ0b2dudFwiKTsifV0sImlzcyI6Imh0dHA6Ly9ob3N0LmRvY2tlci5pbnRlcm5hbDoxMzEwMCIsImV4cCI6MTE3NDY1MDA0MDAsImp0aSI6ImlwWUtWTURyMUFmWXhNY0gifQ.LQe6ikSYTNgkgZFnNlyfn5h5z9MT79-2iwV5OR6GUPR1Ha_2po6NpKxDo5_Epk6iT8TrnWgG20Q3mKJKVxZ4Vg",
          ],
        ],
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("postSsfTransmitterTransmitterIdDelegateStreamSubjectList failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                                        | Type                                                                                                                                                                                             | Required                                                                                                                                                                                         | Description                                                                                                                                                                                      |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                                        | [operations.PostSsfTransmitterTransmitterIdDelegateStreamSubjectListRequestRequest](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-subject-list-request-request.md) | :heavy_check_mark:                                                                                                                                                                               | The request object to use for the request.                                                                                                                                                       |
| `options`                                                                                                                                                                                        | RequestOptions                                                                                                                                                                                   | :heavy_minus_sign:                                                                                                                                                                               | Used to set various options for making HTTP requests.                                                                                                                                            |
| `options.fetchOptions`                                                                                                                                                                           | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                                          | :heavy_minus_sign:                                                                                                                                                                               | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed.                   |
| `options.retries`                                                                                                                                                                                | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                                    | :heavy_minus_sign:                                                                                                                                                                               | Enables retrying HTTP requests under certain failure conditions.                                                                                                                                 |

### Response

**Promise\<[operations.PostSsfTransmitterTransmitterIdDelegateStreamSubjectListResponseResponse](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-subject-list-response-response.md)\>**

### Errors

| Error Type                                                                   | Status Code                                                                  | Content Type                                                                 |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| errors.PostSsfTransmitterTransmitterIdDelegateStreamSubjectListNotFoundError | 404                                                                          | application/json                                                             |
| errors.ArenaDefaultError                                                     | 4XX, 5XX                                                                     | \*/\*                                                                        |

## postSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResource

This API assembles the transmitter's protected resource metadata in the format required for publication at the `/.well-known/oauth-protected-resource` endpoint.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/well-known/oauth-protected-resource" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/well-known/oauth-protected-resource" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.postSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResource({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "GET",
        uri: "https://transmitter.example.com/.well-known/oauth-protected-resource",
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { postSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResource } from "authlete-arena/funcs/post-ssf-transmitter-transmitter-id-delegate-well-known-oauth-protected-resource.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await postSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResource(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "GET",
        uri: "https://transmitter.example.com/.well-known/oauth-protected-resource",
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("postSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResource failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                                                                      | Type                                                                                                                                                                                                                           | Required                                                                                                                                                                                                                       | Description                                                                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                                                                      | [operations.PostSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResourceRequestRequest](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-well-known-oauth-protected-resource-request-request.md) | :heavy_check_mark:                                                                                                                                                                                                             | The request object to use for the request.                                                                                                                                                                                     |
| `options`                                                                                                                                                                                                                      | RequestOptions                                                                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                                                                        | :heavy_minus_sign:                                                                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed.                                                 |
| `options.retries`                                                                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                                                                               |

### Response

**Promise\<[operations.PostSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResourceResponseResponse](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-well-known-oauth-protected-resource-response-response.md)\>**

### Errors

| Error Type                                                                                 | Status Code                                                                                | Content Type                                                                               |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| errors.PostSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResourceNotFoundError | 404                                                                                        | application/json                                                                           |
| errors.ArenaDefaultError                                                                   | 4XX, 5XX                                                                                   | \*/\*                                                                                      |

## postSsfTransmitterTransmitterIdDelegateWellKnownSsfConfiguration

This API assembles the transmitter's metadata in the format required for publication at the `/.well-known/ssf-configuration` endpoint.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/well-known/ssf-configuration" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/well-known/ssf-configuration" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.postSsfTransmitterTransmitterIdDelegateWellKnownSsfConfiguration({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "GET",
        uri: "https://transmitter.example.com/.well-known/ssf-configuration",
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { postSsfTransmitterTransmitterIdDelegateWellKnownSsfConfiguration } from "authlete-arena/funcs/post-ssf-transmitter-transmitter-id-delegate-well-known-ssf-configuration.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await postSsfTransmitterTransmitterIdDelegateWellKnownSsfConfiguration(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      options: {
        pretty: true,
      },
      request: {
        method: "GET",
        uri: "https://transmitter.example.com/.well-known/ssf-configuration",
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("postSsfTransmitterTransmitterIdDelegateWellKnownSsfConfiguration failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                                                         | Type                                                                                                                                                                                                              | Required                                                                                                                                                                                                          | Description                                                                                                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                                                         | [operations.PostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationRequestRequest](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-well-known-ssf-configuration-request-request.md) | :heavy_check_mark:                                                                                                                                                                                                | The request object to use for the request.                                                                                                                                                                        |
| `options`                                                                                                                                                                                                         | RequestOptions                                                                                                                                                                                                    | :heavy_minus_sign:                                                                                                                                                                                                | Used to set various options for making HTTP requests.                                                                                                                                                             |
| `options.fetchOptions`                                                                                                                                                                                            | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                                                           | :heavy_minus_sign:                                                                                                                                                                                                | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed.                                    |
| `options.retries`                                                                                                                                                                                                 | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                                                     | :heavy_minus_sign:                                                                                                                                                                                                | Enables retrying HTTP requests under certain failure conditions.                                                                                                                                                  |

### Response

**Promise\<[operations.PostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationResponseResponse](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-well-known-ssf-configuration-response-response.md)\>**

### Errors

| Error Type                                                                           | Status Code                                                                          | Content Type                                                                         |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| errors.PostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationNotFoundError | 404                                                                                  | application/json                                                                     |
| errors.ArenaDefaultError                                                             | 4XX, 5XX                                                                             | \*/\*                                                                                |

## postSsfTransmitterTransmitterIdEventRegister

Register an event.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/event/register" method="post" path="/ssf/transmitter/{transmitter_id}/event/register" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.postSsfTransmitterTransmitterIdEventRegister({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      subId: {
        format: "iss_sub",
        iss: "https://example.com",
        sub: "user001",
      },
      events: {
        "https://schemas.openid.net/secevent/risc/event-type/credential-compromise": {
          "credential_type": "password",
        },
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { postSsfTransmitterTransmitterIdEventRegister } from "authlete-arena/funcs/post-ssf-transmitter-transmitter-id-event-register.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await postSsfTransmitterTransmitterIdEventRegister(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    body: {
      subId: {
        format: "iss_sub",
        iss: "https://example.com",
        sub: "user001",
      },
      events: {
        "https://schemas.openid.net/secevent/risc/event-type/credential-compromise": {
          "credential_type": "password",
        },
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("postSsfTransmitterTransmitterIdEventRegister failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PostSsfTransmitterTransmitterIdEventRegisterRequest](../../models/operations/post-ssf-transmitter-transmitter-id-event-register-request.md)                        | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.PostSsfTransmitterTransmitterIdEventRegisterResponse](../../models/operations/post-ssf-transmitter-transmitter-id-event-register-response.md)\>**

### Errors

| Error Type                                                       | Status Code                                                      | Content Type                                                     |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| errors.PostSsfTransmitterTransmitterIdEventRegisterNotFoundError | 404                                                              | application/json                                                 |
| errors.ArenaDefaultError                                         | 4XX, 5XX                                                         | \*/\*                                                            |

## getSsfTransmitterTransmitterIdStreamList

This API returns the streams that belong to the transmitter.

Search criteria can be specified using query parameters when calling the
API. For example, if the `status=enabled` query parameter is provided, only
streams whose status is `enabled` are returned; streams whose status is
`paused` or `disabled` are excluded from the response. Similarly, if the
`created_at_ge=2026-01-01T12:00:00` query parameter is specified, only
streams created on or after "2026-01-01 12:00:00 (UTC)" are returned.
Multiple search criteria can be combined.

The `limit` query parameter specifies the maximum number of streams
included in the response. If this parameter is omitted, the default value
of `50` is used. The value of `limit` must be between `1` and `200`,
inclusive.

If additional matching streams remain, the API response includes the
`next_cursor` response parameter. By specifying its value as the `cursor`
query parameter in the next API call, you can retrieve the next page of
streams starting from the position indicated by the cursor. Therefore, by
repeatedly calling the API with the `next_cursor` value returned in the
previous response as the value of the `cursor` query parameter, until the
response no longer contains `next_cursor`, you can retrieve all matching
streams.

If the `cursor` query parameter is included in an API call, all query
parameters that specify search criteria are ignored. The cursor preserves
the search criteria specified in the initial API call, so there is no need
to specify them again. Note, however, that the `limit` query parameter is
not considered a search criterion and can therefore be used together with
the `cursor` query parameter.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/ssf/transmitter/{transmitter_id}/stream/list" method="get" path="/ssf/transmitter/{transmitter_id}/stream/list" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.getSsfTransmitterTransmitterIdStreamList({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { getSsfTransmitterTransmitterIdStreamList } from "authlete-arena/funcs/get-ssf-transmitter-transmitter-id-stream-list.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await getSsfTransmitterTransmitterIdStreamList(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("getSsfTransmitterTransmitterIdStreamList failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetSsfTransmitterTransmitterIdStreamListRequest](../../models/operations/get-ssf-transmitter-transmitter-id-stream-list-request.md)                                | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetSsfTransmitterTransmitterIdStreamListResponse](../../models/operations/get-ssf-transmitter-transmitter-id-stream-list-response.md)\>**

### Errors

| Error Type                                                   | Status Code                                                  | Content Type                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| errors.GetSsfTransmitterTransmitterIdStreamListNotFoundError | 404                                                          | application/json                                             |
| errors.ArenaDefaultError                                     | 4XX, 5XX                                                     | \*/\*                                                        |

## getSsfTransmitterTransmitterIdStreamStreamId

Retrieve information about the stream.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/ssf/transmitter/{transmitter_id}/stream/{stream_id}" method="get" path="/ssf/transmitter/{transmitter_id}/stream/{stream_id}" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.getSsfTransmitterTransmitterIdStreamStreamId({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    pretty: true,
    streamId: "stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { getSsfTransmitterTransmitterIdStreamStreamId } from "authlete-arena/funcs/get-ssf-transmitter-transmitter-id-stream-stream-id.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await getSsfTransmitterTransmitterIdStreamStreamId(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    pretty: true,
    streamId: "stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("getSsfTransmitterTransmitterIdStreamStreamId failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetSsfTransmitterTransmitterIdStreamStreamIdRequest](../../models/operations/get-ssf-transmitter-transmitter-id-stream-stream-id-request.md)                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetSsfTransmitterTransmitterIdStreamStreamIdResponse](../../models/operations/get-ssf-transmitter-transmitter-id-stream-stream-id-response.md)\>**

### Errors

| Error Type                                                       | Status Code                                                      | Content Type                                                     |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| errors.GetSsfTransmitterTransmitterIdStreamStreamIdNotFoundError | 404                                                              | application/json                                                 |
| errors.ArenaDefaultError                                         | 4XX, 5XX                                                         | \*/\*                                                            |

## deleteSsfTransmitterTransmitterIdStreamStreamId

Delete the stream.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="delete_/ssf/transmitter/{transmitter_id}/stream/{stream_id}" method="delete" path="/ssf/transmitter/{transmitter_id}/stream/{stream_id}" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.deleteSsfTransmitterTransmitterIdStreamStreamId({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    pretty: true,
    streamId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { deleteSsfTransmitterTransmitterIdStreamStreamId } from "authlete-arena/funcs/delete-ssf-transmitter-transmitter-id-stream-stream-id.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await deleteSsfTransmitterTransmitterIdStreamStreamId(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    pretty: true,
    streamId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("deleteSsfTransmitterTransmitterIdStreamStreamId failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.DeleteSsfTransmitterTransmitterIdStreamStreamIdRequest](../../models/operations/delete-ssf-transmitter-transmitter-id-stream-stream-id-request.md)                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.DeleteSsfTransmitterTransmitterIdStreamStreamIdResponse](../../models/operations/delete-ssf-transmitter-transmitter-id-stream-stream-id-response.md)\>**

### Errors

| Error Type                                                          | Status Code                                                         | Content Type                                                        |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| errors.DeleteSsfTransmitterTransmitterIdStreamStreamIdNotFoundError | 404                                                                 | application/json                                                    |
| errors.ArenaDefaultError                                            | 4XX, 5XX                                                            | \*/\*                                                               |

## postSsfTransmitterTransmitterIdStreamStreamIdVerify

This API registers a verification event into the stream.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/stream/{stream_id}/verify" method="post" path="/ssf/transmitter/{transmitter_id}/stream/{stream_id}/verify" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.postSsfTransmitterTransmitterIdStreamStreamIdVerify({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    streamId: "stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { postSsfTransmitterTransmitterIdStreamStreamIdVerify } from "authlete-arena/funcs/post-ssf-transmitter-transmitter-id-stream-stream-id-verify.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await postSsfTransmitterTransmitterIdStreamStreamIdVerify(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    streamId: "stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("postSsfTransmitterTransmitterIdStreamStreamIdVerify failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PostSsfTransmitterTransmitterIdStreamStreamIdVerifyRequest](../../models/operations/post-ssf-transmitter-transmitter-id-stream-stream-id-verify-request.md)        | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.PostSsfTransmitterTransmitterIdStreamStreamIdVerifyResponse](../../models/operations/post-ssf-transmitter-transmitter-id-stream-stream-id-verify-response.md)\>**

### Errors

| Error Type                                                                | Status Code                                                               | Content Type                                                              |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| errors.PostSsfTransmitterTransmitterIdStreamStreamIdVerifyBadRequestError | 400                                                                       | application/json                                                          |
| errors.PostSsfTransmitterTransmitterIdStreamStreamIdVerifyNotFoundError   | 404                                                                       | application/json                                                          |
| errors.ArenaDefaultError                                                  | 4XX, 5XX                                                                  | \*/\*                                                                     |

## getSsfTransmitterTransmitterIdStreamStreamIdEventList

This API returns the events that have been dispatched to the stream.

Search criteria can be specified using query parameters when calling the
API. For example, if the
`event_identifier=https://schemas.openid.net/secevent/caep/event-type/session-revoked`
query parameter is provided, only events whose event identifier matches
the specified value are returned. Similarly, if the
`toe_ge=2026-01-01T12:00:00` query parameter is specified, only events
whose time of event (`toe`) is on or after "2026-01-01 12:00:00 (UTC)"
are returned. Multiple search criteria can be combined.

The `limit` query parameter specifies the maximum number of events
included in the response. If this parameter is omitted, the default value
of `50` is used. The value of `limit` must be between `1` and `200`,
inclusive.

If additional matching events remain, the API response includes the
`next_cursor` response parameter. By specifying its value as the `cursor`
query parameter in the next API call, you can retrieve the next page of
events starting from the position indicated by the cursor. Therefore, by
repeatedly calling the API with the `next_cursor` value returned in the
previous response as the value of the `cursor` query parameter, until the
response no longer contains `next_cursor`, you can retrieve all matching
events.

If the `cursor` query parameter is included in an API call, all query
parameters that specify search criteria are ignored. The cursor preserves
the search criteria specified in the initial API call, so there is no need
to specify them again. Note, however, that the `limit` query parameter is
not considered a search criterion and can therefore be used together with
the `cursor` query parameter.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/ssf/transmitter/{transmitter_id}/stream/{stream_id}/event/list" method="get" path="/ssf/transmitter/{transmitter_id}/stream/{stream_id}/event/list" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.getSsfTransmitterTransmitterIdStreamStreamIdEventList({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    streamId: "stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { getSsfTransmitterTransmitterIdStreamStreamIdEventList } from "authlete-arena/funcs/get-ssf-transmitter-transmitter-id-stream-stream-id-event-list.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await getSsfTransmitterTransmitterIdStreamStreamIdEventList(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    streamId: "stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("getSsfTransmitterTransmitterIdStreamStreamIdEventList failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetSsfTransmitterTransmitterIdStreamStreamIdEventListRequest](../../models/operations/get-ssf-transmitter-transmitter-id-stream-stream-id-event-list-request.md)   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetSsfTransmitterTransmitterIdStreamStreamIdEventListResponse](../../models/operations/get-ssf-transmitter-transmitter-id-stream-stream-id-event-list-response.md)\>**

### Errors

| Error Type                                                                | Status Code                                                               | Content Type                                                              |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| errors.GetSsfTransmitterTransmitterIdStreamStreamIdEventListNotFoundError | 404                                                                       | application/json                                                          |
| errors.ArenaDefaultError                                                  | 4XX, 5XX                                                                  | \*/\*                                                                     |

## getSsfTransmitterTransmitterIdStreamStreamIdEventEventJti

Retrieve information about the event.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/ssf/transmitter/{transmitter_id}/stream/{stream_id}/event/{event_jti}" method="get" path="/ssf/transmitter/{transmitter_id}/stream/{stream_id}/event/{event_jti}" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.getSsfTransmitterTransmitterIdStreamStreamIdEventEventJti({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    streamId: "stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
    eventJti: "<value>",
    pretty: true,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { getSsfTransmitterTransmitterIdStreamStreamIdEventEventJti } from "authlete-arena/funcs/get-ssf-transmitter-transmitter-id-stream-stream-id-event-event-jti.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await getSsfTransmitterTransmitterIdStreamStreamIdEventEventJti(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    streamId: "stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
    eventJti: "<value>",
    pretty: true,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("getSsfTransmitterTransmitterIdStreamStreamIdEventEventJti failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                             | Type                                                                                                                                                                                  | Required                                                                                                                                                                              | Description                                                                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                             | [operations.GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiRequest](../../models/operations/get-ssf-transmitter-transmitter-id-stream-stream-id-event-event-jti-request.md) | :heavy_check_mark:                                                                                                                                                                    | The request object to use for the request.                                                                                                                                            |
| `options`                                                                                                                                                                             | RequestOptions                                                                                                                                                                        | :heavy_minus_sign:                                                                                                                                                                    | Used to set various options for making HTTP requests.                                                                                                                                 |
| `options.fetchOptions`                                                                                                                                                                | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                               | :heavy_minus_sign:                                                                                                                                                                    | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed.        |
| `options.retries`                                                                                                                                                                     | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                         | :heavy_minus_sign:                                                                                                                                                                    | Enables retrying HTTP requests under certain failure conditions.                                                                                                                      |

### Response

**Promise\<[operations.GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiResponse](../../models/operations/get-ssf-transmitter-transmitter-id-stream-stream-id-event-event-jti-response.md)\>**

### Errors

| Error Type                                                                    | Status Code                                                                   | Content Type                                                                  |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| errors.GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiNotFoundError | 404                                                                           | application/json                                                              |
| errors.ArenaDefaultError                                                      | 4XX, 5XX                                                                      | \*/\*                                                                         |

## deleteSsfTransmitterTransmitterIdStreamStreamIdEventEventJti

Delete the event.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="delete_/ssf/transmitter/{transmitter_id}/stream/{stream_id}/event/{event_jti}" method="delete" path="/ssf/transmitter/{transmitter_id}/stream/{stream_id}/event/{event_jti}" -->
```typescript
import { Arena } from "authlete-arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.deleteSsfTransmitterTransmitterIdStreamStreamIdEventEventJti({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    streamId: "stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
    eventJti: "<value>",
    pretty: true,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "authlete-arena/core.js";
import { deleteSsfTransmitterTransmitterIdStreamStreamIdEventEventJti } from "authlete-arena/funcs/delete-ssf-transmitter-transmitter-id-stream-stream-id-event-event-jti.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await deleteSsfTransmitterTransmitterIdStreamStreamIdEventEventJti(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    streamId: "stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
    eventJti: "<value>",
    pretty: true,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("deleteSsfTransmitterTransmitterIdStreamStreamIdEventEventJti failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                                   | Type                                                                                                                                                                                        | Required                                                                                                                                                                                    | Description                                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                                   | [operations.DeleteSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiRequest](../../models/operations/delete-ssf-transmitter-transmitter-id-stream-stream-id-event-event-jti-request.md) | :heavy_check_mark:                                                                                                                                                                          | The request object to use for the request.                                                                                                                                                  |
| `options`                                                                                                                                                                                   | RequestOptions                                                                                                                                                                              | :heavy_minus_sign:                                                                                                                                                                          | Used to set various options for making HTTP requests.                                                                                                                                       |
| `options.fetchOptions`                                                                                                                                                                      | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                                     | :heavy_minus_sign:                                                                                                                                                                          | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed.              |
| `options.retries`                                                                                                                                                                           | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                               | :heavy_minus_sign:                                                                                                                                                                          | Enables retrying HTTP requests under certain failure conditions.                                                                                                                            |

### Response

**Promise\<[operations.DeleteSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiResponse](../../models/operations/delete-ssf-transmitter-transmitter-id-stream-stream-id-event-event-jti-response.md)\>**

### Errors

| Error Type                                                                       | Status Code                                                                      | Content Type                                                                     |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| errors.DeleteSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiNotFoundError | 404                                                                              | application/json                                                                 |
| errors.ArenaDefaultError                                                         | 4XX, 5XX                                                                         | \*/\*                                                                            |
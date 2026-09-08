# Delegate.WellKnown

## Overview

### Available Operations

* [protectedResource](#protectedresource) - Protected Resource Metadata Endpoint (/.well-known/oauth-protected-resource)
* [ssfConfiguration](#ssfconfiguration) - Transmitter Metadata Endpoint (/.well-known/ssf-configuration)

## protectedResource

This API assembles the transmitter's protected resource metadata in the format required for publication at the `/.well-known/oauth-protected-resource` endpoint.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/well-known/oauth-protected-resource" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/well-known/oauth-protected-resource" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.delegate.wellKnown.protectedResource({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { delegateWellKnownProtectedResource } from "@authlete/arena/funcs/delegate-well-known-protected-resource.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await delegateWellKnownProtectedResource(arena, {
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
    console.log("delegateWellKnownProtectedResource failed:", res.error);
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

## ssfConfiguration

This API assembles the transmitter's metadata in the format required for publication at the `/.well-known/ssf-configuration` endpoint.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/well-known/ssf-configuration" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/well-known/ssf-configuration" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.delegate.wellKnown.ssfConfiguration({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { delegateWellKnownSsfConfiguration } from "@authlete/arena/funcs/delegate-well-known-ssf-configuration.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await delegateWellKnownSsfConfiguration(arena, {
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
    console.log("delegateWellKnownSsfConfiguration failed:", res.error);
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
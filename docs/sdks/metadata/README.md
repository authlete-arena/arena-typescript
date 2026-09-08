# Metadata

## Overview

### Available Operations

* [getProtectedResource](#getprotectedresource) - OAuth 2.0 Protected Resource Metadata
* [getJwks](#getjwks) - JWK Set Document
* [getOpenApiDocument](#getopenapidocument) - Retrieve the OpenAPI document of this web application.

## getProtectedResource

This API publishes the protected resource metadata of this server in a manner conformant to [RFC 9728: OAuth 2.0 Protected Resource Metadata](https://www.rfc-editor.org/rfc/rfc9728.html).


RFC 9728: OAuth 2.0 Protected Resource Metadata
<https://www.rfc-editor.org/rfc/rfc9728.html>

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/.well-known/oauth-protected-resource" method="get" path="/.well-known/oauth-protected-resource" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await arena.metadata.getProtectedResource({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "@authlete/arena/core.js";
import { metadataGetProtectedResource } from "@authlete/arena/funcs/metadata-get-protected-resource.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await metadataGetProtectedResource(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("metadataGetProtectedResource failed:", res.error);
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
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await arena.metadata.getJwks({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "@authlete/arena/core.js";
import { metadataGetJwks } from "@authlete/arena/funcs/metadata-get-jwks.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await metadataGetJwks(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("metadataGetJwks failed:", res.error);
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

## getOpenApiDocument

This API publishes the OpenAPI document of this web application in a manner conformant to the [MicroProfile OpenAPI Specification](https://microprofile.io/).


MicroProfile OpenAPI Specification
<https://microprofile.io/>

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/openapi" method="get" path="/openapi" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await arena.metadata.getOpenApiDocument({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ArenaCore } from "@authlete/arena/core.js";
import { metadataGetOpenApiDocument } from "@authlete/arena/funcs/metadata-get-open-api-document.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await metadataGetOpenApiDocument(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("metadataGetOpenApiDocument failed:", res.error);
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
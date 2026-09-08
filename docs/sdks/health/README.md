# Health

## Overview

### Available Operations

* [database](#database) - Database probe.
* [liveness](#liveness) - Liveness probe for Kubernetes.
* [readiness](#readiness) - Readiness probe for Kubernetes.
* [startup](#startup) - Startup probe for Kubernetes.

## database

This API is intended to check whether the database connection is alive or down.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/probe/database" method="get" path="/probe/database" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await arena.health.database({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { healthDatabase } from "@authlete/arena/funcs/health-database.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await healthDatabase(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("healthDatabase failed:", res.error);
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

## liveness

This API is intended to serve as a Kubernetes liveness probe. Refer to [Liveness, Readiness, and Startup Probes](https://kubernetes.io/docs/concepts/configuration/liveness-readiness-startup-probes/) for details.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/probe/liveness" method="get" path="/probe/liveness" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await arena.health.liveness({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { healthLiveness } from "@authlete/arena/funcs/health-liveness.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await healthLiveness(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("healthLiveness failed:", res.error);
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

## readiness

This API is intended to serve as a Kubernetes readiness probe. Refer to [Liveness, Readiness, and Startup Probes](https://kubernetes.io/docs/concepts/configuration/liveness-readiness-startup-probes/) for details.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/probe/readiness" method="get" path="/probe/readiness" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await arena.health.readiness({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { healthReadiness } from "@authlete/arena/funcs/health-readiness.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await healthReadiness(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("healthReadiness failed:", res.error);
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

## startup

This API is intended to serve as a Kubernetes startup probe. Refer to [Liveness, Readiness, and Startup Probes](https://kubernetes.io/docs/concepts/configuration/liveness-readiness-startup-probes/) for details.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/probe/startup" method="get" path="/probe/startup" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await arena.health.startup({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { healthStartup } from "@authlete/arena/funcs/health-startup.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await healthStartup(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("healthStartup failed:", res.error);
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
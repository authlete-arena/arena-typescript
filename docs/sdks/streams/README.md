# Streams

## Overview

### Available Operations

* [list](#list) - List streams.
* [get](#get) - Retrieve information about the stream.
* [delete](#delete) - Delete the stream.
* [verify](#verify) - Register a verification event into the stream.

## list

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
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.streams.list({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { streamsList } from "@authlete/arena/funcs/streams-list.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await streamsList(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("streamsList failed:", res.error);
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

## get

Retrieve information about the stream.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/ssf/transmitter/{transmitter_id}/stream/{stream_id}" method="get" path="/ssf/transmitter/{transmitter_id}/stream/{stream_id}" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.streams.get({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { streamsGet } from "@authlete/arena/funcs/streams-get.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await streamsGet(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    pretty: true,
    streamId: "stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("streamsGet failed:", res.error);
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

## delete

Delete the stream.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="delete_/ssf/transmitter/{transmitter_id}/stream/{stream_id}" method="delete" path="/ssf/transmitter/{transmitter_id}/stream/{stream_id}" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.streams.delete({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { streamsDelete } from "@authlete/arena/funcs/streams-delete.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await streamsDelete(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    pretty: true,
    streamId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("streamsDelete failed:", res.error);
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

## verify

This API registers a verification event into the stream.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/stream/{stream_id}/verify" method="post" path="/ssf/transmitter/{transmitter_id}/stream/{stream_id}/verify" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.streams.verify({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { streamsVerify } from "@authlete/arena/funcs/streams-verify.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await streamsVerify(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    streamId: "stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("streamsVerify failed:", res.error);
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
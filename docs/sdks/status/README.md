# Delegate.Status

## Overview

### Available Operations

* [get](#get) - Stream Status Read (HTTP GET to the status endpoint)
* [update](#update) - Stream Status Update (HTTP POST to the status endpoint)

## get

This API processes a stream status read request, which is an HTTP GET request to the status endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/status/read" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/status/read" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.delegate.status.get({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { delegateStatusGet } from "@authlete/arena/funcs/delegate-status-get.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await delegateStatusGet(arena, {
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
    console.log("delegateStatusGet failed:", res.error);
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

## update

This API processes a stream status update request, which is an HTTP POST request to the status endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/status/update" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/status/update" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.delegate.status.update({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { delegateStatusUpdate } from "@authlete/arena/funcs/delegate-status-update.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await delegateStatusUpdate(arena, {
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
    console.log("delegateStatusUpdate failed:", res.error);
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
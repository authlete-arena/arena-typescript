# Delegate.Streams

## Overview

### Available Operations

* [create](#create) - Stream Create (HTTP POST to the configuration endpoint)
* [get](#get) - Stream Read (HTTP GET to the configuration endpoint)
* [update](#update) - Stream Update (HTTP PATCH to the configuration endpoint)
* [replace](#replace) - Stream Replace (HTTP PUT to the configuration endpoint)
* [delete](#delete) - Stream Delete (HTTP DELETE to the configuration endpoint)
* [verify](#verify) - Stream Verify (HTTP POST to the verification endpoint)
* [poll](#poll) - Stream Poll (HTTP POST to the poll endpoint)

## create

This API processes a stream creation request, which is an HTTP POST request to the configuration endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/create" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/create" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.delegate.streams.create({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { delegateStreamsCreate } from "@authlete/arena/funcs/delegate-streams-create.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await delegateStreamsCreate(arena, {
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
    console.log("delegateStreamsCreate failed:", res.error);
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

## get

This API processes a stream read request, which is an HTTP GET request to the configuration endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/read" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/read" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.delegate.streams.get({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { delegateStreamsGet } from "@authlete/arena/funcs/delegate-streams-get.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await delegateStreamsGet(arena, {
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
    console.log("delegateStreamsGet failed:", res.error);
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

## update

This API processes a stream update request, which is an HTTP PATCH request to the configuration endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/update" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/update" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.delegate.streams.update({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { delegateStreamsUpdate } from "@authlete/arena/funcs/delegate-streams-update.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await delegateStreamsUpdate(arena, {
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
    console.log("delegateStreamsUpdate failed:", res.error);
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

## replace

This API processes a stream replace request, which is an HTTP PUT request to the configuration endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/replace" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/replace" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.delegate.streams.replace({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { delegateStreamsReplace } from "@authlete/arena/funcs/delegate-streams-replace.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await delegateStreamsReplace(arena, {
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
    console.log("delegateStreamsReplace failed:", res.error);
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

## delete

This API processes a stream deletion request, which is an HTTP DELETE request to the configuration endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/delete" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/delete" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.delegate.streams.delete({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { delegateStreamsDelete } from "@authlete/arena/funcs/delegate-streams-delete.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await delegateStreamsDelete(arena, {
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
    console.log("delegateStreamsDelete failed:", res.error);
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

## verify

This API processes a verification request, which is an HTTP POST request to the verification endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/verify" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/verify" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.delegate.streams.verify({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { delegateStreamsVerify } from "@authlete/arena/funcs/delegate-streams-verify.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await delegateStreamsVerify(arena, {
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
    console.log("delegateStreamsVerify failed:", res.error);
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

## poll

This API processes a poll request, which is an HTTP POST request to the poll endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/poll/{stream_id}" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/poll/{stream_id}" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.delegate.streams.poll({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { delegateStreamsPoll } from "@authlete/arena/funcs/delegate-streams-poll.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await delegateStreamsPoll(arena, {
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
    console.log("delegateStreamsPoll failed:", res.error);
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
# Delegate.Subjects

## Overview

### Available Operations

* [add](#add) - Stream Subject Add (HTTP POST to the add subject endpoint)
* [remove](#remove) - Stream Subject Remove (HTTP POST to the remove subject endpoint)
* [list](#list) - Stream Subject List (HTTP GET to the list subjects endpoint)

## add

This API processes a subject add request, which is an HTTP POST request to the add subject endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/subject/add" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/subject/add" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.delegate.subjects.add({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { delegateSubjectsAdd } from "@authlete/arena/funcs/delegate-subjects-add.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await delegateSubjectsAdd(arena, {
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
    console.log("delegateSubjectsAdd failed:", res.error);
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

## remove

This API processes a subject remove request, which is an HTTP POST request to the remove subject endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/subject/remove" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/subject/remove" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.delegate.subjects.remove({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { delegateSubjectsRemove } from "@authlete/arena/funcs/delegate-subjects-remove.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await delegateSubjectsRemove(arena, {
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
    console.log("delegateSubjectsRemove failed:", res.error);
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

## list

This API processes a subject list request, which is an HTTP GET request to the list subjects endpoint of the transmitter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/delegate/stream/subject/list" method="post" path="/ssf/transmitter/{transmitter_id}/delegate/stream/subject/list" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.delegate.subjects.list({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { delegateSubjectsList } from "@authlete/arena/funcs/delegate-subjects-list.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await delegateSubjectsList(arena, {
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
    console.log("delegateSubjectsList failed:", res.error);
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
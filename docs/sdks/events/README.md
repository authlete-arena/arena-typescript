# Events

## Overview

### Available Operations

* [register](#register) - Register an event.
* [list](#list) - List stream events.
* [get](#get) - Retrieve information about the event.
* [delete](#delete) - Delete the event.

## register

Register an event.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter/{transmitter_id}/event/register" method="post" path="/ssf/transmitter/{transmitter_id}/event/register" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.events.register({
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
        "https://schemas.openid.net/secevent/risc/event-type/credential-compromise": {},
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
import { eventsRegister } from "@authlete/arena/funcs/events-register.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await eventsRegister(arena, {
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
        "https://schemas.openid.net/secevent/risc/event-type/credential-compromise": {},
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("eventsRegister failed:", res.error);
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

## list

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
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.events.list({
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
import { eventsList } from "@authlete/arena/funcs/events-list.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await eventsList(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
    streamId: "stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("eventsList failed:", res.error);
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

## get

Retrieve information about the event.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/ssf/transmitter/{transmitter_id}/stream/{stream_id}/event/{event_jti}" method="get" path="/ssf/transmitter/{transmitter_id}/stream/{stream_id}/event/{event_jti}" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.events.get({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { eventsGet } from "@authlete/arena/funcs/events-get.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await eventsGet(arena, {
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
    console.log("eventsGet failed:", res.error);
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

## delete

Delete the event.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="delete_/ssf/transmitter/{transmitter_id}/stream/{stream_id}/event/{event_jti}" method="delete" path="/ssf/transmitter/{transmitter_id}/stream/{stream_id}/event/{event_jti}" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.events.delete({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { eventsDelete } from "@authlete/arena/funcs/events-delete.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await eventsDelete(arena, {
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
    console.log("eventsDelete failed:", res.error);
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
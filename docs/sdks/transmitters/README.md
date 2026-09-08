# Transmitters

## Overview

### Available Operations

* [create](#create) - Create a transmitter.
* [get](#get) - Retrieve information about the transmitter.
* [update](#update) - Update the transmitter.
* [delete](#delete) - Delete the transmitter.
* [patch](#patch) - Apply a patch to the transmitter.

## create

Create a transmitter.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/ssf/transmitter" method="post" path="/ssf/transmitter" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.transmitters.create({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { transmittersCreate } from "@authlete/arena/funcs/transmitters-create.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await transmittersCreate(arena, {
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
    console.log("transmittersCreate failed:", res.error);
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

## get

Retrieve information about the transmitter.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/ssf/transmitter/{transmitter_id}" method="get" path="/ssf/transmitter/{transmitter_id}" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.transmitters.get({
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
import { transmittersGet } from "@authlete/arena/funcs/transmitters-get.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await transmittersGet(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "trl9f1ropjojsj2gv8rrbc7k9ku918lpum9s4n7ophngl3sa",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("transmittersGet failed:", res.error);
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

## update

Update the transmitter.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="put_/ssf/transmitter/{transmitter_id}" method="put" path="/ssf/transmitter/{transmitter_id}" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.transmitters.update({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { transmittersUpdate } from "@authlete/arena/funcs/transmitters-update.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await transmittersUpdate(arena, {
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
    console.log("transmittersUpdate failed:", res.error);
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

## delete

Delete the transmitter.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="delete_/ssf/transmitter/{transmitter_id}" method="delete" path="/ssf/transmitter/{transmitter_id}" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.transmitters.delete({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { transmittersDelete } from "@authlete/arena/funcs/transmitters-delete.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await transmittersDelete(arena, {
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
    pretty: true,
    transmitterId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("transmittersDelete failed:", res.error);
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

## patch

Apply a patch to the transmitter.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="patch_/ssf/transmitter/{transmitter_id}" method="patch" path="/ssf/transmitter/{transmitter_id}" -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const result = await arena.transmitters.patch({
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
import { ArenaCore } from "@authlete/arena/core.js";
import { transmittersPatch } from "@authlete/arena/funcs/transmitters-patch.js";

// Use `ArenaCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const arena = new ArenaCore({
  serverURL: "https://api.example.com",
  security: {
    bearer: process.env["ARENA_BEARER"] ?? "",
  },
});

async function run() {
  const res = await transmittersPatch(arena, {
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
    console.log("transmittersPatch failed:", res.error);
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
# GetSsfTransmitterTransmitterIdStreamStreamIdResponseBody

Successfully retrieved information about the stream.

## Example Usage

```typescript
import { GetSsfTransmitterTransmitterIdStreamStreamIdResponseBody } from "authlete-arena/models/operations";

let value: GetSsfTransmitterTransmitterIdStreamStreamIdResponseBody = {
  stream: {
    createdAt: "2025-06-20T06:47:00",
    updatedAt: "2025-06-21T06:47:00",
    streamId: "stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
    metadata: {
      streamId: "stj3odpcfg19u6q62t2h7k0uk3t7srkdai6e0ccd7jd4ognt",
      iss: "https://transmitter.example.com",
      aud: "ssf-receiver",
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
      eventsRequested: [
        "https://schemas.openid.net/secevent/risc/event-type/account-disabled",
        "https://schemas.openid.net/secevent/risc/event-type/account-enabled",
        "https://schemas.openid.net/secevent/risc/event-type/credential-compromise",
        "https://schemas.openid.net/secevent/ssf/event-type/verification",
      ],
      eventsDelivered: [
        "https://schemas.openid.net/secevent/risc/event-type/account-disabled",
        "https://schemas.openid.net/secevent/risc/event-type/account-enabled",
        "https://schemas.openid.net/secevent/risc/event-type/credential-compromise",
        "https://schemas.openid.net/secevent/ssf/event-type/verification",
      ],
      minVerificationInterval: 60,
      description: "SSF Receiver",
      inactivityTimeout: 86400,
      defaultSubjects: "NONE",
    },
  },
};
```

## Fields

| Field                                                                                                                                                  | Type                                                                                                                                                   | Required                                                                                                                                               | Description                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `result`                                                                                                                                               | [operations.GetSsfTransmitterTransmitterIdStreamStreamIdResult](../../models/operations/get-ssf-transmitter-transmitter-id-stream-stream-id-result.md) | :heavy_minus_sign:                                                                                                                                     | N/A                                                                                                                                                    |
| `stream`                                                                                                                                               | [operations.GetSsfTransmitterTransmitterIdStreamStreamIdStream](../../models/operations/get-ssf-transmitter-transmitter-id-stream-stream-id-stream.md) | :heavy_minus_sign:                                                                                                                                     | N/A                                                                                                                                                    |
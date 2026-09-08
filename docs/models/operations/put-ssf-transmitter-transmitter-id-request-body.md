# PutSsfTransmitterTransmitterIdRequestBody

## Example Usage

```typescript
import { PutSsfTransmitterTransmitterIdRequestBody } from "@authlete/arena/models/operations";

let value: PutSsfTransmitterTransmitterIdRequestBody = {
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
};
```

## Fields

| Field                                                                                                                                                                 | Type                                                                                                                                                                  | Required                                                                                                                                                              | Description                                                                                                                                                           |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `metadata`                                                                                                                                                            | [operations.PutSsfTransmitterTransmitterIdMetadataRequest](../../models/operations/put-ssf-transmitter-transmitter-id-metadata-request.md)                            | :heavy_check_mark:                                                                                                                                                    | Transmitter Configuration Metadata defined in [OpenID Shared Signals Framework Specification 1.0](https://openid.net/specs/openid-sharedsignals-framework-1_0.html).<br/> |
| `settings`                                                                                                                                                            | [operations.PutSsfTransmitterTransmitterIdSettingsRequest](../../models/operations/put-ssf-transmitter-transmitter-id-settings-request.md)                            | :heavy_minus_sign:                                                                                                                                                    | N/A                                                                                                                                                                   |
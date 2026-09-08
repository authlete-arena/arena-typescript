# GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiSubId17

The subject identifier with the `saml_assertion_id` format as defined in [Section 3.5.2. SAML Assertion ID Subject Identifier Format](https://openid.github.io/sharedsignals/openid-sharedsignals-framework-1_0.html#section-3.5.2) of [OpenID Shared Signals Framework Specification 1.0](https://openid.github.io/sharedsignals/openid-sharedsignals-framework-1_0.html).


## Example Usage

```typescript
import { GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiSubId17 } from "@authlete/arena/models/operations";

let value: GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiSubId17 = {
  format: "saml_assertion_id",
  issuer: "american_express",
  assertionId: "<id>",
};
```

## Fields

| Field                 | Type                  | Required              | Description           |
| --------------------- | --------------------- | --------------------- | --------------------- |
| `format`              | *"saml_assertion_id"* | :heavy_check_mark:    | N/A                   |
| `issuer`              | *any*                 | :heavy_check_mark:    | N/A                   |
| `assertionId`         | *any*                 | :heavy_check_mark:    | N/A                   |
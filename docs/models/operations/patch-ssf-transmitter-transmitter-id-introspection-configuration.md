# PatchSsfTransmitterTransmitterIdIntrospectionConfiguration

Configuration for access token introspection ([RFC 7662](https://www.rfc-editor.org/rfc/rfc7662.html)).


## Example Usage

```typescript
import { PatchSsfTransmitterTransmitterIdIntrospectionConfiguration } from "@authlete/arena/models/operations";

let value: PatchSsfTransmitterTransmitterIdIntrospectionConfiguration = {
  issuer: "american_express",
};
```

## Fields

| Field                                                                                                                       | Type                                                                                                                        | Required                                                                                                                    | Description                                                                                                                 |
| --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| `scheme`                                                                                                                    | [operations.PatchSsfTransmitterTransmitterIdScheme](../../models/operations/patch-ssf-transmitter-transmitter-id-scheme.md) | :heavy_minus_sign:                                                                                                          | The HTTP authentication scheme.                                                                                             |
| `userId`                                                                                                                    | *any*                                                                                                                       | :heavy_minus_sign:                                                                                                          | The user ID, required for the Basic Authentication.                                                                         |
| `password`                                                                                                                  | *any*                                                                                                                       | :heavy_minus_sign:                                                                                                          | The password, required for the Basic Authentication.                                                                        |
| `accessToken`                                                                                                               | *any*                                                                                                                       | :heavy_minus_sign:                                                                                                          | The access token, required for the Bearer or DPoP Authentication.                                                           |
| `issuer`                                                                                                                    | *any*                                                                                                                       | :heavy_check_mark:                                                                                                          | The identifier of the authorization server.                                                                                 |
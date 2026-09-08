# GetSsfTransmitterTransmitterIdIntrospectionConfiguration

Configuration for access token introspection ([RFC 7662](https://www.rfc-editor.org/rfc/rfc7662.html)).


## Example Usage

```typescript
import { GetSsfTransmitterTransmitterIdIntrospectionConfiguration } from "@authlete/arena/models/operations";

let value: GetSsfTransmitterTransmitterIdIntrospectionConfiguration = {
  issuer: "https://tiny-slime.com",
};
```

## Fields

| Field                                                                                                                   | Type                                                                                                                    | Required                                                                                                                | Description                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| `scheme`                                                                                                                | [operations.GetSsfTransmitterTransmitterIdScheme](../../models/operations/get-ssf-transmitter-transmitter-id-scheme.md) | :heavy_minus_sign:                                                                                                      | The HTTP authentication scheme.                                                                                         |
| `userId`                                                                                                                | *string*                                                                                                                | :heavy_minus_sign:                                                                                                      | The user ID, required for the Basic Authentication.                                                                     |
| `password`                                                                                                              | *string*                                                                                                                | :heavy_minus_sign:                                                                                                      | The password, required for the Basic Authentication.                                                                    |
| `accessToken`                                                                                                           | *string*                                                                                                                | :heavy_minus_sign:                                                                                                      | The access token, required for the Bearer or DPoP Authentication.                                                       |
| `issuer`                                                                                                                | *string*                                                                                                                | :heavy_check_mark:                                                                                                      | The identifier of the authorization server.                                                                             |
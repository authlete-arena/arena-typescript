# PostSsfTransmitterIntrospectionConfigurationRequest

Configuration for access token introspection ([RFC 7662](https://www.rfc-editor.org/rfc/rfc7662.html)).


## Example Usage

```typescript
import { PostSsfTransmitterIntrospectionConfigurationRequest } from "authlete-arena/models/operations";

let value: PostSsfTransmitterIntrospectionConfigurationRequest = {
  issuer: "discover",
};
```

## Fields

| Field                                                                                                        | Type                                                                                                         | Required                                                                                                     | Description                                                                                                  |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| `scheme`                                                                                                     | [operations.PostSsfTransmitterSchemeRequest](../../models/operations/post-ssf-transmitter-scheme-request.md) | :heavy_minus_sign:                                                                                           | The HTTP authentication scheme.                                                                              |
| `userId`                                                                                                     | *any*                                                                                                        | :heavy_minus_sign:                                                                                           | The user ID, required for the Basic Authentication.                                                          |
| `password`                                                                                                   | *any*                                                                                                        | :heavy_minus_sign:                                                                                           | The password, required for the Basic Authentication.                                                         |
| `accessToken`                                                                                                | *any*                                                                                                        | :heavy_minus_sign:                                                                                           | The access token, required for the Bearer or DPoP Authentication.                                            |
| `issuer`                                                                                                     | *any*                                                                                                        | :heavy_check_mark:                                                                                           | The identifier of the authorization server.                                                                  |
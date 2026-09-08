# PostSsfTransmitterCreator

The creator of the transmitter.

## Example Usage

```typescript
import { PostSsfTransmitterCreator } from "authlete-arena/models/operations";

let value: PostSsfTransmitterCreator = {};
```

## Fields

| Field                                                   | Type                                                    | Required                                                | Description                                             |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| `iss`                                                   | *any*                                                   | :heavy_minus_sign:                                      | The issuer of the access token.                         |
| `sub`                                                   | *any*                                                   | :heavy_minus_sign:                                      | The subject of the access token.                        |
| `clientId`                                              | *any*                                                   | :heavy_minus_sign:                                      | The client ID of the access token.                      |
| `jti`                                                   | *any*                                                   | :heavy_minus_sign:                                      | The identifier of the access token.                     |
| `hash`                                                  | *any*                                                   | :heavy_minus_sign:                                      | The base64url-encoded SHA-256 hash of the access token. |
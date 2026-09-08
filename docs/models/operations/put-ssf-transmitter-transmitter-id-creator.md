# PutSsfTransmitterTransmitterIdCreator

The creator of the transmitter.

## Example Usage

```typescript
import { PutSsfTransmitterTransmitterIdCreator } from "@authlete/arena/models/operations";

let value: PutSsfTransmitterTransmitterIdCreator = {};
```

## Fields

| Field                                                   | Type                                                    | Required                                                | Description                                             |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| `iss`                                                   | *string*                                                | :heavy_minus_sign:                                      | The issuer of the access token.                         |
| `sub`                                                   | *string*                                                | :heavy_minus_sign:                                      | The subject of the access token.                        |
| `clientId`                                              | *string*                                                | :heavy_minus_sign:                                      | The client ID of the access token.                      |
| `jti`                                                   | *string*                                                | :heavy_minus_sign:                                      | The identifier of the access token.                     |
| `hash`                                                  | *string*                                                | :heavy_minus_sign:                                      | The base64url-encoded SHA-256 hash of the access token. |
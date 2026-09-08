# PostSsfTransmitterTransmitterIDEventRegisterSubIDJwtId1

The subject identifier with the `jwt_id` format as defined in [Section 3.5.1. JWT ID Subject Identifier Format](https://openid.github.io/sharedsignals/openid-sharedsignals-framework-1_0.html#section-3.5.1) of [OpenID Shared Signals Framework Specification 1.0](https://openid.github.io/sharedsignals/openid-sharedsignals-framework-1_0.html).


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIDEventRegisterSubIDJwtId1 } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIDEventRegisterSubIDJwtId1 = {
  format: "jwt_id",
  iss: "<value>",
  jti: "<value>",
};
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `format`           | *"jwt_id"*         | :heavy_check_mark: | N/A                |
| `iss`              | *string*           | :heavy_check_mark: | N/A                |
| `jti`              | *string*           | :heavy_check_mark: | N/A                |
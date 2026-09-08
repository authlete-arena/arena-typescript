# PostSsfTransmitterTransmitterIdEventRegisterSubId5

The subject identifier with the `jwt_id` format as defined in [Section 3.5.1. JWT ID Subject Identifier Format](https://openid.github.io/sharedsignals/openid-sharedsignals-framework-1_0.html#section-3.5.1) of [OpenID Shared Signals Framework Specification 1.0](https://openid.github.io/sharedsignals/openid-sharedsignals-framework-1_0.html).


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdEventRegisterSubId5 } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdEventRegisterSubId5 = {
  format: "jwt_id",
  iss: "<value>",
  jti: "<value>",
};
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `format`           | *"jwt_id"*         | :heavy_check_mark: | N/A                |
| `iss`              | *any*              | :heavy_check_mark: | N/A                |
| `jti`              | *any*              | :heavy_check_mark: | N/A                |
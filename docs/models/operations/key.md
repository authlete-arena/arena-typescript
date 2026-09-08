# Key

JWK defined in [RFC 7517: JSON Web Key (JWK)](https://www.rfc-editor.org/rfc/rfc7517.html).


## Example Usage

```typescript
import { Key } from "authlete-arena/models/operations";

let value: Key = {
  kty: "EC",
  use: "sig",
  keyOps: "sign",
  alg: "ES256",
};
```

## Fields

| Field              | Type               | Required           | Description        | Example            |
| ------------------ | ------------------ | ------------------ | ------------------ | ------------------ |
| `kty`              | *any*              | :heavy_check_mark: | N/A                | EC                 |
| `use`              | *any*              | :heavy_minus_sign: | N/A                | sig                |
| `keyOps`           | *any*              | :heavy_minus_sign: | N/A                | sign               |
| `alg`              | *any*              | :heavy_minus_sign: | N/A                | ES256              |
| `kid`              | *any*              | :heavy_minus_sign: | N/A                |                    |
| `x5u`              | *any*              | :heavy_minus_sign: | N/A                |                    |
| `x5c`              | *any*[]            | :heavy_minus_sign: | N/A                |                    |
| `x5t`              | *any*              | :heavy_minus_sign: | N/A                |                    |
| `x5tNumberS256`    | *any*              | :heavy_minus_sign: | N/A                |                    |
# Key

JWK defined in [RFC 7517: JSON Web Key (JWK)](https://www.rfc-editor.org/rfc/rfc7517.html).


## Example Usage

```typescript
import { Key } from "@authlete/arena/models/operations";

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
| `kty`              | *string*           | :heavy_check_mark: | N/A                | EC                 |
| `use`              | *string*           | :heavy_minus_sign: | N/A                | sig                |
| `keyOps`           | *string*           | :heavy_minus_sign: | N/A                | sign               |
| `alg`              | *string*           | :heavy_minus_sign: | N/A                | ES256              |
| `kid`              | *string*           | :heavy_minus_sign: | N/A                |                    |
| `x5u`              | *string*           | :heavy_minus_sign: | N/A                |                    |
| `x5c`              | *string*[]         | :heavy_minus_sign: | N/A                |                    |
| `x5t`              | *string*           | :heavy_minus_sign: | N/A                |                    |
| `x5tNumberS256`    | *string*           | :heavy_minus_sign: | N/A                |                    |
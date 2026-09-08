# Patch

JSON Patch's operation object defined in [RFC 6902: JavaScript Object Notation (JSON) Patch](https://www.rfc-editor.org/rfc/rfc6902.html).


## Example Usage

```typescript
import { Patch } from "@authlete/arena/models/operations";

let value: Patch = {
  op: "replace",
  path: "/settings/name",
  value: "My Transmitter",
};
```

## Fields

| Field                                          | Type                                           | Required                                       | Description                                    |
| ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| `op`                                           | [operations.Op](../../models/operations/op.md) | :heavy_check_mark:                             | N/A                                            |
| `path`                                         | *any*                                          | :heavy_check_mark:                             | N/A                                            |
| `value`                                        | *any*                                          | :heavy_minus_sign:                             | N/A                                            |
| `from`                                         | *any*                                          | :heavy_minus_sign:                             | N/A                                            |
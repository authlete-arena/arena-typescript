# PatchSsfTransmitterTransmitterIdRequestBody

## Example Usage

```typescript
import { PatchSsfTransmitterTransmitterIdRequestBody } from "authlete-arena/models/operations";

let value: PatchSsfTransmitterTransmitterIdRequestBody = {
  patch: [
    {
      op: "replace",
      path: "/settings/name",
      value: "My Transmitter",
    },
  ],
};
```

## Fields

| Field                                                                                                                    | Type                                                                                                                     | Required                                                                                                                 | Description                                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| `patch`                                                                                                                  | [operations.Patch](../../models/operations/patch.md)[]                                                                   | :heavy_check_mark:                                                                                                       | JSON Patch defined in [RFC 6902: JavaScript Object Notation (JSON) Patch](https://www.rfc-editor.org/rfc/rfc6902.html).<br/> |
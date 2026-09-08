# GetProbeReadinessResponse

## Example Usage

```typescript
import { GetProbeReadinessResponse } from "@authlete/arena/models/operations";

let value: GetProbeReadinessResponse = {
  headers: {
    "key": [
      "<value 1>",
      "<value 2>",
    ],
    "key1": [
      "<value 1>",
      "<value 2>",
      "<value 3>",
    ],
  },
  result: {},
};
```

## Fields

| Field                                                                                                    | Type                                                                                                     | Required                                                                                                 | Description                                                                                              |
| -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `headers`                                                                                                | Record<string, *string*[]>                                                                               | :heavy_check_mark:                                                                                       | N/A                                                                                                      |
| `result`                                                                                                 | [operations.GetProbeReadinessResponseBody](../../models/operations/get-probe-readiness-response-body.md) | :heavy_check_mark:                                                                                       | N/A                                                                                                      |
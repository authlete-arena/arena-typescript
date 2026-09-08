# GetJwksResponse

## Example Usage

```typescript
import { GetJwksResponse } from "authlete-arena/models/operations";

let value: GetJwksResponse = {
  headers: {
    "key": [
      "<value 1>",
      "<value 2>",
      "<value 3>",
    ],
    "key1": [
      "<value 1>",
      "<value 2>",
    ],
  },
  result: {
    keys: [],
  },
};
```

## Fields

| Field                                                                               | Type                                                                                | Required                                                                            | Description                                                                         |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `headers`                                                                           | Record<string, *string*[]>                                                          | :heavy_check_mark:                                                                  | N/A                                                                                 |
| `result`                                                                            | [operations.GetJwksResponseBody](../../models/operations/get-jwks-response-body.md) | :heavy_check_mark:                                                                  | N/A                                                                                 |
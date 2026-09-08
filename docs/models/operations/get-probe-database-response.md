# GetProbeDatabaseResponse

## Example Usage

```typescript
import { GetProbeDatabaseResponse } from "authlete-arena/models/operations";

let value: GetProbeDatabaseResponse = {
  headers: {
    "key": [],
    "key1": [
      "<value 1>",
      "<value 2>",
      "<value 3>",
    ],
    "key2": [
      "<value 1>",
      "<value 2>",
      "<value 3>",
    ],
  },
  result: {},
};
```

## Fields

| Field                                                                                                  | Type                                                                                                   | Required                                                                                               | Description                                                                                            |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `headers`                                                                                              | Record<string, *string*[]>                                                                             | :heavy_check_mark:                                                                                     | N/A                                                                                                    |
| `result`                                                                                               | [operations.GetProbeDatabaseResponseBody](../../models/operations/get-probe-database-response-body.md) | :heavy_check_mark:                                                                                     | N/A                                                                                                    |
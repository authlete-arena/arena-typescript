# GetWellKnownOauthProtectedResourceResponse

## Example Usage

```typescript
import { GetWellKnownOauthProtectedResourceResponse } from "@authlete/arena/models/operations";

let value: GetWellKnownOauthProtectedResourceResponse = {
  headers: {
    "key": [
      "<value 1>",
      "<value 2>",
    ],
    "key1": [],
  },
  result: {
    resource: "<value>",
  },
};
```

## Fields

| Field                                                                                                                                         | Type                                                                                                                                          | Required                                                                                                                                      | Description                                                                                                                                   |
| --------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| `headers`                                                                                                                                     | Record<string, *string*[]>                                                                                                                    | :heavy_check_mark:                                                                                                                            | N/A                                                                                                                                           |
| `result`                                                                                                                                      | [operations.GetWellKnownOauthProtectedResourceResponseBody](../../models/operations/get-well-known-oauth-protected-resource-response-body.md) | :heavy_check_mark:                                                                                                                            | N/A                                                                                                                                           |
# DelegateWellKnownPostSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResourceResponse

The HTTP response that the internet-facing endpoint should return to the endpoint accessor.


## Example Usage

```typescript
import {
  DelegateWellKnownPostSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResourceResponse,
} from "@authlete/arena/models/operations";

let value:
  DelegateWellKnownPostSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResourceResponse =
    {
      status: "<value>",
    };
```

## Fields

| Field                                                                                                                                                                   | Type                                                                                                                                                                    | Required                                                                                                                                                                | Description                                                                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `status`                                                                                                                                                                | *any*                                                                                                                                                                   | :heavy_check_mark:                                                                                                                                                      | The HTTP status code of the HTTP response.<br/>                                                                                                                         |
| `headers`                                                                                                                                                               | *any*[][]                                                                                                                                                               | :heavy_minus_sign:                                                                                                                                                      | HTTP headers that should be included in the HTTP response.<br/>Each element of this `headers` array is an array containing two strings: an HTTP header name and its value.<br/> |
| `contentType`                                                                                                                                                           | *any*                                                                                                                                                                   | :heavy_minus_sign:                                                                                                                                                      | The content type of the HTTP response. This parameter is set when the forwarded response contains a message body.<br/>                                                  |
| `body`                                                                                                                                                                  | *any*                                                                                                                                                                   | :heavy_minus_sign:                                                                                                                                                      | The message body of the HTTP response.<br/>                                                                                                                             |
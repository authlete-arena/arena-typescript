# DelegateWellKnownPostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationResponse

The HTTP response that the internet-facing endpoint should return to the endpoint accessor.


## Example Usage

```typescript
import {
  DelegateWellKnownPostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationResponse,
} from "@authlete/arena/models/operations";

let value:
  DelegateWellKnownPostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationResponse =
    {
      status: 582587,
    };
```

## Fields

| Field                                                                                                                                                                   | Type                                                                                                                                                                    | Required                                                                                                                                                                | Description                                                                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `status`                                                                                                                                                                | *number*                                                                                                                                                                | :heavy_check_mark:                                                                                                                                                      | The HTTP status code of the HTTP response.<br/>                                                                                                                         |
| `headers`                                                                                                                                                               | *string*[][]                                                                                                                                                            | :heavy_minus_sign:                                                                                                                                                      | HTTP headers that should be included in the HTTP response.<br/>Each element of this `headers` array is an array containing two strings: an HTTP header name and its value.<br/> |
| `contentType`                                                                                                                                                           | *string*                                                                                                                                                                | :heavy_minus_sign:                                                                                                                                                      | The content type of the HTTP response. This parameter is set when the forwarded response contains a message body.<br/>                                                  |
| `body`                                                                                                                                                                  | *string*                                                                                                                                                                | :heavy_minus_sign:                                                                                                                                                      | The message body of the HTTP response.<br/>                                                                                                                             |
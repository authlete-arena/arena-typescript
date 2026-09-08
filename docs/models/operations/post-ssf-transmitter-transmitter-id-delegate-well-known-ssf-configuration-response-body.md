# PostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationResponseBody

The message body of responses from delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationResponseBody } from "@authlete/arena/models/operations";

let value:
  PostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationResponseBody =
    {
      response: {
        status: "<value>",
      },
    };
```

## Fields

| Field                                                                                                                                                                                                                                     | Type                                                                                                                                                                                                                                      | Required                                                                                                                                                                                                                                  | Description                                                                                                                                                                                                                               |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `result`                                                                                                                                                                                                                                  | [operations.PostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationResult](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-well-known-ssf-configuration-result.md)                                          | :heavy_minus_sign:                                                                                                                                                                                                                        | N/A                                                                                                                                                                                                                                       |
| `response`                                                                                                                                                                                                                                | [operations.DelegateWellKnownPostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationResponse](../../models/operations/delegate-well-known-post-ssf-transmitter-transmitter-id-delegate-well-known-ssf-configuration-response.md) | :heavy_check_mark:                                                                                                                                                                                                                        | The HTTP response that the internet-facing endpoint should return to the endpoint accessor.<br/>                                                                                                                                          |
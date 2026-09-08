# PostSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResourceResponseBody

The message body of responses from delegate APIs.


## Example Usage

```typescript
import {
  PostSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResourceResponseBody,
} from "@authlete/arena/models/operations";

let value:
  PostSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResourceResponseBody =
    {
      response: {
        status: "<value>",
      },
    };
```

## Fields

| Field                                                                                                                                                                                                                                                  | Type                                                                                                                                                                                                                                                   | Required                                                                                                                                                                                                                                               | Description                                                                                                                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `result`                                                                                                                                                                                                                                               | [operations.PostSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResourceResult](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-well-known-oauth-protected-resource-result.md)                                          | :heavy_minus_sign:                                                                                                                                                                                                                                     | N/A                                                                                                                                                                                                                                                    |
| `response`                                                                                                                                                                                                                                             | [operations.DelegateWellKnownPostSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResourceResponse](../../models/operations/delegate-well-known-post-ssf-transmitter-transmitter-id-delegate-well-known-oauth-protected-resource-response.md) | :heavy_check_mark:                                                                                                                                                                                                                                     | The HTTP response that the internet-facing endpoint should return to the endpoint accessor.<br/>                                                                                                                                                       |
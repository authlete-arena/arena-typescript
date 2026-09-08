# PostSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResourceRequestBody

The message body of requests to delegate APIs.


## Example Usage

```typescript
import {
  PostSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResourceRequestBody,
} from "@authlete/arena/models/operations";

let value:
  PostSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResourceRequestBody =
    {
      options: {
        pretty: true,
      },
      request: {
        method: "<value>",
        uri: "https://witty-institute.org/",
      },
    };
```

## Fields

| Field                                                                                                                                                                                                                                                | Type                                                                                                                                                                                                                                                 | Required                                                                                                                                                                                                                                             | Description                                                                                                                                                                                                                                          |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `options`                                                                                                                                                                                                                                            | [operations.PostSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResourceOptions](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-well-known-oauth-protected-resource-options.md)                                      | :heavy_minus_sign:                                                                                                                                                                                                                                   | N/A                                                                                                                                                                                                                                                  |
| `request`                                                                                                                                                                                                                                            | [operations.DelegateWellKnownPostSsfTransmitterTransmitterIdDelegateWellKnownOauthProtectedResourceRequest](../../models/operations/delegate-well-known-post-ssf-transmitter-transmitter-id-delegate-well-known-oauth-protected-resource-request.md) | :heavy_check_mark:                                                                                                                                                                                                                                   | The original HTTP request that the internet-facing endpoint has received.<br/>                                                                                                                                                                       |
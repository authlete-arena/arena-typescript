# PostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationRequestBody

The message body of requests to delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationRequestBody } from "authlete-arena/models/operations";

let value:
  PostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationRequestBody =
    {
      options: {
        pretty: true,
      },
      request: {
        method: "<value>",
        uri: "https://late-stump.net/",
      },
    };
```

## Fields

| Field                                                                                                                                                                                                                      | Type                                                                                                                                                                                                                       | Required                                                                                                                                                                                                                   | Description                                                                                                                                                                                                                |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `options`                                                                                                                                                                                                                  | [operations.PostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationOptions](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-well-known-ssf-configuration-options.md)                         | :heavy_minus_sign:                                                                                                                                                                                                         | N/A                                                                                                                                                                                                                        |
| `request`                                                                                                                                                                                                                  | [operations.PostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationRequestRequestBody](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-well-known-ssf-configuration-request-request-body.md) | :heavy_check_mark:                                                                                                                                                                                                         | The original HTTP request that the internet-facing endpoint has received.<br/>                                                                                                                                             |
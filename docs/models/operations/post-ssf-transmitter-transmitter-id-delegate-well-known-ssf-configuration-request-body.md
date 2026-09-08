# PostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationRequestBody

The message body of requests to delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationRequestBody } from "@authlete/arena/models/operations";

let value:
  PostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationRequestBody =
    {
      options: {
        pretty: true,
      },
      request: {
        method: "<value>",
        uri: "https://late-stump.net/",
        ipAddress: "192.168.0.1",
      },
    };
```

## Fields

| Field                                                                                                                                                                                                                                   | Type                                                                                                                                                                                                                                    | Required                                                                                                                                                                                                                                | Description                                                                                                                                                                                                                             |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `options`                                                                                                                                                                                                                               | [operations.PostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationOptions](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-well-known-ssf-configuration-options.md)                                      | :heavy_minus_sign:                                                                                                                                                                                                                      | N/A                                                                                                                                                                                                                                     |
| `request`                                                                                                                                                                                                                               | [operations.DelegateWellKnownPostSsfTransmitterTransmitterIdDelegateWellKnownSsfConfigurationRequest](../../models/operations/delegate-well-known-post-ssf-transmitter-transmitter-id-delegate-well-known-ssf-configuration-request.md) | :heavy_check_mark:                                                                                                                                                                                                                      | The original HTTP request that the internet-facing endpoint has received.<br/>                                                                                                                                                          |
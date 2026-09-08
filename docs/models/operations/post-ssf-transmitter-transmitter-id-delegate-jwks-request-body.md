# PostSsfTransmitterTransmitterIdDelegateJwksRequestBody

The message body of requests to delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateJwksRequestBody } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdDelegateJwksRequestBody = {
  options: {
    pretty: true,
  },
  request: {
    method: "<value>",
    uri: "https://unwieldy-guidance.com",
    ipAddress: "192.168.0.1",
  },
};
```

## Fields

| Field                                                                                                                                                                  | Type                                                                                                                                                                   | Required                                                                                                                                                               | Description                                                                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `options`                                                                                                                                                              | [operations.PostSsfTransmitterTransmitterIdDelegateJwksOptions](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-jwks-options.md)                  | :heavy_minus_sign:                                                                                                                                                     | N/A                                                                                                                                                                    |
| `request`                                                                                                                                                              | [operations.DelegatePostSsfTransmitterTransmitterIdDelegateJwksRequest](../../models/operations/delegate-post-ssf-transmitter-transmitter-id-delegate-jwks-request.md) | :heavy_check_mark:                                                                                                                                                     | The original HTTP request that the internet-facing endpoint has received.<br/>                                                                                         |
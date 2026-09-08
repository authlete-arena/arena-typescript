# PostSsfTransmitterTransmitterIdDelegateStreamStatusReadRequestBody

The message body of requests to delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamStatusReadRequestBody } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdDelegateStreamStatusReadRequestBody =
  {
    options: {
      pretty: true,
    },
    request: {
      method: "<value>",
      uri: "https://rewarding-advertisement.net",
      ipAddress: "192.168.0.1",
    },
  };
```

## Fields

| Field                                                                                                                                                                                                         | Type                                                                                                                                                                                                          | Required                                                                                                                                                                                                      | Description                                                                                                                                                                                                   |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `options`                                                                                                                                                                                                     | [operations.PostSsfTransmitterTransmitterIdDelegateStreamStatusReadOptions](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-status-read-options.md)                               | :heavy_minus_sign:                                                                                                                                                                                            | N/A                                                                                                                                                                                                           |
| `request`                                                                                                                                                                                                     | [operations.DelegateStatusPostSsfTransmitterTransmitterIdDelegateStreamStatusReadRequest](../../models/operations/delegate-status-post-ssf-transmitter-transmitter-id-delegate-stream-status-read-request.md) | :heavy_check_mark:                                                                                                                                                                                            | The original HTTP request that the internet-facing endpoint has received.<br/>                                                                                                                                |
# PostSsfTransmitterTransmitterIdDelegateStreamStatusUpdateRequestBody

The message body of requests to delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamStatusUpdateRequestBody } from "@authlete/arena/models/operations";

let value:
  PostSsfTransmitterTransmitterIdDelegateStreamStatusUpdateRequestBody = {
    options: {
      pretty: true,
    },
    request: {
      method: "<value>",
      uri: "https://purple-drug.org/",
    },
  };
```

## Fields

| Field                                                                                                                                                                                                             | Type                                                                                                                                                                                                              | Required                                                                                                                                                                                                          | Description                                                                                                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `options`                                                                                                                                                                                                         | [operations.PostSsfTransmitterTransmitterIdDelegateStreamStatusUpdateOptions](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-status-update-options.md)                               | :heavy_minus_sign:                                                                                                                                                                                                | N/A                                                                                                                                                                                                               |
| `request`                                                                                                                                                                                                         | [operations.DelegateStatusPostSsfTransmitterTransmitterIdDelegateStreamStatusUpdateRequest](../../models/operations/delegate-status-post-ssf-transmitter-transmitter-id-delegate-stream-status-update-request.md) | :heavy_check_mark:                                                                                                                                                                                                | The original HTTP request that the internet-facing endpoint has received.<br/>                                                                                                                                    |
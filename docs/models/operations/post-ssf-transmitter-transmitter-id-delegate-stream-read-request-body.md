# PostSsfTransmitterTransmitterIdDelegateStreamReadRequestBody

The message body of requests to delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamReadRequestBody } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdDelegateStreamReadRequestBody = {
  options: {
    pretty: true,
  },
  request: {
    method: "<value>",
    uri: "https://alert-gerbil.com/",
  },
};
```

## Fields

| Field                                                                                                                                                                                              | Type                                                                                                                                                                                               | Required                                                                                                                                                                                           | Description                                                                                                                                                                                        |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `options`                                                                                                                                                                                          | [operations.PostSsfTransmitterTransmitterIdDelegateStreamReadOptions](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-read-options.md)                                 | :heavy_minus_sign:                                                                                                                                                                                 | N/A                                                                                                                                                                                                |
| `request`                                                                                                                                                                                          | [operations.DelegateStreamsPostSsfTransmitterTransmitterIdDelegateStreamReadRequest](../../models/operations/delegate-streams-post-ssf-transmitter-transmitter-id-delegate-stream-read-request.md) | :heavy_check_mark:                                                                                                                                                                                 | The original HTTP request that the internet-facing endpoint has received.<br/>                                                                                                                     |
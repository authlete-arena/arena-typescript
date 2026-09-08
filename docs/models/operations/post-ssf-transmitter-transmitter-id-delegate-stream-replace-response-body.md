# PostSsfTransmitterTransmitterIdDelegateStreamReplaceResponseBody

The message body of responses from delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamReplaceResponseBody } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdDelegateStreamReplaceResponseBody = {
  response: {
    status: "<value>",
  },
};
```

## Fields

| Field                                                                                                                                                                                                      | Type                                                                                                                                                                                                       | Required                                                                                                                                                                                                   | Description                                                                                                                                                                                                |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `result`                                                                                                                                                                                                   | [operations.PostSsfTransmitterTransmitterIdDelegateStreamReplaceResult](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-replace-result.md)                                     | :heavy_minus_sign:                                                                                                                                                                                         | N/A                                                                                                                                                                                                        |
| `response`                                                                                                                                                                                                 | [operations.DelegateStreamsPostSsfTransmitterTransmitterIdDelegateStreamReplaceResponse](../../models/operations/delegate-streams-post-ssf-transmitter-transmitter-id-delegate-stream-replace-response.md) | :heavy_check_mark:                                                                                                                                                                                         | The HTTP response that the internet-facing endpoint should return to the endpoint accessor.<br/>                                                                                                           |
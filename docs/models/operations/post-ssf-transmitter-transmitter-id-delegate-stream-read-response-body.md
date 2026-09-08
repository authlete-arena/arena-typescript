# PostSsfTransmitterTransmitterIdDelegateStreamReadResponseBody

The message body of responses from delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamReadResponseBody } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdDelegateStreamReadResponseBody = {
  response: {
    status: "<value>",
  },
};
```

## Fields

| Field                                                                                                                                                                                                | Type                                                                                                                                                                                                 | Required                                                                                                                                                                                             | Description                                                                                                                                                                                          |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `result`                                                                                                                                                                                             | [operations.PostSsfTransmitterTransmitterIdDelegateStreamReadResult](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-read-result.md)                                     | :heavy_minus_sign:                                                                                                                                                                                   | N/A                                                                                                                                                                                                  |
| `response`                                                                                                                                                                                           | [operations.DelegateStreamsPostSsfTransmitterTransmitterIdDelegateStreamReadResponse](../../models/operations/delegate-streams-post-ssf-transmitter-transmitter-id-delegate-stream-read-response.md) | :heavy_check_mark:                                                                                                                                                                                   | The HTTP response that the internet-facing endpoint should return to the endpoint accessor.<br/>                                                                                                     |
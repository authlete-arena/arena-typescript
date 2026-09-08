# PostSsfTransmitterTransmitterIdDelegateStreamStatusReadResponseBody

The message body of responses from delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamStatusReadResponseBody } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdDelegateStreamStatusReadResponseBody =
  {
    response: {
      status: "<value>",
    },
  };
```

## Fields

| Field                                                                                                                                                                                                           | Type                                                                                                                                                                                                            | Required                                                                                                                                                                                                        | Description                                                                                                                                                                                                     |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `result`                                                                                                                                                                                                        | [operations.PostSsfTransmitterTransmitterIdDelegateStreamStatusReadResult](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-status-read-result.md)                                   | :heavy_minus_sign:                                                                                                                                                                                              | N/A                                                                                                                                                                                                             |
| `response`                                                                                                                                                                                                      | [operations.DelegateStatusPostSsfTransmitterTransmitterIdDelegateStreamStatusReadResponse](../../models/operations/delegate-status-post-ssf-transmitter-transmitter-id-delegate-stream-status-read-response.md) | :heavy_check_mark:                                                                                                                                                                                              | The HTTP response that the internet-facing endpoint should return to the endpoint accessor.<br/>                                                                                                                |
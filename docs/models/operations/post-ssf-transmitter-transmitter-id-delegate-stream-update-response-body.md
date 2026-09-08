# PostSsfTransmitterTransmitterIdDelegateStreamUpdateResponseBody

The message body of responses from delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamUpdateResponseBody } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdDelegateStreamUpdateResponseBody = {
  response: {
    status: "<value>",
  },
};
```

## Fields

| Field                                                                                                                                                                                                    | Type                                                                                                                                                                                                     | Required                                                                                                                                                                                                 | Description                                                                                                                                                                                              |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `result`                                                                                                                                                                                                 | [operations.PostSsfTransmitterTransmitterIdDelegateStreamUpdateResult](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-update-result.md)                                     | :heavy_minus_sign:                                                                                                                                                                                       | N/A                                                                                                                                                                                                      |
| `response`                                                                                                                                                                                               | [operations.DelegateStreamsPostSsfTransmitterTransmitterIdDelegateStreamUpdateResponse](../../models/operations/delegate-streams-post-ssf-transmitter-transmitter-id-delegate-stream-update-response.md) | :heavy_check_mark:                                                                                                                                                                                       | The HTTP response that the internet-facing endpoint should return to the endpoint accessor.<br/>                                                                                                         |
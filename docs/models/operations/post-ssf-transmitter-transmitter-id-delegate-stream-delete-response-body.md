# PostSsfTransmitterTransmitterIdDelegateStreamDeleteResponseBody

The message body of responses from delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamDeleteResponseBody } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdDelegateStreamDeleteResponseBody = {
  response: {
    status: 882711,
  },
};
```

## Fields

| Field                                                                                                                                                                                                    | Type                                                                                                                                                                                                     | Required                                                                                                                                                                                                 | Description                                                                                                                                                                                              |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `result`                                                                                                                                                                                                 | [operations.PostSsfTransmitterTransmitterIdDelegateStreamDeleteResult](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-delete-result.md)                                     | :heavy_minus_sign:                                                                                                                                                                                       | N/A                                                                                                                                                                                                      |
| `response`                                                                                                                                                                                               | [operations.DelegateStreamsPostSsfTransmitterTransmitterIdDelegateStreamDeleteResponse](../../models/operations/delegate-streams-post-ssf-transmitter-transmitter-id-delegate-stream-delete-response.md) | :heavy_check_mark:                                                                                                                                                                                       | The HTTP response that the internet-facing endpoint should return to the endpoint accessor.<br/>                                                                                                         |
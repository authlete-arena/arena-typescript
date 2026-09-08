# PostSsfTransmitterTransmitterIdDelegateStreamCreateResponseBody

The message body of responses from delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamCreateResponseBody } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdDelegateStreamCreateResponseBody = {
  response: {
    status: 508107,
  },
};
```

## Fields

| Field                                                                                                                                                                                                    | Type                                                                                                                                                                                                     | Required                                                                                                                                                                                                 | Description                                                                                                                                                                                              |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `result`                                                                                                                                                                                                 | [operations.PostSsfTransmitterTransmitterIdDelegateStreamCreateResult](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-create-result.md)                                     | :heavy_minus_sign:                                                                                                                                                                                       | N/A                                                                                                                                                                                                      |
| `response`                                                                                                                                                                                               | [operations.DelegateStreamsPostSsfTransmitterTransmitterIdDelegateStreamCreateResponse](../../models/operations/delegate-streams-post-ssf-transmitter-transmitter-id-delegate-stream-create-response.md) | :heavy_check_mark:                                                                                                                                                                                       | The HTTP response that the internet-facing endpoint should return to the endpoint accessor.<br/>                                                                                                         |
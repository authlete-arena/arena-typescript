# PostSsfTransmitterTransmitterIdDelegateStreamPollStreamIdResponseBody

The message body of responses from delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamPollStreamIdResponseBody } from "authlete-arena/models/operations";

let value:
  PostSsfTransmitterTransmitterIdDelegateStreamPollStreamIdResponseBody = {
    response: {
      status: "<value>",
    },
  };
```

## Fields

| Field                                                                                                                                                                                                            | Type                                                                                                                                                                                                             | Required                                                                                                                                                                                                         | Description                                                                                                                                                                                                      |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `result`                                                                                                                                                                                                         | [operations.PostSsfTransmitterTransmitterIdDelegateStreamPollStreamIdResult](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-poll-stream-id-result.md)                               | :heavy_minus_sign:                                                                                                                                                                                               | N/A                                                                                                                                                                                                              |
| `response`                                                                                                                                                                                                       | [operations.PostSsfTransmitterTransmitterIdDelegateStreamPollStreamIdResponseResponseBody](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-poll-stream-id-response-response-body.md) | :heavy_check_mark:                                                                                                                                                                                               | The HTTP response that the internet-facing endpoint should return to the endpoint accessor.<br/>                                                                                                                 |
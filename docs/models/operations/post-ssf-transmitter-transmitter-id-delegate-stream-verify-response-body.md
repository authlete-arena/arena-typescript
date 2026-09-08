# PostSsfTransmitterTransmitterIdDelegateStreamVerifyResponseBody

The message body of responses from delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamVerifyResponseBody } from "authlete-arena/models/operations";

let value: PostSsfTransmitterTransmitterIdDelegateStreamVerifyResponseBody = {
  response: {
    status: "<value>",
  },
};
```

## Fields

| Field                                                                                                                                                                                              | Type                                                                                                                                                                                               | Required                                                                                                                                                                                           | Description                                                                                                                                                                                        |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `result`                                                                                                                                                                                           | [operations.PostSsfTransmitterTransmitterIdDelegateStreamVerifyResult](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-verify-result.md)                               | :heavy_minus_sign:                                                                                                                                                                                 | N/A                                                                                                                                                                                                |
| `response`                                                                                                                                                                                         | [operations.PostSsfTransmitterTransmitterIdDelegateStreamVerifyResponseResponseBody](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-verify-response-response-body.md) | :heavy_check_mark:                                                                                                                                                                                 | The HTTP response that the internet-facing endpoint should return to the endpoint accessor.<br/>                                                                                                   |
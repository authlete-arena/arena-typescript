# PostSsfTransmitterTransmitterIdDelegateJwksResponseBody

The message body of responses from delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateJwksResponseBody } from "authlete-arena/models/operations";

let value: PostSsfTransmitterTransmitterIdDelegateJwksResponseBody = {
  response: {
    status: "<value>",
  },
};
```

## Fields

| Field                                                                                                                                                                             | Type                                                                                                                                                                              | Required                                                                                                                                                                          | Description                                                                                                                                                                       |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `result`                                                                                                                                                                          | [operations.PostSsfTransmitterTransmitterIdDelegateJwksResult](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-jwks-result.md)                               | :heavy_minus_sign:                                                                                                                                                                | N/A                                                                                                                                                                               |
| `response`                                                                                                                                                                        | [operations.PostSsfTransmitterTransmitterIdDelegateJwksResponseResponseBody](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-jwks-response-response-body.md) | :heavy_check_mark:                                                                                                                                                                | The HTTP response that the internet-facing endpoint should return to the endpoint accessor.<br/>                                                                                  |
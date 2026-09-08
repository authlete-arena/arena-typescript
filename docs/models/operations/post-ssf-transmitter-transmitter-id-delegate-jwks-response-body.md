# PostSsfTransmitterTransmitterIdDelegateJwksResponseBody

The message body of responses from delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateJwksResponseBody } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdDelegateJwksResponseBody = {
  response: {
    status: 730774,
  },
};
```

## Fields

| Field                                                                                                                                                                    | Type                                                                                                                                                                     | Required                                                                                                                                                                 | Description                                                                                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `result`                                                                                                                                                                 | [operations.PostSsfTransmitterTransmitterIdDelegateJwksResult](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-jwks-result.md)                      | :heavy_minus_sign:                                                                                                                                                       | N/A                                                                                                                                                                      |
| `response`                                                                                                                                                               | [operations.DelegatePostSsfTransmitterTransmitterIdDelegateJwksResponse](../../models/operations/delegate-post-ssf-transmitter-transmitter-id-delegate-jwks-response.md) | :heavy_check_mark:                                                                                                                                                       | The HTTP response that the internet-facing endpoint should return to the endpoint accessor.<br/>                                                                         |
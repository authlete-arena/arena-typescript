# PostSsfTransmitterTransmitterIdDelegateStreamVerifyRequestBody

The message body of requests to delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamVerifyRequestBody } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdDelegateStreamVerifyRequestBody = {
  options: {
    pretty: true,
  },
  request: {
    method: "<value>",
    uri: "https://intent-responsibility.com",
  },
};
```

## Fields

| Field                                                                                                                                                                                                  | Type                                                                                                                                                                                                   | Required                                                                                                                                                                                               | Description                                                                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                                              | [operations.PostSsfTransmitterTransmitterIdDelegateStreamVerifyOptions](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-verify-options.md)                                 | :heavy_minus_sign:                                                                                                                                                                                     | N/A                                                                                                                                                                                                    |
| `request`                                                                                                                                                                                              | [operations.DelegateStreamsPostSsfTransmitterTransmitterIdDelegateStreamVerifyRequest](../../models/operations/delegate-streams-post-ssf-transmitter-transmitter-id-delegate-stream-verify-request.md) | :heavy_check_mark:                                                                                                                                                                                     | The original HTTP request that the internet-facing endpoint has received.<br/>                                                                                                                         |
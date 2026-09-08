# PostSsfTransmitterTransmitterIdDelegateStreamCreateRequestBody

The message body of requests to delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamCreateRequestBody } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdDelegateStreamCreateRequestBody = {
  options: {
    pretty: true,
  },
  request: {
    method: "<value>",
    uri: "https://these-bin.org/",
    ipAddress: "192.168.0.1",
  },
};
```

## Fields

| Field                                                                                                                                                                                                  | Type                                                                                                                                                                                                   | Required                                                                                                                                                                                               | Description                                                                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                                              | [operations.PostSsfTransmitterTransmitterIdDelegateStreamCreateOptions](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-create-options.md)                                 | :heavy_minus_sign:                                                                                                                                                                                     | N/A                                                                                                                                                                                                    |
| `request`                                                                                                                                                                                              | [operations.DelegateStreamsPostSsfTransmitterTransmitterIdDelegateStreamCreateRequest](../../models/operations/delegate-streams-post-ssf-transmitter-transmitter-id-delegate-stream-create-request.md) | :heavy_check_mark:                                                                                                                                                                                     | The original HTTP request that the internet-facing endpoint has received.<br/>                                                                                                                         |
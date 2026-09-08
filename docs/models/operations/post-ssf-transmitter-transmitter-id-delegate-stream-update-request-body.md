# PostSsfTransmitterTransmitterIdDelegateStreamUpdateRequestBody

The message body of requests to delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamUpdateRequestBody } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdDelegateStreamUpdateRequestBody = {
  options: {
    pretty: true,
  },
  request: {
    method: "<value>",
    uri: "https://muffled-emergent.org/",
    ipAddress: "192.168.0.1",
  },
};
```

## Fields

| Field                                                                                                                                                                                                  | Type                                                                                                                                                                                                   | Required                                                                                                                                                                                               | Description                                                                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                                              | [operations.PostSsfTransmitterTransmitterIdDelegateStreamUpdateOptions](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-update-options.md)                                 | :heavy_minus_sign:                                                                                                                                                                                     | N/A                                                                                                                                                                                                    |
| `request`                                                                                                                                                                                              | [operations.DelegateStreamsPostSsfTransmitterTransmitterIdDelegateStreamUpdateRequest](../../models/operations/delegate-streams-post-ssf-transmitter-transmitter-id-delegate-stream-update-request.md) | :heavy_check_mark:                                                                                                                                                                                     | The original HTTP request that the internet-facing endpoint has received.<br/>                                                                                                                         |
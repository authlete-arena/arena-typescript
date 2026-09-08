# PostSsfTransmitterTransmitterIdDelegateStreamDeleteRequestBody

The message body of requests to delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamDeleteRequestBody } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdDelegateStreamDeleteRequestBody = {
  options: {
    pretty: true,
  },
  request: {
    method: "<value>",
    uri: "https://sentimental-object.info",
    ipAddress: "192.168.0.1",
  },
};
```

## Fields

| Field                                                                                                                                                                                                  | Type                                                                                                                                                                                                   | Required                                                                                                                                                                                               | Description                                                                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                                              | [operations.PostSsfTransmitterTransmitterIdDelegateStreamDeleteOptions](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-delete-options.md)                                 | :heavy_minus_sign:                                                                                                                                                                                     | N/A                                                                                                                                                                                                    |
| `request`                                                                                                                                                                                              | [operations.DelegateStreamsPostSsfTransmitterTransmitterIdDelegateStreamDeleteRequest](../../models/operations/delegate-streams-post-ssf-transmitter-transmitter-id-delegate-stream-delete-request.md) | :heavy_check_mark:                                                                                                                                                                                     | The original HTTP request that the internet-facing endpoint has received.<br/>                                                                                                                         |
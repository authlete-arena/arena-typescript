# PostSsfTransmitterTransmitterIdDelegateStreamPollStreamIdRequestBody

The message body of requests to delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamPollStreamIdRequestBody } from "@authlete/arena/models/operations";

let value:
  PostSsfTransmitterTransmitterIdDelegateStreamPollStreamIdRequestBody = {
    options: {
      pretty: true,
    },
    request: {
      method: "<value>",
      uri: "https://phony-deck.biz",
      ipAddress: "192.168.0.1",
    },
  };
```

## Fields

| Field                                                                                                                                                                                                                | Type                                                                                                                                                                                                                 | Required                                                                                                                                                                                                             | Description                                                                                                                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `options`                                                                                                                                                                                                            | [operations.PostSsfTransmitterTransmitterIdDelegateStreamPollStreamIdOptions](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-poll-stream-id-options.md)                                 | :heavy_minus_sign:                                                                                                                                                                                                   | N/A                                                                                                                                                                                                                  |
| `request`                                                                                                                                                                                                            | [operations.DelegateStreamsPostSsfTransmitterTransmitterIdDelegateStreamPollStreamIdRequest](../../models/operations/delegate-streams-post-ssf-transmitter-transmitter-id-delegate-stream-poll-stream-id-request.md) | :heavy_check_mark:                                                                                                                                                                                                   | The original HTTP request that the internet-facing endpoint has received.<br/>                                                                                                                                       |
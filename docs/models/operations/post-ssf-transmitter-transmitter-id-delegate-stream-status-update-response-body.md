# PostSsfTransmitterTransmitterIdDelegateStreamStatusUpdateResponseBody

The message body of responses from delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamStatusUpdateResponseBody } from "@authlete/arena/models/operations";

let value:
  PostSsfTransmitterTransmitterIdDelegateStreamStatusUpdateResponseBody = {
    response: {
      status: "<value>",
    },
  };
```

## Fields

| Field                                                                                                                                                                                                               | Type                                                                                                                                                                                                                | Required                                                                                                                                                                                                            | Description                                                                                                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `result`                                                                                                                                                                                                            | [operations.PostSsfTransmitterTransmitterIdDelegateStreamStatusUpdateResult](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-status-update-result.md)                                   | :heavy_minus_sign:                                                                                                                                                                                                  | N/A                                                                                                                                                                                                                 |
| `response`                                                                                                                                                                                                          | [operations.DelegateStatusPostSsfTransmitterTransmitterIdDelegateStreamStatusUpdateResponse](../../models/operations/delegate-status-post-ssf-transmitter-transmitter-id-delegate-stream-status-update-response.md) | :heavy_check_mark:                                                                                                                                                                                                  | The HTTP response that the internet-facing endpoint should return to the endpoint accessor.<br/>                                                                                                                    |
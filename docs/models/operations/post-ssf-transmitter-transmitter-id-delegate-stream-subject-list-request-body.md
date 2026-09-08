# PostSsfTransmitterTransmitterIdDelegateStreamSubjectListRequestBody

The message body of requests to delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamSubjectListRequestBody } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdDelegateStreamSubjectListRequestBody =
  {
    options: {
      pretty: true,
    },
    request: {
      method: "<value>",
      uri: "https://oily-alert.com/",
      ipAddress: "192.168.0.1",
    },
  };
```

## Fields

| Field                                                                                                                                                                                                               | Type                                                                                                                                                                                                                | Required                                                                                                                                                                                                            | Description                                                                                                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `options`                                                                                                                                                                                                           | [operations.PostSsfTransmitterTransmitterIdDelegateStreamSubjectListOptions](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-subject-list-options.md)                                   | :heavy_minus_sign:                                                                                                                                                                                                  | N/A                                                                                                                                                                                                                 |
| `request`                                                                                                                                                                                                           | [operations.DelegateSubjectsPostSsfTransmitterTransmitterIdDelegateStreamSubjectListRequest](../../models/operations/delegate-subjects-post-ssf-transmitter-transmitter-id-delegate-stream-subject-list-request.md) | :heavy_check_mark:                                                                                                                                                                                                  | The original HTTP request that the internet-facing endpoint has received.<br/>                                                                                                                                      |
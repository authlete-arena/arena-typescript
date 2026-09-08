# PostSsfTransmitterTransmitterIdDelegateStreamSubjectListResponseBody

The message body of responses from delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamSubjectListResponseBody } from "@authlete/arena/models/operations";

let value:
  PostSsfTransmitterTransmitterIdDelegateStreamSubjectListResponseBody = {
    response: {
      status: "<value>",
    },
  };
```

## Fields

| Field                                                                                                                                                                                                                 | Type                                                                                                                                                                                                                  | Required                                                                                                                                                                                                              | Description                                                                                                                                                                                                           |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `result`                                                                                                                                                                                                              | [operations.PostSsfTransmitterTransmitterIdDelegateStreamSubjectListResult](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-subject-list-result.md)                                       | :heavy_minus_sign:                                                                                                                                                                                                    | N/A                                                                                                                                                                                                                   |
| `response`                                                                                                                                                                                                            | [operations.DelegateSubjectsPostSsfTransmitterTransmitterIdDelegateStreamSubjectListResponse](../../models/operations/delegate-subjects-post-ssf-transmitter-transmitter-id-delegate-stream-subject-list-response.md) | :heavy_check_mark:                                                                                                                                                                                                    | The HTTP response that the internet-facing endpoint should return to the endpoint accessor.<br/>                                                                                                                      |
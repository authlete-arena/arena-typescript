# PostSsfTransmitterTransmitterIdDelegateStreamSubjectRemoveResponseBody

The message body of responses from delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamSubjectRemoveResponseBody } from "@authlete/arena/models/operations";

let value:
  PostSsfTransmitterTransmitterIdDelegateStreamSubjectRemoveResponseBody = {
    response: {
      status: "<value>",
    },
  };
```

## Fields

| Field                                                                                                                                                                                                                     | Type                                                                                                                                                                                                                      | Required                                                                                                                                                                                                                  | Description                                                                                                                                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `result`                                                                                                                                                                                                                  | [operations.PostSsfTransmitterTransmitterIdDelegateStreamSubjectRemoveResult](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-subject-remove-result.md)                                       | :heavy_minus_sign:                                                                                                                                                                                                        | N/A                                                                                                                                                                                                                       |
| `response`                                                                                                                                                                                                                | [operations.DelegateSubjectsPostSsfTransmitterTransmitterIdDelegateStreamSubjectRemoveResponse](../../models/operations/delegate-subjects-post-ssf-transmitter-transmitter-id-delegate-stream-subject-remove-response.md) | :heavy_check_mark:                                                                                                                                                                                                        | The HTTP response that the internet-facing endpoint should return to the endpoint accessor.<br/>                                                                                                                          |
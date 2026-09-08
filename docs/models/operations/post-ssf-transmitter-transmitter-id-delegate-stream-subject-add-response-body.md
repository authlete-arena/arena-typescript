# PostSsfTransmitterTransmitterIdDelegateStreamSubjectAddResponseBody

The message body of responses from delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamSubjectAddResponseBody } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdDelegateStreamSubjectAddResponseBody =
  {
    response: {
      status: 627294,
    },
  };
```

## Fields

| Field                                                                                                                                                                                                               | Type                                                                                                                                                                                                                | Required                                                                                                                                                                                                            | Description                                                                                                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `result`                                                                                                                                                                                                            | [operations.PostSsfTransmitterTransmitterIdDelegateStreamSubjectAddResult](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-subject-add-result.md)                                       | :heavy_minus_sign:                                                                                                                                                                                                  | N/A                                                                                                                                                                                                                 |
| `response`                                                                                                                                                                                                          | [operations.DelegateSubjectsPostSsfTransmitterTransmitterIdDelegateStreamSubjectAddResponse](../../models/operations/delegate-subjects-post-ssf-transmitter-transmitter-id-delegate-stream-subject-add-response.md) | :heavy_check_mark:                                                                                                                                                                                                  | The HTTP response that the internet-facing endpoint should return to the endpoint accessor.<br/>                                                                                                                    |
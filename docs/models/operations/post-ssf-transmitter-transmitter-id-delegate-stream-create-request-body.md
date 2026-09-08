# PostSsfTransmitterTransmitterIdDelegateStreamCreateRequestBody

The message body of requests to delegate APIs.


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdDelegateStreamCreateRequestBody } from "authlete-arena/models/operations";

let value: PostSsfTransmitterTransmitterIdDelegateStreamCreateRequestBody = {
  options: {
    pretty: true,
  },
  request: {
    method: "<value>",
    uri: "https://these-bin.org/",
  },
};
```

## Fields

| Field                                                                                                                                                                                          | Type                                                                                                                                                                                           | Required                                                                                                                                                                                       | Description                                                                                                                                                                                    |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `options`                                                                                                                                                                                      | [operations.PostSsfTransmitterTransmitterIdDelegateStreamCreateOptions](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-create-options.md)                         | :heavy_minus_sign:                                                                                                                                                                             | N/A                                                                                                                                                                                            |
| `request`                                                                                                                                                                                      | [operations.PostSsfTransmitterTransmitterIdDelegateStreamCreateRequestRequestBody](../../models/operations/post-ssf-transmitter-transmitter-id-delegate-stream-create-request-request-body.md) | :heavy_check_mark:                                                                                                                                                                             | The original HTTP request that the internet-facing endpoint has received.<br/>                                                                                                                 |
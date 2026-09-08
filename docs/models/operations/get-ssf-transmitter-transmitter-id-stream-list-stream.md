# GetSsfTransmitterTransmitterIdStreamListStream

## Example Usage

```typescript
import { GetSsfTransmitterTransmitterIdStreamListStream } from "@authlete/arena/models/operations";

let value: GetSsfTransmitterTransmitterIdStreamListStream = {};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `id`                                                                                          | *number*                                                                                      | :heavy_minus_sign:                                                                            | This is the primary key of the record representing the stream.<br/>                           |
| `streamId`                                                                                    | *string*                                                                                      | :heavy_minus_sign:                                                                            | This is the stream ID that was automatically assigned when the stream was created.<br/>       |
| `createdAt`                                                                                   | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_minus_sign:                                                                            | This is the date and time when the stream was created. The format is `YYYY-MM-DDThh:mm:ss`.<br/> |
| `status`                                                                                      | [operations.StreamStatus](../../models/operations/stream-status.md)                           | :heavy_minus_sign:                                                                            | This is the status of the stream. The value is one of `enabled`, `paused`, or `disabled`.<br/> |
| `description`                                                                                 | *string*                                                                                      | :heavy_minus_sign:                                                                            | This is the description of the stream.<br/>                                                   |
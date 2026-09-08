# PostSsfTransmitterTransmitterIdEventRegisterSubIdUri1

The subject identifier with the `uri` format as defined in [Section 3.2.7. Uniform Resource Identifier (URI) Format](https://www.rfc-editor.org/rfc/rfc9493.html#section-3.2.7) of [RFC 9493: Subject Identifiers for Security Event Tokens](https://www.rfc-editor.org/rfc/rfc9493.html).


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdEventRegisterSubIdUri1 } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdEventRegisterSubIdUri1 = {
  format: "uri",
  uri: "https://free-fencing.com/",
};
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `format`           | *"uri"*            | :heavy_check_mark: | N/A                |
| `uri`              | *string*           | :heavy_check_mark: | N/A                |
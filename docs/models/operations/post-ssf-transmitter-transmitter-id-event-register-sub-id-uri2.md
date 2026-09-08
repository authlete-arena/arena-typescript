# PostSsfTransmitterTransmitterIdEventRegisterSubIdUri2

The subject identifier with the `uri` format as defined in [Section 3.2.7. Uniform Resource Identifier (URI) Format](https://www.rfc-editor.org/rfc/rfc9493.html#section-3.2.7) of [RFC 9493: Subject Identifiers for Security Event Tokens](https://www.rfc-editor.org/rfc/rfc9493.html).


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdEventRegisterSubIdUri2 } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdEventRegisterSubIdUri2 = {
  format: "uri",
  uri: "https://secret-swim.org",
};
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `format`           | *"uri"*            | :heavy_check_mark: | N/A                |
| `uri`              | *string*           | :heavy_check_mark: | N/A                |
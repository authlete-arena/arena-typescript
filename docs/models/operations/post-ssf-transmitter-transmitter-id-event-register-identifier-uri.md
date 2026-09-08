# PostSsfTransmitterTransmitterIdEventRegisterIdentifierURI

The subject identifier with the `uri` format as defined in [Section 3.2.7. Uniform Resource Identifier (URI) Format](https://www.rfc-editor.org/rfc/rfc9493.html#section-3.2.7) of [RFC 9493: Subject Identifiers for Security Event Tokens](https://www.rfc-editor.org/rfc/rfc9493.html).


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdEventRegisterIdentifierURI } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdEventRegisterIdentifierURI = {
  format: "uri",
  uri: "https://naughty-receptor.net/",
};
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `format`           | *"uri"*            | :heavy_check_mark: | N/A                |
| `uri`              | *string*           | :heavy_check_mark: | N/A                |
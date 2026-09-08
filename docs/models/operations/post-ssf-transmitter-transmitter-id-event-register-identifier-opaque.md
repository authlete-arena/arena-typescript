# PostSsfTransmitterTransmitterIdEventRegisterIdentifierOpaque

The subject identifier with the `opaque` format as defined in [Section 3.2.4. Opaque Identifier Format](https://www.rfc-editor.org/rfc/rfc9493.html#section-3.2.4) of [RFC 9493: Subject Identifiers for Security Event Tokens](https://www.rfc-editor.org/rfc/rfc9493.html).


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdEventRegisterIdentifierOpaque } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdEventRegisterIdentifierOpaque = {
  format: "opaque",
  id: "<id>",
};
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `format`           | *"opaque"*         | :heavy_check_mark: | N/A                |
| `id`               | *string*           | :heavy_check_mark: | N/A                |
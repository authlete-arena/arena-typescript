# PostSsfTransmitterTransmitterIdEventRegisterIdentifier3

The subject identifier with the `email` format as defined in [Section 3.2.2. Email Identifier Format](https://www.rfc-editor.org/rfc/rfc9493.html#section-3.2.2) of [RFC 9493: Subject Identifiers for Security Event Tokens](https://www.rfc-editor.org/rfc/rfc9493.html).


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdEventRegisterIdentifier3 } from "authlete-arena/models/operations";

let value: PostSsfTransmitterTransmitterIdEventRegisterIdentifier3 = {
  format: "email",
  email: "Emmet_Johns37@gmail.com",
};
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `format`           | *"email"*          | :heavy_check_mark: | N/A                |
| `email`            | *any*              | :heavy_check_mark: | N/A                |
# PostSsfTransmitterTransmitterIdEventRegisterSubIdEmail1

The subject identifier with the `email` format as defined in [Section 3.2.2. Email Identifier Format](https://www.rfc-editor.org/rfc/rfc9493.html#section-3.2.2) of [RFC 9493: Subject Identifiers for Security Event Tokens](https://www.rfc-editor.org/rfc/rfc9493.html).


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdEventRegisterSubIdEmail1 } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdEventRegisterSubIdEmail1 = {
  format: "email",
  email: "Sterling75@yahoo.com",
};
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `format`           | *"email"*          | :heavy_check_mark: | N/A                |
| `email`            | *string*           | :heavy_check_mark: | N/A                |
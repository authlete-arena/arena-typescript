# PostSsfTransmitterTransmitterIdEventRegisterIdentifierEmail

The subject identifier with the `email` format as defined in [Section 3.2.2. Email Identifier Format](https://www.rfc-editor.org/rfc/rfc9493.html#section-3.2.2) of [RFC 9493: Subject Identifiers for Security Event Tokens](https://www.rfc-editor.org/rfc/rfc9493.html).


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdEventRegisterIdentifierEmail } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdEventRegisterIdentifierEmail = {
  format: "email",
  email: "Bart_Hoeger@hotmail.com",
};
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `format`           | *"email"*          | :heavy_check_mark: | N/A                |
| `email`            | *string*           | :heavy_check_mark: | N/A                |
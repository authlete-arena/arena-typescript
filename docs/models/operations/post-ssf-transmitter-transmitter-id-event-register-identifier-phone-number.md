# PostSsfTransmitterTransmitterIdEventRegisterIdentifierPhoneNumber

The subject identifier with the `phone_number` format as defined in [Section 3.2.5. Phone Number Identifier Format](https://www.rfc-editor.org/rfc/rfc9493.html#section-3.2.5) of [RFC 9493: Subject Identifiers for Security Event Tokens](https://www.rfc-editor.org/rfc/rfc9493.html).


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdEventRegisterIdentifierPhoneNumber } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdEventRegisterIdentifierPhoneNumber = {
  format: "phone_number",
  phoneNumber: "366-993-3796 x44191",
};
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `format`           | *"phone_number"*   | :heavy_check_mark: | N/A                |
| `phoneNumber`      | *string*           | :heavy_check_mark: | N/A                |
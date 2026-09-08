# PostSsfTransmitterTransmitterIdEventRegisterSubIdAccount2

The subject identifier with the `account` format as defined in [Section 3.2.1. Account Identifier Format](https://www.rfc-editor.org/rfc/rfc9493.html#section-3.2.1) of [RFC 9493: Subject Identifiers for Security Event Tokens](https://www.rfc-editor.org/rfc/rfc9493.html).


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdEventRegisterSubIdAccount2 } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdEventRegisterSubIdAccount2 = {
  format: "account",
  uri: "https://spotless-corporation.org",
};
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `format`           | *"account"*        | :heavy_check_mark: | N/A                |
| `uri`              | *string*           | :heavy_check_mark: | N/A                |
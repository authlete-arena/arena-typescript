# PostSsfTransmitterTransmitterIdEventRegisterSubId11

The subject identifier with the `account` format as defined in [Section 3.2.1. Account Identifier Format](https://www.rfc-editor.org/rfc/rfc9493.html#section-3.2.1) of [RFC 9493: Subject Identifiers for Security Event Tokens](https://www.rfc-editor.org/rfc/rfc9493.html).


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdEventRegisterSubId11 } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdEventRegisterSubId11 = {
  format: "account",
  uri: "https://corny-developing.biz",
};
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `format`           | *"account"*        | :heavy_check_mark: | N/A                |
| `uri`              | *any*              | :heavy_check_mark: | N/A                |
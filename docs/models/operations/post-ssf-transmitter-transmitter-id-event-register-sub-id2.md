# PostSsfTransmitterTransmitterIdEventRegisterSubId2

The subject identifier with the `did` format as defined in [Section 3.2.6. Decentralized Identifier (DID) Format](https://www.rfc-editor.org/rfc/rfc9493.html#section-3.2.6) of [RFC 9493: Subject Identifiers for Security Event Tokens](https://www.rfc-editor.org/rfc/rfc9493.html).


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdEventRegisterSubId2 } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdEventRegisterSubId2 = {
  format: "did",
  url: "https://voluminous-wallaby.com/",
};
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `format`           | *"did"*            | :heavy_check_mark: | N/A                |
| `url`              | *any*              | :heavy_check_mark: | N/A                |
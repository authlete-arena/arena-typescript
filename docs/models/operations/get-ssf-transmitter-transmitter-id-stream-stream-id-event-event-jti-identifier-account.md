# GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiIdentifierAccount

The subject identifier with the `account` format as defined in [Section 3.2.1. Account Identifier Format](https://www.rfc-editor.org/rfc/rfc9493.html#section-3.2.1) of [RFC 9493: Subject Identifiers for Security Event Tokens](https://www.rfc-editor.org/rfc/rfc9493.html).


## Example Usage

```typescript
import { GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiIdentifierAccount } from "@authlete/arena/models/operations";

let value:
  GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiIdentifierAccount = {
    format: "account",
    uri: "https://educated-devil.name",
  };
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `format`           | *"account"*        | :heavy_check_mark: | N/A                |
| `uri`              | *string*           | :heavy_check_mark: | N/A                |
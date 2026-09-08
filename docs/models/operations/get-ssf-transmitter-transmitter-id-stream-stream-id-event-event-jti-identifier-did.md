# GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiIdentifierDid

The subject identifier with the `did` format as defined in [Section 3.2.6. Decentralized Identifier (DID) Format](https://www.rfc-editor.org/rfc/rfc9493.html#section-3.2.6) of [RFC 9493: Subject Identifiers for Security Event Tokens](https://www.rfc-editor.org/rfc/rfc9493.html).


## Example Usage

```typescript
import { GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiIdentifierDid } from "@authlete/arena/models/operations";

let value:
  GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiIdentifierDid = {
    format: "did",
    url: "https://pessimistic-honesty.biz/",
  };
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `format`           | *"did"*            | :heavy_check_mark: | N/A                |
| `url`              | *string*           | :heavy_check_mark: | N/A                |
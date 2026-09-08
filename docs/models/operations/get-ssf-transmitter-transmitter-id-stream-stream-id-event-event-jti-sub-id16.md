# GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiSubId16

The subject identifier with the `phone_number` format as defined in [Section 3.2.5. Phone Number Identifier Format](https://www.rfc-editor.org/rfc/rfc9493.html#section-3.2.5) of [RFC 9493: Subject Identifiers for Security Event Tokens](https://www.rfc-editor.org/rfc/rfc9493.html).


## Example Usage

```typescript
import { GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiSubId16 } from "@authlete/arena/models/operations";

let value: GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiSubId16 = {
  format: "phone_number",
  phoneNumber: "223.808.0691 x4201",
};
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `format`           | *"phone_number"*   | :heavy_check_mark: | N/A                |
| `phoneNumber`      | *any*              | :heavy_check_mark: | N/A                |
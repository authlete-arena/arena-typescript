# GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiSubIdPhoneNumber1

The subject identifier with the `phone_number` format as defined in [Section 3.2.5. Phone Number Identifier Format](https://www.rfc-editor.org/rfc/rfc9493.html#section-3.2.5) of [RFC 9493: Subject Identifiers for Security Event Tokens](https://www.rfc-editor.org/rfc/rfc9493.html).


## Example Usage

```typescript
import { GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiSubIdPhoneNumber1 } from "@authlete/arena/models/operations";

let value:
  GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiSubIdPhoneNumber1 = {
    format: "phone_number",
    phoneNumber: "1-961-568-9786",
  };
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `format`           | *"phone_number"*   | :heavy_check_mark: | N/A                |
| `phoneNumber`      | *string*           | :heavy_check_mark: | N/A                |
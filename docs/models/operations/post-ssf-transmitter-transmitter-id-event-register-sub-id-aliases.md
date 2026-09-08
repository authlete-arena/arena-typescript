# PostSsfTransmitterTransmitterIdEventRegisterSubIdAliases

The subject identifier with the `aliases` format as defined in [Section 3.2.8. Aliases Identifier Format](https://www.rfc-editor.org/rfc/rfc9493.html#section-3.2.8) of [RFC 9493: Subject Identifiers for Security Event Tokens](https://www.rfc-editor.org/rfc/rfc9493.html).


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdEventRegisterSubIdAliases } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdEventRegisterSubIdAliases = {
  format: "aliases",
  identifiers: [],
};
```

## Fields

| Field                                                                                                                                                                | Type                                                                                                                                                                 | Required                                                                                                                                                             | Description                                                                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `format`                                                                                                                                                             | [operations.PostSsfTransmitterTransmitterIdEventRegisterFormatAliases](../../models/operations/post-ssf-transmitter-transmitter-id-event-register-format-aliases.md) | :heavy_check_mark:                                                                                                                                                   | N/A                                                                                                                                                                  |
| `identifiers`                                                                                                                                                        | *operations.PostSsfTransmitterTransmitterIdEventRegisterIdentifierUnion*[]                                                                                           | :heavy_check_mark:                                                                                                                                                   | N/A                                                                                                                                                                  |
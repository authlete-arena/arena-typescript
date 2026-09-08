# GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiSubIdAliases

The subject identifier with the `aliases` format as defined in [Section 3.2.8. Aliases Identifier Format](https://www.rfc-editor.org/rfc/rfc9493.html#section-3.2.8) of [RFC 9493: Subject Identifiers for Security Event Tokens](https://www.rfc-editor.org/rfc/rfc9493.html).


## Example Usage

```typescript
import { GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiSubIdAliases } from "@authlete/arena/models/operations";

let value:
  GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiSubIdAliases = {
    format: "aliases",
    identifiers: [],
  };
```

## Fields

| Field                                                                                                                                                                                              | Type                                                                                                                                                                                               | Required                                                                                                                                                                                           | Description                                                                                                                                                                                        |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `format`                                                                                                                                                                                           | [operations.GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiFormatAliases](../../models/operations/get-ssf-transmitter-transmitter-id-stream-stream-id-event-event-jti-format-aliases.md) | :heavy_check_mark:                                                                                                                                                                                 | N/A                                                                                                                                                                                                |
| `identifiers`                                                                                                                                                                                      | *operations.GetSsfTransmitterTransmitterIdStreamStreamIdEventEventJtiIdentifierUnion*[]                                                                                                            | :heavy_check_mark:                                                                                                                                                                                 | N/A                                                                                                                                                                                                |
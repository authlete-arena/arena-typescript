# PostSsfTransmitterTransmitterIdEventRegisterSubId

The subject identifier with the `complex` format as defined in [Section 3.3. Complex Subject Members](https://openid.github.io/sharedsignals/openid-sharedsignals-framework-1_0.html#section-3.3) of [OpenID Shared Signals Framework Specification 1.0](https://openid.github.io/sharedsignals/openid-sharedsignals-framework-1_0.html).


## Example Usage

```typescript
import { PostSsfTransmitterTransmitterIdEventRegisterSubId } from "@authlete/arena/models/operations";

let value: PostSsfTransmitterTransmitterIdEventRegisterSubId = {
  format: "complex",
};
```

## Fields

| Field                                                                                                                                                                | Type                                                                                                                                                                 | Required                                                                                                                                                             | Description                                                                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `format`                                                                                                                                                             | [operations.PostSsfTransmitterTransmitterIdEventRegisterFormatComplex](../../models/operations/post-ssf-transmitter-transmitter-id-event-register-format-complex.md) | :heavy_check_mark:                                                                                                                                                   | N/A                                                                                                                                                                  |
| `additionalProperties`                                                                                                                                               | Record<string, *operations.PostSsfTransmitterTransmitterIdEventRegisterSubIdUnion3*>                                                                                 | :heavy_minus_sign:                                                                                                                                                   | N/A                                                                                                                                                                  |
# GetSsfTransmitterTransmitterIdStreamStreamIdDefaultSubjects

OPTIONAL. The `default_subjects` configured for this stream. If explicitly specified at stream creation, that value is used; if omitted, the Transmitter's `default_subjects` value is used instead. This property cannot be changed after stream creation.
Note that this property is proposed in [Issue 326 "default_subjects per stream"](https://github.com/openid/sharedsignals/issues/326) and is not included in the final version of the Shared Signals Framework specification.


## Example Usage

```typescript
import { GetSsfTransmitterTransmitterIdStreamStreamIdDefaultSubjects } from "@authlete/arena/models/operations";

let value: GetSsfTransmitterTransmitterIdStreamStreamIdDefaultSubjects = "NONE";

// Open enum: unrecognized values are captured as Unrecognized<string>
```

## Values

```typescript
"ALL" | "NONE" | Unrecognized<string>
```
# StreamStatus

This is the status of the stream. The value is one of `enabled`, `paused`, or `disabled`.


## Example Usage

```typescript
import { StreamStatus } from "@authlete/arena/models/operations";

let value: StreamStatus = "enabled";

// Open enum: unrecognized values are captured as Unrecognized<string>
```

## Values

```typescript
"enabled" | "paused" | "disabled" | Unrecognized<string>
```
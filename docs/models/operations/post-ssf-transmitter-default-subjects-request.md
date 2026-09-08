# PostSsfTransmitterDefaultSubjectsRequest

OPTIONAL. A string indicating the default behavior of newly created streams. If present, the value MUST be either `"ALL"` or `"NONE"`. If not provided, the Transmitter behavior in this regard is unspecified.
- `"ALL"` indicates that any subjects that are appropriate for the
  stream are added to the stream by default. The Receiver MAY remove
  subjects from the stream via the `remove_subject_endpoint`, causing
  events for those subjects to _not_ be transmitted. The Receiver MAY
  re-add any subjects removed this way via the `add_subject_endpoint`.

- `"NONE"` indicates that no subjects are added by default. The Receiver
  MAY add subjects to the stream via the `add_subject_endpoint`,
  causing only events for those subjects to be transmitted. The Receiver
  MAY remove subjects added this way via the `remove_subject_endpoint`.


## Example Usage

```typescript
import { PostSsfTransmitterDefaultSubjectsRequest } from "authlete-arena/models/operations";

let value: PostSsfTransmitterDefaultSubjectsRequest = "NONE";
```

## Values

```typescript
"ALL" | "NONE"
```
# Method

The delivery method. Supported values are `urn:ietf:rfc:8935` (PUSH) ([RFC 8935: Push-Based Security Event Token (SET) Delivery Using HTTP](https://www.rfc-editor.org/rfc/rfc8935.html)) and `urn:ietf:rfc:8936` (POLL) ([RFC 8936: Poll-Based Security Event Token (SET) Delivery Using HTTP](https://www.rfc-editor.org/rfc/rfc8936.html)).


## Example Usage

```typescript
import { Method } from "authlete-arena/models/operations";

let value: Method = "urn:ietf:rfc:8935";

// Open enum: unrecognized values are captured as Unrecognized<string>
```

## Values

```typescript
"urn:ietf:rfc:8935" | "urn:ietf:rfc:8936" | Unrecognized<string>
```
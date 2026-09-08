# Err

A value from the IANA "[Security Event Token Error Codes](https://www.iana.org/assignments/secevent/secevent.xhtml#secevent-error-codes)" registry that identifies the error.


## Example Usage

```typescript
import { Err } from "authlete-arena/models/operations";

let value: Err = "access_denied";

// Open enum: unrecognized values are captured as Unrecognized<string>
```

## Values

```typescript
"invalid_request" | "invalid_key" | "invalid_issuer" | "invalid_audience" | "authentication_failed" | "access_denied" | Unrecognized<string>
```
# QueryParamStatus

This query parameter specifies the stream status as a search criterion.
The allowed values are `enabled`, `paused`, and `disabled`.

## Example Usage

```typescript
import { QueryParamStatus } from "authlete-arena/models/operations";

let value: QueryParamStatus = "paused";
```

## Values

```typescript
"enabled" | "paused" | "disabled"
```
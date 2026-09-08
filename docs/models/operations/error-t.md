# ErrorT

The error information in the same format as an error object defined in [Section 2.6](https://www.rfc-editor.org/rfc/rfc8936.html#section-2.6) of [RFC 8936 Poll-Based Security Event Token (SET) Delivery Using HTTP](https://www.rfc-editor.org/rfc/rfc8936.html).


## Example Usage

```typescript
import { ErrorT } from "@authlete/arena/models/operations";

let value: ErrorT = {
  err: "authentication_failed",
  description: "The SET could not be authenticated",
};
```

## Fields

| Field                                                                                                                                                                          | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `err`                                                                                                                                                                          | [operations.Err](../../models/operations/err.md)                                                                                                                               | :heavy_check_mark:                                                                                                                                                             | A value from the IANA "[Security Event Token Error Codes](https://www.iana.org/assignments/secevent/secevent.xhtml#secevent-error-codes)" registry that identifies the error.<br/> |
| `description`                                                                                                                                                                  | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | A human-readable string that provides additional diagnostic information.<br/>                                                                                                  |
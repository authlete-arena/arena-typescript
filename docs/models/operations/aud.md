# Aud

Transmitter-Supplied, REQUIRED. A string or an array of strings containing an audience claim as defined in JSON Web Token (JWT) [RFC7519](https://www.rfc-editor.org/rfc/rfc7519.html) that identifies the Event Receiver(s) for the Event Stream. This property cannot be updated. If multiple Receivers are specified then the Transmitter SHOULD know that these Receivers are the same entity.



## Supported Types

### `any`

```typescript
const value: any = "ssf-receiver";
```

### `any[]`

```typescript
const value: any[] = [
  "ssf-receiver",
];
```


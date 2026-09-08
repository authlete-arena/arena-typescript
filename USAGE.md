<!-- Start SDK Example Usage [usage] -->
```typescript
import { Arena } from "@authlete/arena";

const arena = new Arena({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await arena.metadata.getProtectedResource({
    xFapiInteractionId: "1152537a-7f40-4405-860e-0fbdc75837b3",
  });

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->
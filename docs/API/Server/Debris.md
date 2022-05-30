# Debris

Utility that manages the programmatic removal of objects.

---

API

```typescript
add: (object: unknown, time: number) => void;
```

---

## Methods

??? abstract "Add: `#!typescript (object: unknown, time: number) => void`"

    #### Add
    Method that adds object to debris queue, destroying them after they have reached their     expiration time.

    ---
    ##### Example


    ```typescript
    Debris.add(object, number);

    // n seconds later, the object is destroyed!
    ```

# Audio

This controller handles all the Audio functionality for the client.

API

```typescript
add: (object: unknown, time: number) => void;
```

<br/>
## add

```typescript
Debris.add(object, number);

// n seconds later, the object is destroyed!
```

Method that adds object to debris queue, destroying them after they have reached their expiration time.

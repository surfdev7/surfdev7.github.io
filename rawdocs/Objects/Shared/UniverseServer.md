# UniverseServer

The `UniverseServer` object is created by `Core.Network.Universe` and stores the information for a single universe server.

<br/>
API

```typescript
type UniverseServer = {
	state: LocalServerState;
	id: string;
	creationTimeUTC: number;
};

type LocalServerState = "new" | "dead";
```

## Properties

!!! tip "id: `string`"

    #### id
    JobId of server. (value is `"studio"` if testing in Roblox studio otherwise **UUID**)

---

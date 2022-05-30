# Network

Service responsible for handling all networking related tasks on the servers end.

---

API

```typescript
Universe: {
      ServersChanged: Signal<(servers: UniverseServer[]) => void, false>;
      GetServers: () => UniverseServer[];
};

ClientEvents: {
      Trigger: <T extends ClientEvent>(event: T | ClientEvent, Player: Player) => void;
      TriggerAll: <T extends ClientEvent>(event: ClientEvent | T) => void;
},

GetPlayerPing: (Player: Player) => number;
```

---

## Methods

### Universe

Universe is the sub-service of Network responsible for tracking other servers within the place universe.

??? todo "ServersChanged: `#!typescript ServersChanged: Signal<(servers: UniverseServer[]) => void, false>`"

    #### ServersChanged

    Signal that fires when server list is updated internally. (when a server is created or destroyed)

    ---

    ##### Example

    ```typescript
      Core.Network.Universe.ServersChanged.Connect((servers: UniverseServer[]) => {
            // do something!
      });
      ```

??? abstract "GetServers: `#!typescript GetServers: () => UniverseServer[];`"

    #### GetServers
    Method to access the real time `UniverseServer[]` list.

    ---

    ##### Example

    ```typescript
    Core.Network.Universe.GetServers(); // UniverseServer[];
    ```

---

### ClientEvents

ClientEvents is the sub-directory of Network that allows the server to propagate an event to a client or clients.

??? abstract "Trigger: `#!typescript Trigger: <T extends ClientEvent>(event: T | ClientEvent, Player: Player) => void`"

    #### Trigger
    Method to trigger client event for a single client

    ---

    ##### Example

    ```typescript
    Core.Network.ClientEvents.Trigger(ClientEvent, Player);
    ```

??? abstract "TriggerAll: `#!typescript TriggerAll: <T extends ClientEvent>(event: ClientEvent | T) => void`"

    #### TriggerAll
    Method to trigger client event for all clients

    ---

    ##### Example

    ```typescript
    Core.Network.ClientEvents.TriggerAll(ClientEvent);
    ```

---

!!! attention

    #### GetPlayerPing will return **-1** if a players ping has not been registered yet.

??? abstract "GetPlayerPing: `#!typescript GetPlayerPing: (Player: Player) => number`"

    #### GetPlayerPing
    Method to get current registered ping of `Player`.

    ---

    ##### Example

    ```typescript
    Core.Network.GetPlayerPing(Player); // -> number
    ```

---

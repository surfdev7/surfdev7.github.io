# Moderation

Service responsible for handling all moderation tasks.

---

API

```typescript
BanLocalPlayerFromLocalServer: (Player: Player, reason: string) => void;

UnBanLocalPlayerFromLocalServer: (PlayerUserId: number) => void;

IsPlayerLocallyBanned: (Player: Player) => boolean;

PlayerPassedLocalModeration: (Player: Player) => boolean;

KickPlayer: (Player: Player, reason: string) => void;
```

---

## Methods

??? abstract "BanLocalPlayerFromLocalServer: `#!typescript (Player: Player, reason: string) => void`"

    #### BanLocalPlayerFromLocalServer
    Bans player from local server. (Not a cross server permanent ban)

    ---
    ##### Example
    ```typescript
    Moderation.BanLocalPlayerFromLocalServer(Player, string);

    // "YOU have been KICKED for <string reason>!"
    ```

??? abstract "UnBanLocalPlayerFromLocalServer: `#!typescript (PlayerUserId: number) => void`"

    #### UnBanLocalPlayerFromLocalServer
    UnBans player from local server. (only repeals local server ban)

    ---

    ##### Example

    ```typescript
    Moderation.UnBanLocalPlayerFromLocalServer(PlayerUserId);
    ```

??? abstract "IsPlayerLocallyBanned: `#!typescript (Player: Player) => boolean`"

    #### IsPlayerLocallyBanned
    Checks if player is locally banned. (used internally in users service)

    ---

    ##### Example

    ```lua
    print(Moderation.IsPlayerLocallyBanned(Player)); // -> true | false
    ```

??? abstract "PlayerPassedLocalModeration: `#!typescript (Player: Player) => boolean`"

    #### PlayerPassedLocalModeration
    Returns whether or not player is locally banned.

??? abstract "KickPlayer: `#!typescript (Player: Player, reason: string) => void `"

    #### KickPlayer
    The actual kick function of the server.

    ---

    ##### Example

    ```
    Moderation.KickPlayer(Player, string);

    // "YOU have been KICKED for <string reason>!"
    ```

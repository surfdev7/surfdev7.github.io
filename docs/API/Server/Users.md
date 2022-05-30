# Users

Service responsible for handling players and their `User` object(s).

---

## API

```typescript
UserJoined: (f: (user: User) => void) => void;

Leaderstats: {
      Watch: (statName: string, parseValue?: ((value: number) => string) | undefined) => void;
};

GetUserCache: () => Map<string, User>;

GetUserList: () => User[];

Get: (playerName: PlayerIdentifier) => User;

Exists: (playerName: PlayerIdentifier) => boolean;
```

---

## Methods

### Leaderstats

Leaderstats is a sub-service of Users responsible for tracking and handling leaderboard stats.

??? abstract "Watch: `#!typescript (statName: string, parseValue?: ((value: number) => string) | undefined) => void;`"

    #### Watch
    Tells service to monitor `statName` and generate leaderstats objects.

    ---

    ##### Example
    ```typescript
    Core.Users.Leaderstats.Watch("kills");
    ```
    In the example, players will be able to see their `"kills"` leaderstat next to their name on the leaderboard.

---

??? abstract "GetUserCache: `#!typescript () => Map<string, User>;`"

    #### GetUserCache
    Returns `ServerUsers` object from service.

    ---

    ##### Example
    ```typescript
    const users = Core.Users.GetUserCache();
    ```

??? abstract "GetUserList: `#!typescript () => User[];`"

    #### GetUserList
    Returns `ServerUsers` object mapped to a list.

    ---

    ##### Example
    ```typescript
    // This example awards points to the users who are currently in the game.
    Core.Users.GetUserList().forEach((user) => {
          awardPoints(user);
    });
    ```

!!! danger

    #### Potential type error

    **Before** calling `Users.Get` verify **first** that the user exists using `Users.Exists`.

    ---

    The `Get` method will only return a `User` object. It will not return `#!typescript undefined` if the user does not exist. This type guard bypass was intentionally implemented to avoid using the `#!typescript as unknown as T` workaround.

??? abstract "Get: `#!typescript (PlayerIdentifier) => User;`"

    #### Get
      Returns `User` object from `PlayerIdentifier`.

    ##### Example
    ```typescript
    // Player 'player1' is in the server.

    const user = Core.Users.Get("player1"); // -> user

    const user2 = Core.Users.Get(Player1); // -> user

    ```

??? abstract "Exists: `#!typescript (PlayerIdentifier) => boolean;`"

    #### Exists
      Returns whether the user `PlayerIdentifier` exists or not.

    ##### Example
    ```typescript
    print(Core.Users.Exists("Player1")); // -> false

    ```

---

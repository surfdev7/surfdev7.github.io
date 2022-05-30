## Welcome to the surfcore 2 documentation!

surfcore2 is the second version of surfcore. I decided to re-write the core to increase performance. The source code for surfcore2 is private, but the documentation is not.

<br/>
### A slightly overwhelming overlook at the API:

# Server

```typescript
Users: {
      UserJoined: (f: (user: User) => void) => void;
      Leaderstats: {
            Watch: (statName: string, parseValue?: ((value: number) => string) | undefined) => void;
      };
      GetUserCache: () => Map<string, User>;
      GetUserList: () => User[];
      Get: (playerName: PlayerIdentifier) => User;
      Exists: (playerName: PlayerIdentifier) => boolean;
},

Network: {
      Universe: {
            ServersChanged: Signal<(servers: UniverseServer[]) => void, false>;
            GetServers: () => UniverseServer[];
      };
      ClientEvents: {
            Trigger: <T extends ClientEvent>(event: T | ClientEvent, Player: Player) => void;
            TriggerAll: <T extends ClientEvent>(event: ClientEvent | T) => void;
      },
      GetPlayerPing: (Player: Player) => number;
},

Moderation: {
    BanLocalPlayerFromLocalServer: (Player: Player, reason: string) => void;
    UnBanLocalPlayerFromLocalServer: (PlayerUserId: number) => void;
    IsPlayerLocallyBanned: (Player: Player) => boolean;
    PlayerPassedLocalModeration: (Player: Player) => boolean;
    KickPlayer: (Player: Player, reason: string) => void;
},

Debris: {
      add: (object: unknown, time: number) => void;
}
```

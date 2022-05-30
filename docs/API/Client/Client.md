# Client

This controller handles the local client.

API

```typescript
Platform: string;

PlatformUpdate: Signal<(platform: Platform.clientPlatform) => void, false>;
```

<br/>
## Platform

```typescript
ClientCore.Client.Platform; // -> Platform.clientPlatform
```

`(property)` current platform client is running on. (based on Platform util inference).

Value: `Platform.clientPlatform`

-   `"computer"` (default) detected device is a computer.
-   `"phone"` detected device is a phone.
-   `"tablet"` detected device is a tablet.
-   `"console"` detected device is a console.

<br/>
## PlatformUpdate

```typescript
ClientCore.Client.PlatformUpdate.Connect((platform) => {
	print("Player is playing on: " + platform);
});
```

Signal for changes to client platform. This is usually triggered after the screen size or input changes.

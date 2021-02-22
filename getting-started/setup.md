---
description: How to set up the SDK in your project
---

# Setup

## Installation

You can implement the API is through Roblox's `require` feature.

Make a script in `ServerScriptService` with the following code:

```lua
local metrikSDK = require(WILL BE UPDATED WHEN RELEASED)

metrikSDK:Register(YOUR TOKEN HERE) -- This will register your game with our servers
metrikSDK:Start() -- This loads all the data that is needed for the API
```

Then change the `YOUR TOKEN HERE` to your Metrik Token, which you can get [here.](https://app.metrik.dev/settings/token/)

{% hint style="warning" %}
Remember to never share your Metrik Token with anybody
{% endhint %}

After all that, the Metrik SDK will be inserted in your game so that you can view, update and delete data as well as add custom data imports through Roblox.

### Access on the client

By default you cannot access the module on the client. To do so, you must enable it on the server:

```lua
metrikSDK:EnableClientAccess() -- This will enable client access on your game
```

Then you can use the basic functionality \(`GET` HTTP requests\) in your client

```lua
local placeID = game.PlaceId
local metrikSDK = require(game.ReplicatedStorage:WaitForChild("MetrikClient") -- This will access a version of the SDK on the client that was accessed on the server

-- Example usage (Not required)
gameVisits = metrikSDK:GetData("Visits", placeID)

print(gameVisits)


```




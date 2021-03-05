---
description: How to configure the Metrik SDK
---

# Configuration

If you have successfully set up the SDK, the next step is to configure it.

To start configuring, add this to your Metrik handler in `ServerScriptService`:

```lua
local metrikSDK = require(WILL BE UPDATED WHEN RELEASED)

configuration = {
    name = "your-place-name-here", -- Used to let Metrik know where the data is coming from. Defaults to your place's name.
    token = "XXXXXXXXXXXXXXXXXXXX", -- Replace this with your token. This will register your game with our servers
    build = "production", -- Used to know if you are using Metrik in a production environment. Defaults to 'development'
    clientAccessEnabled = true, -- Used to know whether or not to allow access to the Metrik SDK on the client
    ver = "stable" -- Used to know which version of the SDK to use. Defaults to 'stable'
}

metrikSDK:Start(configuration) -- This loads all the data that is needed for the API & SDK
```

## Configuration Attributes

### Name

The name is used to let the Metrik servers know what place the data is coming from. The name must follow these rules:

* No caps \(`ABCDEFGHIJKLMNOPQRSTUVXWYZ`\)
* No spaces \( ``\)
* Dashes between words \(`place-name`\)

If you follow these rules while naming your place, it will not error. If you do follow these rules and it does error, contact us through our messenger to get more information.

{% hint style="info" %}
Once the data has been entered into Metrik, it will be formatted from `place-name` to `Place Name` and added as a new 
{% endhint %}


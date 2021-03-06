---
description: How to configure the Metrik SDK
---

# Configuration

If you have successfully set up the SDK, the next step is to configure it.

To start configuring, add this to your Metrik handler in `ServerScriptService`:

```lua
local metrikSDK = require(WILL BE UPDATED WHEN RELEASED)

configuration = {
    name = "Your Place Name Here", -- Used to let Metrik know what this place should be called.
    slug = "your-place-slug-here", -- Used to let Metrik know where the data is coming from. Defaults to your place's name.
    parent = "your-app-slug-here", -- Used to let Metrik know where to nest your data. If left empty, will default to the main app.
    token = "XXXXXXXXXXXXXXXXXXXX", -- Replace this with your token. This will register your game with our servers
    build = "production", -- Used to know if you are using Metrik in a production environment. Defaults to 'development'
    clientAccessEnabled = true, -- Used to know whether or not to allow access to the Metrik SDK on the client
    ver = "stable" -- Used to know which version of the SDK to use. Defaults to 'stable'
}

metrikSDK:Start(configuration) -- This loads all the data that is needed for the API & SDK
```

## Configuration Attributes

### Name

#### _STRING_

The name attribute is simply cosmetic, and can be left if you want to keep the configuration as short as possible. The name is used to display on the Metrik web app what this place is named.

If you have no name set, the slug will be formatted from `place-slug` to `Place Slug`, for example until you set a proper name.

### Slug

#### _STRING_

The slug attribute is used to let the Metrik servers know what place the data is coming from. The slug must follow these rules:

* No caps \(`ABCDEFGHIJKLMNOPQRSTUVXWYZ`\)
* No spaces \( ``\)
* Dashes between words \(`place-slug`\)

If you follow these rules while naming your place, it will not error. If you do follow these rules and it does error, contact us through our messenger to get more information.

If you have no name set, the slug will be formatted from `place-slug` to `Place Slug`, for example until you set a proper name.

### Parent

#### _STRING_

The parent attribute is used to let Metrik know where exactly to nest your new Place. This is recommended because otherwise your workspace will become very messy and unorganized. The attribute must contain an app slug that has already been created inside of your workspace.

{% hint style="info" %}
To create a new App, you can visit [app.metrik.dev/new/app](https://app.metrik.dev/new/app)
{% endhint %}

### Token

#### _STRING_

The token is assigned to your workspace 


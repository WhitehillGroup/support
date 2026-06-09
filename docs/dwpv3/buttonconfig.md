---
icon: tools
label: Button Configuration
order: 94
tags: [Configuration]
image: /static/assets/whg_headbanner.png
authors:
  - name: everywhxn
    link: https://github.com/everywhxn
    avatar: https://avatars.githubusercontent.com/u/219159259
categories:
  - Whitehill
  - DWProx
  - V3
---
# Configuring Your V3 Buttons

![](/static/assets/banners/whg_v3config.png)

Don't press the button, they said.

!!!warning
This page assumes the user has basic knowledge of the Roblox scripting language, Luau.
!!!

---

Each button inside `DWProx` **->** `Buttons` will have a `ButtonSettings` [ModuleScript](https://create.roblox.com/docs/reference/engine/classes/ModuleScript), which will look as follows:

```lua
local ButtonSettings = {
	-- / CONFIG / --
	["WhitelistEnabled"] = false,
	
	-- / PROXIMITYPROMPT / --
	["ProximityPrompt"] = false,
	["HoldDuration"] = 0.25,
	["MaxActivationDistance"] = 5,
	["GamepadKeyCode"] = "ButtonX",
	["KeyboardKeyCode"] = "E", 

	
	-- / SYSTEM / --
	["ButtonSpec"] = "\80\84\72\49",
}
return ButtonSettings

```

---

### WhitelistEnabled
=== `boolean`

Whether to enable or disable the button whitelist.

---

Example:
```lua
["WhitelistEnabled"] = false
```

===

### ProximityPrompt
=== `boolean`

Whether to enable or disable proximity-prompt mode.

---

Example:
```lua
["ProximityPrompt"] = false
```

===

### HoldDuration
=== `number`

Controls how long player has to hold the prompt before the button is pressed.

---

Example:
```lua
["HoldDuration"] = 2.5
```

===

### MaxActivationDistance
=== `number`

Controls how far you can be from the button before you can click it.

---

Example:
```lua
["MaxActivationDistance"] = 5
```

===

### GamepadKeyCode
=== `string`

Gamepad key-code to be used on the prompt. See more codes [here](https://create.roblox.com/docs/reference/engine/enums/KeyCode).

---

Example:
```lua
["GamepadKeyCode"] = "ButtonX"
```

===

### KeyboardKeyCode
=== `string`

Keyboard key-code to be used on the prompt. See more codes [here](https://create.roblox.com/docs/reference/engine/enums/KeyCode).

---

Example:
```lua
["KeyboardKeyCode"] = "E"
```

===

### ButtonSpec
=== `string`

!!!danger
Under any circumstances, **do not** modify this value. Otherwise, you might **brick the system**.
!!!

===

---

!!!success Configuration Complete!

Not working? Make sure you followed the syntax, or visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.

!!!

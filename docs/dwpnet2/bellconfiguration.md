---
icon: tools
label: Bell Configuration
order: 93
tags: [Configuration]
image: /static/assets/whg_headbanner.png
authors:
  - name: roaxcean
    link: https://github.com/roaxcean
    avatar: https://avatars.githubusercontent.com/u/219159259
categories:
  - Whitehill
  - DWProx
  - Net2+
---
# Configuring Your Net2+ Bells

![](/static/assets/banners/whg_net2config.png)

Chimes obnoxiously in your ears.

!!!warning
This page assumes the user has basic knowledge of the Roblox scripting language, Luau.
!!!

---

Each button inside `DWProx Net2+` **->** `Bell` will have a `Settings` [ModuleScript](https://create.roblox.com/docs/reference/engine/classes/ModuleScript), which will look as follows:

=== Chimebox

```lua
local ChimeboxSettings = {
	-- / CONFIG / --
	["WhitelistEnabled"] = false, -- When True This Door Release Will Only Work For Users / Groups In The Whitelist Thats In The Main Door Settings! (Authorised People / Groups List)
	-- / SOUND / --
	["SoundID"] = "rbxassetid://1840084282", -- Chimebox SoundId (You Must Keep The *rbxassetid://* At The Start Of The ID)
	["Volume"] = 1, -- Chimebox Volume
	["PlaybackSpeed"] = 1, -- Chimebox Pitch
	
	-- / SYSTEM / --
	["Identifier"] = "\67\104\105\109\101\66\111\120\84\121\112\101\65", -- DO NOT TOUCH THIS!
}
return ChimeboxSettings
```

=== Doorbell

```lua
local ButtonSettings = {
	-- / CONFIG / --
	["WhitelistEnabled"] = false, -- When True This Button Will Only Work For Users In The Whitelist Thats In The Main Door settings!

	-- / SYSTEM / --
	["ButtonSpec"] = "\66\101\108\108\84\121\112\101\65", -- DO NOT TOUCH THIS!
}
return ButtonSettings

```

===

---

## Chimebox

### WhitelistEnabled
=== `boolean`

Whether to enable or disable the bell whitelist.

---

Example:
```lua
["WhitelistEnabled"] = false
```

===

### SoundID
=== `string`

Sound ID to play when the chimebox is triggered.

!!!alert
You **must** keep the `rbxassetid://` part of the Sound ID.
!!!

---

Example:
```lua
["SoundID"] = "rbxassetid://1840084282"
```

===

### Volume
=== `number`

Volume at which the chimebox will play it's sound, `1` being the standard volume.

---

Example:
```lua
["Volume"] = 1
```

===

### PlaybackSpeed
=== `number`

Speed at which the chimebox will play it's sound, `1` being the standard speed.

---

Example:
```lua
["PlaybackSpeed"] = 1
```

===

### Identifier
=== `string`

!!!danger
Under any circumstances, **do not** modify this value. Otherwise, you might **brick the system**.
!!!

===

---

## Doorbell

### WhitelistEnabled
=== `boolean`

Whether to enable or disable the bell whitelist.

---

Example:
```lua
["WhitelistEnabled"] = false
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


---
icon: tools
label: Reader Configuration
order: 95
tags: [Configuration]
image: /static/assets/whg_headbanner.png
authors:
  - name: Dunbars123
    link: https://github.com/michaeldun123
    avatar: https://avatars.githubusercontent.com/u/42805814
  - name: roaxcean
    link: https://github.com/roaxcean
    avatar: https://avatars.githubusercontent.com/u/219159259
categories:
  - Whitehill
  - DWProx
  - V3
---
# Configuring Your V3 Readers

![](/static/assets/banners/whg_v3config.png)

Beep beep, I need my cards.

!!!warning
This page assumes the user has basic knowledge of the Roblox scripting language, Luau.
!!!

---

## Default Readers

Each reader inside `DWProx` **->** `Readers` will have a `ReaderSettings` [ModuleScript](https://create.roblox.com/docs/reference/engine/classes/ModuleScript), which will look as follows:

```lua
--[[        ____ _       ______                 
 		   / __ \ |     / / __ \_________  _  __
 		  / / / / | /| / / /_/ / ___/ __ \| |/_/
		 / /_/ /| |/ |/ / ____/ /  / /_/ />  <  
		/_____/ |__/|__/_/   /_/   \____/_/|_|  
		Made By DuckyProductions And Whitehill ET
		
]]

local Settings = {	
	-- / CARD / --
	["Cards"] = {"1", "2", "3", "4", "5", "0"},
	["WhitelistEnabled"] = false,
	
	-- / SYSTEM / --
	["ReaderSpec"] = "\80\50\50\53"
}
return Settings
```

---

### Cards
=== `{ number }`
A table of Access Levels that are whitelisted to use the reader **at any time**.

---

Example:
```lua
["Cards"] = {"1", "2", "3", "4", "5", "0"}
```

===

### WhitelistEnabled
=== `boolean`

Whether to enable or disable the reader whitelist.

---

Example:
```lua
["WhitelistEnabled"] = false
```

===

### ReaderSpec
=== `string`

!!!danger
Under any circumstances, **do not** modify this value. Otherwise, you might **brick the system**.
!!!

===

---

## Custom Readers

!!!warning
These settings apply only to the **Custom Reader**, it will not work on default readers.
!!!

Same with default readers, you can find `ReaderSettings` [ModuleScript](https://create.roblox.com/docs/reference/engine/classes/ModuleScript) as a child of the reader model.

```lua
--[[        ____ _       ______                 
 		   / __ \ |     / / __ \_________  _  __
 		  / / / / | /| / / /_/ / ___/ __ \| |/_/
		 / /_/ /| |/ |/ / ____/ /  / /_/ />  <  
		/_____/ |__/|__/_/   /_/   \____/_/|_|  
		Made By DuckyProductions And Whitehill ET
		
]]

local Settings = {	
	-- / CARD / --
	["Cards"] = {"1", "2", "3", "4", "5", "0"},
	["WhitelistEnabled"] = false,
	
	-- / CUSTOM READER SETTINGS / --
	["LEDAccept"] = function(Reader)
		-- Handle function here
	end,
	["LEDIdle"] = function(Reader)
		-- Handle function here
	end,
	["LEDDeny"] = function(Reader)
		-- Handle function here
	end,
	["LEDLocked"] = function(Reader)
		-- Handle function here
	end,
	
	["SoundAccept"] = function(Reader)
		-- Handle function here
	end,
	["SoundDeny"] = function(Reader)
		-- Handle function here
	end,
	
	-- / SYSTEM / --
	["ReaderSpec"] = "CUSTOM"
}
return Settings
```

---

!!!info
`Cards`, `WhitelistEnabled` and `ReaderSpec` work identically to the default reader.
!!!

!!!warning
This section is more prone to user errors, if you don't know what you're doing, use the default readers. No support will be provided for custom readers.
!!!

### LEDAccept
=== `( Model ) -> ()`

Used when the reader accepts a card.

===

### LEDIdle
=== `( Model ) -> ()`

Used when the goes back to an 'idle' state.

===

### LEDDeny
=== `( Model ) -> ()`

Used when the reader denies a card.

===

### LEDLocked
=== `( Model ) -> ()`

Used when the reader goes into a 'locked' state.

===

### SoundAccept
=== `( Model ) -> ()`

Used for positive outcome interactions. (Ex.: Accepting a card.)

===

### SoundDeny
=== `( Model ) -> ()`

Used for negative outcome interactions. (Ex.: Denying a card.)

===

---

!!!success Configuration Complete!

Not working? Make sure you followed the syntax, or visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.

!!!

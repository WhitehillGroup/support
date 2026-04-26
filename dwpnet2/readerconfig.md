# Configuring Your Net2+ Readers

![](/static/assets/banners/whg_net2config.png)

Beep beep beeeeep, these readers need an ethernet connection.

!!!warning
This page assumes the user has basic knowledge of the Roblox scripting language, Luau.
!!!

---

Each reader inside `DWProx Net2+` **->** `Readers` will have a `ReaderSettings` [ModuleScript](https://create.roblox.com/docs/reference/engine/classes/ModuleScript), which will look as follows:

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
	["ReaderSpec"] = "\84\121\112\101\65"
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

!!!success Configuration Complete!

Not working? Make sure you followed the syntax, or visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.

!!!

# Configuring Your EAS

![](/static/assets/banners/whg_easconfig.png)

Mini-modding right here.

!!!warning
This page assumes the user has basic knowledge of the Roblox scripting language, Luau.
!!!

---

Your default configuration, found in `JSM | Intelli-Sense EAS` **->** `JSM | Controller` **->** `Settings`, is structured as follows:

```lua
--[[ 
	           _______ __  ___
	          / / ___//  |/  /
	     __  / /\__ \/ /|_/ / 
	    / /_/ /___/ / /  / /  
	    \____//____/_/  /_/
 	         EAS System
 	      © Whitehill Group

]]--
local Settings = {
	-----------------------------------------------------------------
	["SiteName"] = "Whitehill Group",
	["ClockEnabled"] = true,
	-----------------------------------------------------------------
	["Login"] = {
		["LowestAccessLevel"] = "Employee",
		["SCOv3Location"] = nil,
	},
	["AutomaticIntegrations"] = {
		["Applegate_VoCoVo"] = false,
		["Kybo_Walvo"] = false,
	},
}
return Settings
```

---

## General Settings

### SiteName
=== `string`
This will be displayed on the controller screen.

---

Example:
```lua
["SiteName"] = "Cardiff Bay Shopping Centre"
```

===

### ClockEnabled
=== `boolean`
Whether to display your game's time.

---

Example:
```lua
["ClockEnabled"] = false
```

!!!info
Note: It will display the game time, not the player's time.
!!!
===

### Login
=== `{ [string]: string | Folder? }`
For additional security, it is recommended to only log in with an operator barcode.

- **LowestAccessLevel**: (`"Administrator" | "Manager" | "Employee"`) 
  Lowest access level via the Operator Barcode. (See [Accounts Configuration](/sco/accounts.md#operatorid) for more info.) 
- **SCOv3Location**: (`Folder?`)
  Set to the SCO v3.1 root folder if you plan on using shared accounts.

---

Example:
```lua
["Login"] = {
	["LowestAccessLevel"] = "Manager",
	["SCOv3Location"] = workspace["JSM | SelfCheckout V3"],
}
```

===

### AutomaticIntegrations
=== `{ [string]: boolean }`
- **Applegate_VoCoVo**: (`boolean`)
  Integration with VoCoVo by Applegate. Set to `false` if not using.
- **Kybo_Walvo**: (`boolean`)
  Integration with Walvo by Kybo. Set to `false` if not using.

---

Example:
```lua
["AutomaticIntegrations"] = {
	["Applegate_VoCoVo"] = false,
	["Kybo_Walvo"] = true,
}
```

===

---

## Accounts

!!!info
For a detailed guide, see SelfServ SCO [Accounts Configuration](/sco/accounts.md) page. The EAS Accounts and SCO Accounts are identical.
!!!

---

## Finalizing

Now, using the examples provided, a complete `Settings` module will look as follows:

```lua
--[[ 
	           _______ __  ___
	          / / ___//  |/  /
	     __  / /\__ \/ /|_/ / 
	    / /_/ /___/ / /  / /  
	    \____//____/_/  /_/
 	         EAS System
 	      © Whitehill Group

]]--
local Settings = {
	-----------------------------------------------------------------
	["SiteName"] = "Cardiff Bay Shopping Centre",
	["ClockEnabled"] = false,
	-----------------------------------------------------------------
	["Login"] = {
		["LowestAccessLevel"] = "Manager",
		["SCOv3Location"] = workspace["JSM | SelfCheckout V3"],
	},
	["AutomaticIntegrations"] = {
		["Applegate_VoCoVo"] = false,
		["Kybo_Walvo"] = true,
	},
}
return Settings
```

---

!!!success Configuration Complete!

Not working? Make sure you followed the syntax, or visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.
!!!

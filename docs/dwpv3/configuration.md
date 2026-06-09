---
icon: tools
label: Configuration
order: 96
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
# Configuring Your V3

![](/static/assets/banners/whg_v3config.png)

Welcome to customization heaven. (#2)

!!!warning
This page assumes the user has basic knowledge of the Roblox scripting language, Luau.
!!!

!!!danger
The default doors that ship with DWProx use a **different** configuration module. Make sure you edit the actual V3 configuration module.
!!!

---

Your configuration module, found under each V3 door `DWProx` **->** `Settings`, is structured as follows:

```lua
--[[        ____ _       ______                 
 		   / __ \ |     / / __ \_________  _  __
 		  / / / / | /| / / /_/ / ___/ __ \| |/_/
		 / /_/ /| |/ |/ / ____/ /  / /_/ />  <  
		/_____/ |__/|__/_/   /_/   \____/_/|_|  
		Made By DuckyProductions And Whitehill ET
		
		V3.5
]]

local Settings = {

	-- / General Settings / --	
	["OpenTime"] = 5,

	["Accepted"] = function (beans: number): ()
		print("The card that has beans inside got the id of: " .. beans)
	end,
	["Return"] = function (): ()
		return false
	end,
	["Denied"] = function (): ()
		return false
	end,

	-- / Whitelist Settings / --
	["AuthorisedPeople"] = {
		112672616, -- AlexG_1337
		199830788, -- Coco_Beagle
		780522, -- jakisall
		123570775, -- crazydoge2016
		88605917, -- DanielF
	    9109291923, -- everywhxn
	}, 
	["AuthorisedGroups"] = {
		["5203509"] = {255}, -- DuckyProductions
		["5150453"] = {255, 254, 253}, -- Whitehill
	},

	-- / Webhook Settings / --
	["LogCorrectScans"] = false,
	["LogIncorrectScans"] = false,
	["LogButtonPresses"] = false,

	["GameLogo"] = "",
	["DoorName"] = "",

	-- / Global API Settings / --
	["GAPI-Lock"] = true,
	["GAPI-Fire"] = true,
	["GAPI-Open"] = true,
	["GAPI-Hold"] = true,

	-- / Expanse Integration / --
	["ExpanseEnabled"] = false,
	["ExpanseLocation"] = script.ExpanseIntegration.Value,
	["ExpanseInterfaceID"] = 1,
}

return Settings
```

---

## General Settings

### OpenTime
=== `number`
For how long the door should stay open after accepting a card.

---

Example:
```lua
["OpenTime"] = 5
```
===

### Accepted
=== `( number ) -> ()`
A custom function to run after accepting a card.
Passing either the Card ID (`number`) as the first argument.

---

Example:
```lua
["Accepted"] = function (beans): ()
    print("The card that has beans inside got the id of: " .. beans)
end
```
===

### Return
=== `(number) -> ()`
A custom function to run after `OpenTime` has passed.

---

Example:
```lua
["Return"] = function (): ()
    return false
end
```
===

### Denied
=== `(number) -> ()`
A custom function to run after denying a card.

---

Example:
```lua
["Denied"] = function (): ()
    return false
end
```
===

---

## Whitelist Settings

### AuthorisedPeople
=== `{ number }`
A table of Roblox User IDs that are whitelisted to use the readers/exit buttons **when whitelist is enabled**.

---

Example:
```lua
["AuthorisedPeople"] = {
	112672616, -- AlexG_1337
	199830788, -- Coco_Beagle
	780522, -- jakisall
	123570775, -- crazydoge2016
	88605917, -- DanielF
	9109291923, -- everywhxn
} 
```

===

### AuthorisedGroups
=== `{ [string]: number }`
A dictionary of Roblox Community IDs holding Rank IDs that are whitelisted to use the readers/exit buttons **when whitelist is enabled**.

---

Example:
```lua
["AuthorisedGroups"] = {
	["5203509"] = {255}, -- DuckyProductions
	["5150453"] = {255, 254, 253}, -- Whitehill
}
```

===

---

## Webhook Settings

!!!warning
The Webhook URL is stored under `Settings`, in a `WebhookURL` ModuleScript.
!!!

### LogCorrectScans
=== `boolean`
Should V3 log correct scans.

---

Example:
```lua
["LogCorrectScans"] = false
```
===

### LogIncorrectScans
=== `boolean`
Should V3 log incorrect scans.

---

Example:
```lua
["LogIncorrectScans"] = false
```
===

### LogButtonPresses
=== `boolean`
Should V3 log button presses.

---

Example:
```lua
["LogButtonPresses"] = false
```
===

### GameLogo
=== `string`
Image URL, not a Roblox Image ID, for the webhook to use.

---

Example:
```lua
["GameLogo"] = "https://example.com/some/path/to/image.png"
```
===

### DoorName
=== `string`
Door name for the webhook to use.

---

Example:
```lua
["DoorName"] = "Main Entrace Door"
```
===

---

## Global API Settings

### GAPI-Lock
=== `boolean`
Should the doors listen to Global API Lock requests?

---

Example:
```lua
["GAPI-Lock"] = false
```
===

### GAPI-Fire
=== `boolean`
Should the doors listen to Global API Fire requests?

---

Example:
```lua
["GAPI-Fire"] = false
```
===

### GAPI-Open
=== `boolean`
Should the doors listen to Global API Open requests?

---

Example:
```lua
["GAPI-Open"] = false
```
===

### GAPI-Hold
=== `boolean`
Should the doors listen to Global API Hold requests?

---

Example:
```lua
["GAPI-Hold"] = false
```
===

---

## Expanse Integration Settings

!!!danger
This section is dedicated to Ae Expanse by [SCADA](https://www.roblox.com/communities/5791519/Scada-Control-Systems#!/about), which you can find [here](https://www.roblox.com/games/11387612316/Scada-Product-Hub). **To use Expanse you need a separate license.**
!!!

### ExpanseEnabled
=== `boolean`
Should Expanse be used?

---

Example:
```lua
["ExpanseEnabled"] = false
```
===

### ExpanseLocation
=== `Folder`
Location of the Ae Expanse `Folder`.

---

Example:
```lua
["ExpanseLocation"] = script.ExpanseIntegration.Value
```
===

### ExpanseInterfaceID
=== `number`
The Expanse Interface ID to listen to.

---

Example:
```lua
["ExpanseInterfaceID"] = 1
```
===

---

!!!success Configuration Complete!

Not working? Make sure you followed the syntax, or visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.
!!!

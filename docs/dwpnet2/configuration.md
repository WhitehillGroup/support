---
icon: tools
label: Configuration
order: 95
tags: [Configuration]
image: /static/assets/whg_headbanner.png
authors:
  - name: roaxcean
    link: https://github.com/roaxcean
    avatar: https://avatars.githubusercontent.com/u/219159259
  - name: Dunbars123
    link: https://github.com/michaeldun123
    avatar: https://avatars.githubusercontent.com/u/42805814
categories:
  - Whitehill
  - DWProx
  - Net2+
---
# Configuring Your Net2+

![](/static/assets/banners/whg_net2config.png)

Welcome to customization heaven. (#2)

!!!warning
This page assumes the user has basic knowledge of the Roblox scripting language, Luau.
!!!

---

Your Paxton configuration module, found under each Net2+ door `DWProx Net2+` **->** `PaxtonSettings`, is structured as follows:

```lua
--[[        ____ _       ______                 
 		   / __ \ |     / / __ \_________  _  __
 		  / / / / | /| / / /_/ / ___/ __ \| |/_/
		 / /_/ /| |/ |/ / ____/ /  / /_/ />  <  
		/_____/ |__/|__/_/   /_/   \____/_/|_|  
		Made By DuckyProductions And Whitehill ET
			   ___           _              
			  / _ \__ ___  _| |_ ___  _ __  
			 / /_)/ _` \ \/ / __/ _ \| '_ \ 
			/ ___/ (_| |>  <| || (_) | | | |
			\/    \__,_/_/\_\\__\___/|_| |_|
			              			Net2+	
			              			
]]--

local Settings = {

	-- / General Settings / --
	["OpenTime"] = 10,

	["Accepted"] = function (): ()
		script.Parent.Parent:WaitForChild("DoorUnlockingAPIThings"):Fire("Open")
	end,
	["Return"] = function (): ()
		script.Parent.Parent:WaitForChild("DoorUnlockingAPIThings"):Fire("Close")
	end,
	["Denied"] = function (): ()
		return false
	end,

	-- / Webhook Settings / --
	["LogCorrectScans"] = false,
	["LogIncorrectScans"] = false,
	["LogButtonPresses"] = false,
	["LogDoorReleases"] = false,

	["GameLogo"] = "",
	["DoorName"] = "",

	-- / Global API Settings / --
	["GAPI-Lock"] = true,
	["GAPI-Fire"] = true,
	["GAPI-Open"] = true,
	["GAPI-Hold"] = true,
	["GAPI-ResetReleases"] = true,

	-- / Expanse Integration / --
	["ExpanseEnabled"] = true,
	["ExpanseLocation"] = script.ExpanseIntegration.Value,
	["ExpanseInterfaceID"] = 1,

	["DisableConsoleOutputs"] = false,

	["CabinetMaximumAngle"] = -120,

	-- / Whitelist Settings / -- 
	["AuthorisedPeople"] = {
		112672616, -- AlexG_1337
		199830788, -- Coco_Beagle
	}, 
	["AuthorisedGroups"] = {
		["5203509"] = {255}, -- DuckyProductions
		["5150453"] = {255, 254, 253}, -- Whitehill
	},
	-----------------------------------------------------------------
	["CabinetAuthorisedPeople"] = {
		112672616, -- AlexG_1337
		199830788, -- Coco_Beagle
	}, 
	["CabinetAuthorisedGroups"] = {
		["5203509"] = {255}, -- DuckyProductions
		["5150453"] = {255, 254, 253}, -- Whitehill
	},
	["DisableCabinetWhitelist"] = false,
	-----------------------------------------------------------------
	["DoorReleaseAuthorisedPeople"] = {
		112672616, -- AlexG_1337
		199830788, -- Coco_Beagle
	},
	["DoorReleaseAuthorisedGroups"] = {
		["5203509"] = {255}, -- DuckyProductions
		["5150453"] = {255, 254, 253}, -- Whitehill
	},
	-----------------------------------------------------------------
	["DoorBellAuthorisedPeople"] = {
		112672616, -- AlexG_1337
		199830788, -- Coco_Beagle
	},
	["DoorBellAuthorisedGroups"] = {
		["5203509"] = {255}, -- DuckyProductions
		["5150453"] = {255, 254, 253}, -- Whitehill
	},
	-----------------------------------------------------------------
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
["OpenTime"] = 20
```
===

### Accepted
=== `( number | string ) -> ()`
A custom function to run after accepting a card. 
Passing either the Card ID (`number`) or Card Function (`string`) as the first argument.

---

Example:
```lua
["Accepted"] = function (): ()
    script.Parent.Parent:WaitForChild("DoorUnlockingAPIThings"):Fire("Open")
end
```
===

### Return
=== `() -> ()`
A custom function to run after `OpenTime` has passed.

---

Example:
```lua
["Return"] = function (): ()
    script.Parent.Parent:WaitForChild("DoorUnlockingAPIThings"):Fire("Close")
end
```
===

### Denied
=== `() -> ()`
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

## Webhook Settings

!!!warning
The Webhook URL is stored under `PaxtonSettings`, in a `WebhookURL` ModuleScript.
!!!

### LogCorrectScans
=== `boolean`
Should Net2+ log correct scans.

---

Example:
```lua
["LogCorrectScans"] = false
```
===

### LogIncorrectScans
=== `boolean`
Should Net2+ log incorrect scans.

---

Example:
```lua
["LogIncorrectScans"] = false
```
===

### LogButtonPresses
=== `boolean`
Should Net2+ log button presses.

---

Example:
```lua
["LogButtonPresses"] = false
```
===

### LogDoorReleases
=== `boolean`
Should Net2+ log emergency door releases.

---

Example:
```lua
["LogDoorReleases"] = false
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

### GAPI-ResetReleases
=== `boolean`
Should the doors listen to Global API Reset Releases requests?

---

Example:
```lua
["GAPI-ResetReleases"] = false
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

## Miscellaneous Settings

### DisableConsoleOutputs
=== `boolean`
Whether to disable all console outputs from Net2+ or not.

---

Example:
```lua
["DisableConsoleOutputs"] = false
```
===

### CabinetMaximumAngle
=== `number`
How far the Paxton cabinet opens, in degrees.

---

Example:
```lua
["CabinetMaximumAngle"] = -120
```

!!!warning Important notice:
Keep the number **negative**, and below `-5`, as any higher value **will** cause problems.
!!!

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
	9109291923, -- roaxcean
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

### CabinetAuthorisedPeople
=== `{ number }`
A table of Roblox User IDs that are whitelisted to open the Paxton cabinet.

---

Example:
```lua
["CabinetAuthorisedPeople"] = {
	112672616, -- AlexG_1337
	199830788, -- Coco_Beagle
	9109291923, -- roaxcean
} 
```

===

### CabinetAuthorisedGroups
=== `{ [string]: number }`
A dictionary of Roblox Community IDs holding Rank IDs that are whitelisted to open the Paxton cabinet.

---

Example:
```lua
["CabinetAuthorisedGroups"] = {
	["5203509"] = {255}, -- DuckyProductions
	["5150453"] = {255, 254, 253}, -- Whitehill
}
```

===


### DisableCabinetWhitelist
=== `boolean`

Whether to disable the Paxton cabinet whitelist.

---

Example:
```lua
["DisableConsoleOutputs"] = false
```

!!!danger Important Note
This is strictly for demo purposes, and **will allow** anyone to play your doors.
!!!


===

### DoorReleaseAuthorisedPeople
=== `{ number }`
A table of Roblox User IDs that are whitelisted to press the door release button.

---

Example:
```lua
["DoorReleaseAuthorisedPeople"] = {
	112672616, -- AlexG_1337
	199830788, -- Coco_Beagle
	9109291923, -- roaxcean
} 
```

===

### DoorReleaseAuthorisedGroups
=== `{ [string]: number }`
A dictionary of Roblox Community IDs holding Rank IDs that are whitelisted to press the door release button.

---

Example:
```lua
["DoorReleaseAuthorisedGroups"] = {
	["5203509"] = {255}, -- DuckyProductions
	["5150453"] = {255, 254, 253}, -- Whitehill
}
```

===

### DoorBellAuthorisedPeople
=== `{ number }`
A table of Roblox User IDs that are whitelisted to ring the doorbells.

---

Example:
```lua
["DoorBellAuthorisedPeople"] = {
	112672616, -- AlexG_1337
	199830788, -- Coco_Beagle
	9109291923, -- roaxcean
} 
```

===

### DoorBellAuthorisedGroups
=== `{ [string]: number }`
A dictionary of Roblox Community IDs holding Rank IDs that are whitelisted to ring the doorbells.

---

Example:
```lua
["DoorBellAuthorisedGroups"] = {
	["5203509"] = {255}, -- DuckyProductions
	["5150453"] = {255, 254, 253}, -- Whitehill
}
```

===

---


!!!success Configuration Complete!

Not working? Make sure you followed the syntax, or visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.
!!!

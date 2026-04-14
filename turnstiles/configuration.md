# Configuring Your Turnstiles

![](/static/assets/banners/whg_turnstilesconfig.png)

Make them call a lift, or change which card is authorized... Among others!

!!!warning
This page assumes the user has basic knowledge of the Roblox scripting language, Luau.
!!!

---

Your default configuration module, separate for each turnstile, found under `DWProx - KONE Turnstile 100 Single`/`DWProx - KONE Turnstile 100 Multipack` **->** `Settings`, is structured as follows:

```lua 
local Settings = {

	-- / General Settings / --
	["Cards"] = {"1", "2", "3", "4", "5", "0"},
	["OpenTime"] = 5,
	["StartupMode"] = "Normal",
	["ArrowIdleColor"] = "Black",
	["MovementIdentifier"] = 1,

	-- / Lift Call Setings / --
	["LiftLocation"] = nil,
	["LiftCurrentFloor"] = "0",
	
	-- / Lift Directions / --
	["LiftDirections"] = {
		["A"] = "Left",
		["B"] = "Right",
	},

	-- / DO NOT EDIT / --
	["Identifier"] = "\75\84\49\48\48",
	["UnitVersion"] = 1

}
return Settings
```

---

## General Settings

### Cards
=== `{string}`
A list of Card IDs to allow to open the turnstile.

---

Example:
```lua
["Cards"] = {"1", "4", "0"}
```
===

### OpenTime
=== `number`
How long the gate stays open after the card is scanned.

---

Example:
```lua
["OpenTime"] = 5
```
===

### StartupMode
=== `"Normal" | "Lock" | "Exit" | "Entry" | "Hold"`
What mode to apply at turnstile startup.

---

Example:
```lua
["StartupMode"] = "Hold"
```

!!!info
This uses the same modes as the [Turnstiles API](/turnstiles/api.md). Check that for more information.
!!!
===

### ArrowIdleColor
=== `"Black" | "Grey"`
Defines the idle state color of the traffic light arrows when the gate is inactive.

---

Example:

```lua
["ArrowIdleColor"] = "Grey"
```
===

### MovementIdentifier
=== `1 | 2`
Specifies the turnstile movement method:

* `1` — Uses **CFrame Lerp** for smooth animation.
* `2` — Uses **direct CFrame movement**, faster but less smooth.

---

Example:

```lua
["MovementIdentifier"] = 1
```
===

---

## Lift Call Settings

!!!warning
Lift integration is currently **in beta** and may not function 100% of the time.
!!!

### LiftLocation
=== `Instance | nil`
If your turnstile is configured to call lifts, set this to the lift location (e.g. `workspace.Lifts`).
Set to `nil` if no lift should be connected.

---

Example:

```lua
["LiftLocation"] = workspace.Lifts
```
===

### LiftCurrentFloor
=== `string`
Indicates the floor identifier where this turnstile is installed.
Used to determine lift routing logic.

---

Example:

```lua
["LiftCurrentFloor"] = "2"
```
===

---

## Lift Directions

### LiftDirections
=== `{ [string]: "Left" | "Right" | "Left infront" | "Left Up" | "Right infront" | "Right Up" }`
Defines the direction for the turnstiles towards point to when using a lift.

---

Example:

```lua
["LiftDirections"] = {
	["A"] = "Left",
	["B"] = "Right"
}
```
===

---

## Turnstile Controller

Each turnstile has a controller. The code for controller can be changed by accessing  `DWProx - KONE Turnstile 100 Single`/`DWProx - KONE Turnstile 100 Multipack` **->** `TurnstileController` **->** `ControllerCode`. It's structure as following:

```lua
local Code = {

	["AccessCode"] = "1234",

}
return Code
```

### AccessCode
=== `string`
The code that allows users to access the turnstiles control panel.

---

Example:
```lua
["AccessCode"] = "5723"
```
===

---

## Finalizing

Now, using the examples provided, a complete module will look as follows:

```lua
local Settings = {

	-- / General Settings / --
	["Cards"] = {"1", "4", "0"},
	["OpenTime"] = 5,
	["StartupMode"] = "Hold",
	["ArrowIdleColor"] = "Grey",
	["MovementIdentifier"] = 1,

	-- / Lift Call Setings / --
	["LiftLocation"] = workspace.Lifts,
	["LiftCurrentFloor"] = "2",
	
	-- / Lift Directions / --
	["LiftDirections"] = {
		["A"] = "Left",
		["B"] = "Right",
	},

	-- / DO NOT EDIT / --
	["Identifier"] = "\75\84\49\48\48",
	["UnitVersion"] = 1

}
return Settings
```

---

!!!success Configuration Complete!

Not working? Make sure you followed the syntax, or visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.
!!!

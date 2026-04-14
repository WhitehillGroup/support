# Configuring Your AutoPro

![](/static/assets/banners/whg_apconfig.png)

Need your doors open faster? Yes, we have that.

!!!warning
This page assumes the user has basic knowledge of the Roblox scripting language, Luau.
!!!

---

Your default configuration module, found under `AutoPro` **->** `Settings`, is structured as follows:

```lua
--[[    
    ___         __        ____                     ___ 
   /   | __  __/ /_____  / __ \_________     _   _|__ \
  / /| |/ / / / __/ __ \/ /_/ / ___/ __ \   | | / /_/ /
 / ___ / /_/ / /_/ /_/ / ____/ /  / /_/ /   | |/ / __/ 
/_/  |_\__,_/\__/\____/_/   /_/   \____/    |___/____/ 
                                                       
            Whitehill AutoPro Version 2
            
Version 2 brings some new controllers to AutoPro, as well
as upgrades to the existing controllers. It also allows 
the usage of one controller on multiple doors, as well as 
bringing swing and custom doors natively to AutoPro for the 
first time.      
]]--

local Settings = {
	-- / Door Settings / --	
	["StartupMode"] = "Normal",
	["OpenTime"] = 5,
	
	-- / Sliding / --
	["Slide - MovementTime"] = 1.5,
	["Slide - WinterMovementTime"] = 1.5,
	["Slide - DoorEasingStyle"] = Enum.EasingStyle.Quad,
	["Slide - DoorEasingDirection"] = Enum.EasingDirection.InOut,
	
	-- / Swing / --
	["Swing - TargetAngle"] = 85,
	["Swing - OpeningDoorSpeed"] = 1.5,
	["Swing - ClosingDoorSpeed"] = 1.5,
	
	-- / Custom / --
	["Custom - Open"] = function()
		return false
	end,
	["Custom - Close"] = function()
		return false
	end,
	
	-- / Whitelist Settings / --
	["AuthorisedPeople"] = {
		112672616, -- AlexG_1337
		199830788, -- Coco_Beagle
	}, 
	["AuthorisedGroups"] = {
		["5150453"] = {255, 254, 253}, -- Whitehill
	}
}
return Settings
```

---

## General Settings

### StartupMode
=== `"Normal" | "Hold" | "Exit" | "Lock"`
This will be the default mode of the doors upon game start.

What do these mean?
- `Normal`: Automatic door operation, open/closes normally.
- `Hold`: The door will be constantly open.
- `Exit`: Only allows foot traffic to exit, not enter. A one-way mode of operation.
- `Lock`: Doesn't allow any foot traffic. Locked stage.

---

Example:
```lua
["StartupMode"] = "Hold"
```

!!!info
Note: This isn't permanent, you can freely switch between those modes in-game by using the Door Controller.
!!!
===

### OpenTime
=== `number`
Defines how long the door will stay open after opening, after this delay, the door will close.

---

Example:
```lua
["OpenTime"] = 8
```
===

---

## Sliding Doors

### MovementTime
=== `number`
How long will the door take to open/close when **winter mode** is **disabled**.

---

Example:
```lua
["Slide - MovementTime"] = 1
```

===

=== `number`
How long will the door take to open/close when **winter mode** is **enabled**.

---

Example:
```lua
["Slide - WinterMovementTime"] = 1.25
```

===

### DoorEasingStyle
=== `Enum.EasingStyle`

The [Easing Style](https://create.roblox.com/docs/reference/engine/enums/EasingStyle) to apply to the door during movement.

---

Example:
```lua
["Slide - DoorEasingStyle"] = Enum.EasingStyle.Sine
```

!!!
The Roblox Engine Reference doesn't help you understand Easing Styles? Check out [this](https://devforum.roblox.com/t/understanding-easing-styles/937281) DevForum post.
!!!
===

### DoorEasingDirection
=== `Enum.EasingDirection`

The [Easing Style](https://create.roblox.com/docs/reference/engine/enums/EasingDirection) to apply to the door during movement.

---

Example:
```lua
["Slide - DoorEasingDirection"] = Enum.EasingDirection.Out
```
===

---

## Swing Doors

### TargetAngle
=== `number`

How far will the door open in degrees from its default position.

---

Example:
```lua
["Swing - TargetAngle"] = 95
```

### OpeningDoorSpeed
=== `number`

How long will the door take to open fully.

---

Example:
```lua
["Swing - OpeningDoorSpeed"] = 1.25
```
===

### ClosingDoorSpeed
=== `number`

How long will the door take to close fully.

---

Example:
```lua
["Swing - ClosingDoorSpeed"] = 1.75
```
===

---

## Custom Functions

!!!info
This section is entirely skippable if you don't want to add any custom functionality to the doors themselves.
!!!

### Open
=== `() -> ()`
In this function you put **your own** additional functionality to happen when the door **opens**.

--- 

Example:
```lua
["Custom - Open"] = function()
	print(`The door at "{script.Parent:GetFullName()}" has opened!`)
	
	return false
end
```
===

### Close
=== `() -> ()`
In this function you put **your own** additional functionality to happen when the door **closes**.

--- 

Example:
```lua
["Custom - Open"] = function()
	print(`The door at "{script.Parent:GetFullName()}" has closed!`)
	
	return false
end
```
===

---

## Whitelisting

### AuthorisedPeople
=== `{ number }`
A list of [User IDs](https://create.roblox.com/docs/reference/engine/classes/Player#UserId) to allow the use of the controller.

---

Example:
```lua
["AuthorisedPeople"] = {
	123456789, 
	987654321,
} 
```

!!!warning
Users added to this table will be granted permission to **control the doors**. Choose carefully.
!!!

===

### AuthorisedGroups
=== `{ [string]: { number } }`
A dictionary of Community IDs (formerly Group IDs), and their selected Rank IDs, to allow the use of the controller.

---

Example:

```lua
["AuthorisedGroups"] = {
	["123456789"] = {50, 150, 255}
}
```

!!!warning
Ranks (and subsequently users with these ranks) added to this table will be granted permission to **control the doors**. Choose carefully.
!!!

===

---

## Finalizing

Now, using the examples provided, a complete module will look as follows:

```lua
local Settings = {
	-- / Door Settings / --	
	["StartupMode"] = "Hold",
	["OpenTime"] = 8,
	
	-- / Sliding / --
	["Slide - MovementTime"] = 1,
	["Slide - WinterMovementTime"] = 1.25,
	["Slide - DoorEasingStyle"] = Enum.EasingStyle.Sine,
	["Slide - DoorEasingDirection"] = Enum.EasingDirection.Out,
	
	-- / Swing / --
	["Swing - TargetAngle"] = 95,
	["Swing - OpeningDoorSpeed"] = 1.25,
	["Swing - ClosingDoorSpeed"] = 1.75,
	
	-- / Custom / --
	["Custom - Open"] = function()
		print(`The door at "{script.Parent:GetFullName()}" has opened!`)
		
		return false
	end,
	["Custom - Close"] = function()
		print(`The door at "{script.Parent:GetFullName()}" has closed!`)
		
		return false
	end,
	
	-- / Whitelist Settings / --
	["AuthorisedPeople"] = {
		123456789, 
		987654321,
	}, 
	["AuthorisedGroups"] = {
		["123456789"] = {50, 150, 255},
	}
}
return Settings
```

---

!!!success Configuration Complete!

Not working? Make sure you followed the syntax, or visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.
!!!

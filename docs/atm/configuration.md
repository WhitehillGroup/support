---
icon: tools
label: Configuration
order: 95
tags: [Configuration]
image: /static/assets/whg_headbanner.png
authors: 
    - name: everywhxn
      link: https://github.com/everywhxn
      avatar: https://avatars.githubusercontent.com/u/219159259
categories:
  - JSM
  - SelfServ ATM
---
# Configuring Your SelfServ ATM

![](/static/assets/banners/whg_atmconfig.png)

Want to customize your banknotes? This is the place.

!!!warning
This page assumes the user has basic knowledge of the Roblox scripting language, Luau.
!!!

---

Your default configuration module, found under `JSM | ATM V3` **->** `SystemConfig`, is structured as follows:

```lua
--[[ 
	           _______ __  ___
	          / / ___//  |/  /
	     __  / /\__ \/ /|_/ / 
	    / /_/ /___/ / /  / /  
	    \____//____/_/  /_/
 	          ATM v3

System Wide Configuration

]]--
local Settings = {
	-----------------------------------------------------------------
	["Currency"] = "£",
	["ATMCharge"] = nil,
	["CardFlash"] = true,
	["SecurityTimeout"] = 20,
	["Images"] = {
		TennerDecal = {"rbxassetid://5892488849","rbxassetid://5892491132"},
		TwentyDecal = {"rbxassetid://5892492516","rbxassetid://5892493276"},
		FiftyDecal = {"rbxassetid://5892494158","rbxassetid://5892493678"},
	}
	-----------------------------------------------------------------
}
return Settings
```

## General Settings

### Currency
=== `string`
The specified character will be used as a prefix to all monetary values wherever a price is indicated.

---

Example:
```lua
["Currency"] = "€"
```

!!!
Please be advised that this setting is purely cosmetic and does not involve any actual currency conversion.
!!!
===

### ATMCharge
=== `number?` 
This will be the amount that the ATM will charge for withdrawals. Set to `nil` to disable the fee.

---

Example:
```lua
["ATMCharge"] = 0.50
```

!!!warning
Heads up, update your ATM UI to reflect the cost of withdrawals.
!!!
===

### CardFlash
=== `bool`
Should the green light on the card slot flash when idle?

---

Example:
```lua
["CardFlash"] = false
```
===

### SecurityTimeout
=== `number`
Any number given will be the time required for the ATM to classify the interaction as _"Inactive"_ and terminate it automatically.

---

Example:
```lua
["SecurityTimeout"] = 16
```
===

### Images
=== `{ [string]: { string } }`
A dictionary of banknote image asset IDs, used to visually represent the cash denominations dispensed by the ATM.  
Each entry corresponds to a denomination (e.g. £10, £20, £50), and contains a pair of Roblox asset IDs representing the **front** and **back** of the note.


---

Example:
```lua
["Images"] = {
	TennerDecal = {"rbxassetid://123456789","rbxassetid://987654321"},
	TwentyDecal = {"rbxassetid://123456789","rbxassetid://987654321"},
	FiftyDecal = {"rbxassetid://123456789","rbxassetid://987654321"},
}
```

!!!warning
Heads up, remember always to include the `rbxassetid://` part.
!!!

===

---

## Finalizing

Now, using the examples provided, a complete module will look as follows:

```lua
local Settings = {
	["Currency"] = "€",
	["ATMCharge"] = 0.50,
	["CardFlash"] = false,
	["SecurityTimeout"] = 16,
	["Images"] = {
		TennerDecal = {"rbxassetid://123456789","rbxassetid://987654321"},
		TwentyDecal = {"rbxassetid://123456789","rbxassetid://987654321"},
		FiftyDecal = {"rbxassetid://123456789","rbxassetid://987654321"},
	}
}

return Settings
```

---

!!!success Configuration Complete!

Not working? Make sure you followed the syntax, or visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.

!!!

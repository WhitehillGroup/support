# Configuring Your SCO Accounts

![](/static/assets/banners/whg_scoconfig.png)

Welcome to customization heaven.

!!!warning
This page assumes the user has basic knowledge of the Roblox scripting language, Luau.
!!!

---

Your default accounts module, found under `JSM | SelfCheckout V3` **->** `SystemConfig` **->** `Accounts`, is structured as follows:

```lua
--[[
	           _______ __  ___
	          / / ___//  |/  /
	     __  / /\__ \/ /|_/ / 
	    / /_/ /___/ / /  / /  
	    \____//____/_/  /_/
 	      Self Checkout v3

    For additional security, it is recomended to only login with an operator barcode, however passcodes can be used if prefered.
	
]]--

local OperatorID = {		
	["1"] = {
		["Name"] = "DefaultCashier",
		["Type"] = "Employee",
		["Password"] = "1234"
	},	
	["2"] = {
		["Name"] = "DefaultManager",
		["Type"] = "Manager",
		["Password"] = "1234"
	},
	["3"] = {
		["Name"] = "DefaultAdministrator",
		["Type"] = "Administrator",
		["Password"] = "1234"
	},
}
return OperatorID
```

# Syntax

!!!light Access Levels
- `Administrator`: Able to perform all checkout functions,
- `Manager`: Able to close and open lanes, As well as perform all transaction related functions,
- `Employee`: Able to perform all transaction related functions.
!!!

### OperatorID
=== `{ [string]: { [string]: string } }`

The dictionary key (for example, the `"1"`, `"2"`, etc. above) is the ID you will log in with.

!!!light Keys
- `Name`: Name of account, shown when the account number is entered into the keypad,
- `Type`: Access tier (`Employee`, `Manager`, or `Administrator`),
- `Password`: Password for the account.
!!!

---

Example:

```lua
local OperatorID = {
	["4321"] = {
		["Name"] = "Store Employees",
		["Type"] = "Employee",
		["Password"] = "1345"
	},	
	["62"] = {
		["Name"] = "Karen Manager",
		["Type"] = "Manager",
		["Password"] = "7568"
	},
	["387"] = {
		["Name"] = "Maintenance Staff",
		["Type"] = "Administrator",
		["Password"] = "2456"
	},
	["875"] = {
		["Name"] = "Ownership",
		["Type"] = "Administrator",
		["Password"] = "4876"
	},
}
return OperatorID
```

===

---

!!!success Configuration Complete!

Not working? Make sure you followed the syntax, or visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.
!!!

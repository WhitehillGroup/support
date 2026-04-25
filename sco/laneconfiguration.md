# Configuring Your SelfServ Terminal

![](/static/assets/banners/whg_scoconfig.png)

Welcome to a localized customization heaven.

!!!warning
This page assumes the user has basic knowledge of the Roblox scripting language, Luau.
!!!

---

Your lane-specific configuration module, found under `JSM | SelfCheckout V3` **->** `Terminals` **->** Target Terminal **->** `Settings`, is structured as follows:

```lua
--[[ 
	           _______ __  ___
	          / / ___//  |/  /
	     __  / /\__ \/ /|_/ / 
	    / /_/ /___/ / /  / /  
	    \____//____/_/  /_/
 	      Self Checkout v3

Lane-Specific Configuration

Many settings are fetched from system settings ('JSM | SelfCheckout V3' → 'SystemConfig'). These options can be overriden by changing them lane by lane.

The 'CardOnly' setting has no effect on checkouts with no cash processing, or should a compatable ATM system not be found in the game.

]]--
local SysConf = require(script.Parent.Parent.Parent.SystemConfig)
local Settings = {
	-----------------------------------------------------------------
	["LaneNumber"] = 1,
	["CardOnly"] = false,
	["StartMode"] = 1,
	-----------------------------------------------------------------
	["UITheme"] = SysConf.UITheme,
	["CustomThemeLogo"] = SysConf.CustomThemeLogo,
	-----------------------------------------------------------------
	["Currency"] = SysConf.Currency,
	["ContactlessLimit"] = SysConf.ContactlessLimit,
	["InsertCardProximityPrompt"] = SysConf.InsertCardProximityPrompt,
	["PromptForBags"] = SysConf.PromptForBags,
	["CarrierBagCharge"] = SysConf.CarrierBagCharge,
	-----------------------------------------------------------------
	["OperatorID"] = SysConf.OperatorID,
	-----------------------------------------------------------------
	["Maintenance"] = SysConf.Maintenance,
	-----------------------------------------------------------------
	["ReceiptCustomisation"] = SysConf.ReceiptCustomisation,
	-----------------------------------------------------------------
	["Discounts"] = SysConf.Discounts,
	-----------------------------------------------------------------
	["AutomaticIntegrations"] = SysConf.AutomaticIntegrations,
	-----------------------------------------------------------------
	["InGameStaff"] = SysConf.InGameStaff,
	-----------------------------------------------------------------
	["TransactionCompletion"] = SysConf.TransactionCompletion,
	-----------------------------------------------------------------
	["MiscUISettings"] = SysConf.MiscUISettings,
	-----------------------------------------------------------------
	["BarcodeType"] = SysConf["Scan&ShopSettings"].CheckoutSettings.BarcodeType,
	-----------------------------------------------------------------
	["HotkeySettings"] = SysConf.HotkeySettings,
	-----------------------------------------------------------------
}
return Settings
```

---

## Syntax

### LaneNumber
=== `number`
Lane number that the SCO will use.

---

Example:
```lua
["LaneNumber"] = 1
```

!!!danger
This value **must** be unique. Otherwise, the SCO will throw an error.
!!!

===

### CardOnly
=== `boolean`
Should the SCO accept only card/contactless transactions?

---

Example:
```lua
["CardOnly"] = true
```

===

### StartMode
=== `number`
Start-up mode.
Controls how the SCO boots at game start-up:

* `1` — Plays full startup sequence, Lane is automatically open.
* `2` — Plays full startup sequence, Requires a member of staff to open the lane.
* `3` — Doesn't play full startup, Lane is automatically open.
* `4` — System Is off, Requires a member of staff with maintenance permissions open the lane.

---

Example:
```lua
["StartMode"] = 1
```

===

### UITheme
=== `string`
UI Preset to load. Set to `Default` for JSM v3 UI, any other value will load UI from `JSM | UI Template` if found in `ServerStorage`.

---

Example:
```lua
["UITheme"] = SysConf.UITheme
```
===

### CustomThemeLogo
=== `string?`
If set to `nil`, loads default ui associated with theme, either JSM or the theme creator, or loads the image id provided.

---

Example:
```lua
["CustomThemeLogo"] = SysConf.CustomThemeLogo
```

!!!warning
Supply just the ID, without including the `rbxassetid://` part.
!!!
===

### Currency
=== `string`
The specified character will be used as a prefix to all monetary values wherever a price is indicated.

---

Example:
```lua
["Currency"] = SysConf.Currency
```

!!!
Please be advised that this setting is purely cosmetic and does not involve any actual currency conversion.
!!!
===

### ContactlessLimit
=== `number`
Contactless payment upper limit. Transactions worth more than the set value won't be able to be paid via contactless.

---

Example:
```lua
["ContactlessLimit"] = SysConf.ContactlessLimit
```
===

### InsertCardProximityPrompt
=== `boolean`
Whether to insert a [Proximity Prompt](https://create.roblox.com/docs/reference/engine/classes/ProximityPrompt) into the card reader instead of a [Click Detector](https://create.roblox.com/docs/reference/engine/classes/ClickDetector).

---

Example:
```lua
["InsertCardProximityPrompt"] = SysConf.InsertCardProximityPrompt
```
===

### PromptForBags
=== `boolean`
Whether to prompt for shopping bags before going to the payment screen.

---

Example:
```lua
["PromptForBags"] = SysConf.PromptForBags
```

!!!
This is a purely cosmetic setting, and will not actually give any bags to the user.
!!!
===

### CarrierBagCharge
=== `float`
Price per one shopping bag. (If enabled.)

---

Example:
```lua
["CarrierBagCharge"] = SysConf.CarrierBagCharge
```
===

### OperatorID
=== `{ [string]: any }`
Operator ID settings, see the [SCO Configuration](/sco/configuration/#operatorid) page for more information.

---

Example:
```lua
["OperatorID"] = SysConf.OperatorID
```
===

### Maintenance
=== `{ [string]: any }`
Maintenance settings, see the [SCO Configuration](/sco/configuration/#maintenance) page for more information.

---

Example:
```lua
["Maintenance"] = SysConf.Maintenance
```
===

### ReceiptCustomisation
=== `{ [string]: any }`
Receipt customisation settings, see the [SCO Configuration](/sco/configuration/#receiptcustomisation) page for more information.

---

Example:
```lua
["ReceiptCustomisation"] = SysConf.ReceiptCustomisation
```
===

### Discounts

!!!warning
This feature is not available yet.
!!!

### AutomaticIntegrations
=== `any`
Automatic integrations settings, see the [SCO Configuration](/sco/configuration/#automaticintegrations) page for more information.

---

Example:
```lua
["AutomaticIntegrations"] = SysConf.AutomaticIntegrations
```
===

### InGameStaff
=== `{ [string]: any }`
In-game staff settings, see the [SCO Configuration](/sco/configuration/#ingamestaff) page for more information.

---

Example:
```lua
["InGameStaff"] = SysConf.InGameStaff
```
===

### TransactionCompletion
=== `{ [string]: any }`
Transaction completion settings, see the [SCO Configuration](/sco/configuration/#transactioncompletion) page for more information.

---

Example:
```lua
["TransactionCompletion"] = SysConf.TransactionCompletion
```
===

### MiscUISettings
=== `{ [string]: any }`
Miscellaneous UI settings, see the [SCO Configuration](/sco/configuration/#miscuisettings) page for more information.

---

Example:
```lua
["MiscUISettings"] = SysConf.MiscUISettings
```
===

### BarcodeType
=== `number`
S&S Transfer code, see the [SCO Configuration](/sco/configuration/#barcodetype) page for more information.

---

Example:
```lua
["BarcodeType"] = SysConf["Scan&ShopSettings"].CheckoutSettings.BarcodeType
```
===

### HotkeySettings

!!!warning
This feature is not available yet.
!!!

---

!!!success Configuration Complete!

Not working? Make sure you followed the syntax, or visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.
!!!

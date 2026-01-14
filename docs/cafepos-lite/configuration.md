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
categories:
  - JSM
  - SelfServ SCO
---
# Configuring Your SelfServ SCO

![](/static/assets/banners/whg_scoconfig.png)

Welcome to customization heaven.

!!!warning
This page assumes the user has basic knowledge of the Roblox scripting language, Luau.
!!!

---

Your default configuration module, found under `JSM | SelfCheckout V3` **->** `SystemConfig`, is structured as follows:

```lua
--[[ 
	           _______ __  ___
	          / / ___//  |/  /
	     __  / /\__ \/ /|_/ / 
	    / /_/ /___/ / /  / /  
	    \____//____/_/  /_/
 	      Self Checkout v3
 	      © Whitehill Group
 	      
System Wide Configuration

Configure lane specific settings within each terminal.
Configure accounts in the "Accounts" script.

]]--
local Settings = { 
	-----------------------------------------------------------------
	["UITheme"] = "Default", 
	["CustomThemeLogo"] = nil,
	-----------------------------------------------------------------
	["Currency"] = "£",
	["JSMATMLocation"] = workspace["JSM | ATM V3"],
	["ContactlessLimit"] = 100,
	["InsertCardProximityPrompt"] = false, 
	["PromptForBags"] = true,
	["CarrierBagCharge"] = 0.05,
	-----------------------------------------------------------------
	["OperatorID"] = {
		["Enabled"] = false,
		["ShowPlayerWhenLoggedIn"] = true,
	},
	-----------------------------------------------------------------
	["Maintenance"] = { -- 
		["MaintenanceHatch-Users"] = { 
			112672616, -- Example (AlexG_1337)
			199830788, -- Example (Coco_Beagle)
			9109291923, -- Example (roaxcean)
		},
		["MaintenanceHatch-Groups"] = {
			["5150453"] = {255, 254, 253}, -- Example (Whitehill)
		},
		["DisableMaintenanceHatchWhitelist"] = false,
	},
	-----------------------------------------------------------------
	["ReceiptCustomisation"] = {
		["Enabled"] = true,
		["Heading"] = "JSM Self Checkout",
		["Subheading"] = "Customer Receipt",
		["Footer"] = "Thank you for shopping with us!",
		["PaperConsumption"] = 100,
	},
	-----------------------------------------------------------------
	["AutomaticIntegrations"] = {
		["Whitehill_RankCache"] = nil,
		["Applegate_VoCoVo"] = false,
		["Kybo_Walvo"] = true,
		
		["AllowPayWithPhoneAPI"] = false,
	},
	-----------------------------------------------------------------
	["InGameStaff"] = {
		["Enabled"] = false,
		["StaffUsers"] = { 
			112672616, -- Example (AlexG_1337)
			199830788, -- Example (Coco_Beagle)
			9109291923, -- Example (roaxcean)
		},
		["StaffGroups"] = { 
			["5150453"] = {255, 254, 253}, -- Example (Whitehill)
		},
		["StaffThreshold"] = 3,
	},
	-----------------------------------------------------------------
	["TransactionCompletion"] = {
		["DisableEAS"] = true,
		["AdditionalRemoval"] = { 
			"RandomEventTest",
		},
	},
	-----------------------------------------------------------------
	["MiscUISettings"] = {
		["StartCardOnlyMessage"] = "<b>Card Only</b>  No Coins/Notes Accepted",
		["StartCashOnlyMessage"] = "<b>Cash Only</b>  No Debit/Credit Cards Accepted",
		["StartNormMessage"] = "<b>Card</b> and <b>Cash</b> Payments Accepted",
		["TakeItemsMessage"] = "Please take your items",
		["RememberMessage"] = "Don't forget your receipt",
		["RememberMessageCash"] = "Don't forget your change & receipt",
		["FinishMessage"] = "Thanks for using this JSM Self Checkout",
		["PayButtonTotal"] = false,
		["DefaultUIAnimations"] = true,
	},
	-----------------------------------------------------------------
	["RemoteAttendantSettings"] = {
		-- Not Functional
	},
	-----------------------------------------------------------------
	["Scan&ShopSettings"] = {
		["TerminalSettings"] = {
			["IdleMessage"] = "Welcome to JSM Scan & Shop.",
			["WelcomeMessage"] = "Welcome to JSM Scan & Shop.",
			["AutoRelease"] = true,
			["ReleaseTimeout"] = 10,
			["LowHandsetWarning"] = 5,
			["ShowBoot"] = false, 
		},
		["HandsetSettings"] = {
			["WelcomeScreen"] = true,
			["ShowCurrency"] = true, 
			["ItemLimit"] = 200,
			["FinishMessage"] = "Thanks for using JSM Scan & Shop.", 
		},
		["CheckoutSettings"] = {
			["BarcodeType"] = 2,
		},
		["AutoReturn"] = true, 		
		["AllowExternal"] = false,
	},
	-----------------------------------------------------------------
	["HotkeySettings"] = {
		-- Not Functional
	},
	-----------------------------------------------------------------
}
return Settings
```

---

## Syntax

### UITheme
=== `string`
UI Preset to load. Set to `Default` for JSM v3 UI, any other value will load UI from `JSM | UI Template` if found in `ServerStorage`.

---

Example:
```lua
["UITheme"] = "SomeCustomUI"
```
===

### CustomThemeLogo
=== `string?`
If set to `nil`, loads default ui associated with theme, either JSM or the theme creator, or loads the image id provided.

---

Example:
```lua
["CustomThemeLogo"] = "123456789"
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
["Currency"] = "€"
```

!!!
Please be advised that this setting is purely cosmetic and does not involve any actual currency conversion.
!!!
===

### JSMATMLocation
=== `Folder`
Where the JSM ATM v3 Folder is located. Set to `nil` if not using.

---

Example:
```lua
["JSMATMLocation"] = workspace["JSM | ATM V3"]
```

!!!
This enables the Self Checkouts to use currency as payment options. Otherwise, only contactless/card options will be available. 
!!!
===

### ContactlessLimit
=== `number`
Contactless payment upper limit. Transactions worth more than the set value won't be able to be paid via contactless.

---

Example:
```lua
["ContactlessLimit"] = 250
```
===

### InsertCardProximityPrompt
=== `bool`
Whether to insert a [Proximity Prompt](https://create.roblox.com/docs/reference/engine/classes/ProximityPrompt) into the card reader instead of a [Click Detector](https://create.roblox.com/docs/reference/engine/classes/ClickDetector).

---

Example:
```lua
["InsertCardProximityPrompt"] = true
```
===

### PromptForBags
=== `bool`
Whether to prompt for shopping bags before going to the payment screen.

---

Example:
```lua
["PromptForBags"] = true
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
["CarrierBagCharge"] = 0.01
```
===

---

## OperatorID
!!!info
For additional security, it is recommended to only log in with an operator barcode.
!!!

### Enabled
=== `bool`
Whether pins should be enabled.

---

Example:

```lua
["Enabled"] = false
```

===

### ShowPlayerWhenLoggedIn
=== `bool`
Whether to show the player name instead of account name. 
If logged in with operator barcode player will be shown instead of account name, in all other situations account name is shown.

---

Example:

```lua
["ShowPlayerWhenLoggedIn"] = true
```

===

#### Example Section:
```lua
["OperatorID"] = {
	["Enabled"] = false,
	["ShowPlayerWhenLoggedIn"] = true,
}
```

---

## Maintenance

### MaintenanceHatch-Users
=== `{ number }`
A table of Roblox User IDs that are whitelisted to open the Maintenance Hatch.

---

Example:

```lua
["MaintenanceHatch-Users"] = { 
	112672616, -- Example (AlexG_1337)
	199830788, -- Example (Coco_Beagle)
	9109291923, -- Example (roaxcean)
}
```

===

### MaintenanceHatch-Groups
=== `{ [string]: number }`
A dictionary of Roblox Community IDs holding Rank IDs that are whitelisted to open the Maintenance Hatch.

---

Example:

```lua
["MaintenanceHatch-Groups"] = {
	["5150453"] = {255, 254, 253}, -- Example (Whitehill)
}
```

===

### DisableMaintenanceHatchWhitelist
=== `bool`
Whether to disable the Maintenance Hatch whitelist.

---

Example:

```lua
["DisableMaintenanceHatchWhitelist"] = false
```

!!!warning
This setting is intended to demonstration purposes only. Disabling the whitelist will enable all users to open the hatch, and reboot your checkouts.
!!!

===

#### Example Section:

```lua
["Maintenance"] = {
	["MaintenanceHatch-Users"] = { 
		112672616, -- Example (AlexG_1337)
		199830788, -- Example (Coco_Beagle)
		9109291923, -- Example (roaxcean)
	},
	["MaintenanceHatch-Groups"] = {
		["5150453"] = {255, 254, 253}, -- Example (Whitehill)
	},
	["DisableMaintenanceHatchWhitelist"] = false,
}
```

---

## ReceiptCustomisation

### Enabled
=== `bool`
Whether to enable receipt printing or not.

---

Example:

```lua
["Enabled"] = true
```
===

### Heading
=== `string`
Top text on the receipt.

---

Example:

```lua
["Heading"] = "JSM Self Checkout"
```
===

### Subheading
=== `string`
Subtitle below the heading text.

---

Example:

```lua
["Subheading"] = "Customer Receipt"
```
===

### Footer
=== `string`
The bottom-most text.

---

Example:

```lua
["Footer"] = "Thank you for shopping with us!"
```
===

### PaperConsumption
=== `number`
Consumption of printer paper.
- `0` - No consumption.
- `>0` - How many receipts per roll.

---

Example:

```lua
["PaperConsumption"] = 100
```

!!!warning
This feature is not available yet.
!!!
===

#### Example Section:

```lua 
["ReceiptCustomisation"] = {
	["Enabled"] = true,
	["Heading"] = "JSM Self Checkout",
    ["Subheading"] = "Customer Receipt",
	["Footer"] = "Thank you for shopping with us!",
	["PaperConsumption"] = 100,
}
```

---

## AutomaticIntegrations

### Whitehill_RankCache
=== `ModuleScript`
Location of the Whitehill RankCache library (if installed), set to `nil` if not being used.

---

Example:

```lua
["Whitehill_RankCache"] = nil
```
===

### Applegate_VoCoVo
=== `bool`
Whether using the Applegate VoCoVo for Self Checkout notifications.

---

Example:

```lua
["Applegate_VoCoVo"] = false
```
===

### Kybo_Walvo
=== `bool`
Whether using the Kybo Walvo for Self Checkout notifications.

---

Example:

```lua
["Kybo_Walvo"] = true
```
===

### AllowPayWithPhoneAPI
=== `bool`
Integration with external payment devices.

---

Example:

```lua
["AllowPayWithPhoneAPI"] = false
```

!!!warning
This feature is not available yet.
!!!
===

#### Example Section:

```lua
["AutomaticIntegrations"] = {
	["Whitehill_RankCache"] = nil,
	["Applegate_VoCoVo"] = false,
	["Kybo_Walvo"] = true,
	
	["AllowPayWithPhoneAPI"] = false,
}
```

---

## InGameStaff

### Enabled
=== `bool`
Whether the in-game staff availability system is active.

---

Example:

```lua
["Enabled"] = false
```

===

### StaffUsers
=== `{ number }`
A table of Roblox User IDs considered as staff for intervention handling.

---

Example:

```lua
["StaffUsers"] = {
	112672616, -- Example (AlexG_1337)
	199830788, -- Example (Coco_Beagle)
	9109291923, -- Example (roaxcean)
}
```

===

### StaffGroups
=== `{ [string]: number }`
A dictionary mapping group IDs to one or more staff ranks.

---

Example:

```lua
["StaffGroups"] = {
    ["5150453"] = {255, 254, 253}, -- Example (Whitehill)
}
```

===

### StaffThreshold
=== `number`
Minimum number of staff members required in-game to support intervention workflows.

---

Example:

```lua
["StaffThreshold"] = 3
```

===

#### Example Section:
```lua
["InGameStaff"] = {
	["Enabled"] = false,
	["StaffUsers"] = { 
		112672616, -- Example (AlexG_1337)
		199830788, -- Example (Coco_Beagle)
		9109291923, -- Example (roaxcean)
	},
	["StaffGroups"] = { 
    	["5150453"] = {255, 254, 253}, -- Example (Whitehill)
	},
	["StaffThreshold"] = 3,
}
```

---

# TransactionCompletion

### DisableEAS
=== `bool`
Determines whether EAS tags should be automatically deactivated on tools when a transaction is completed.

---

Example:

```lua
["DisableEAS"] = true
```

===

### AdditionalRemoval

=== `{ string }`
A list of instance names to remove from the tool's `Handle` upon transaction finalization.

---

Example:

```lua
["AdditionalRemoval"] = {
    "RandomEventTest",
}
```

===

#### Example Section:

```lua
["TransactionCompletion"] = {
	["DisableEAS"] = true,
	["AdditionalRemoval"] = {
		"RandomEventTest",
	},
}
```

---

## MiscUISettings

### StartCardOnlyMessage
=== `string`
Displayed on the welcome screen when the lane is configured for card-only transactions.

---

### StartCashOnlyMessage
=== `string`
Displayed when the lane only accepts cash.

---

### StartNormMessage
=== `string`
Displayed in standard operation (cash + card).

---

### TakeItemsMessage
=== `string`
Message shown on the final screen reminding customers to take their items.

---

### RememberMessage
=== `string`
Reminder to take receipts in card-only and mixed-payment modes.

---

### RememberMessageCash
=== `string`
Reminder to take both change and receipt when cash was used.

---

### FinishMessage
=== `string`
Finish message displayed when the transaction completes.

---

### PayButtonTotal
=== `bool`
If `true`, the Pay button shows the total transaction price.
If `false`, it displays "Finish & Pay".

---

### DefaultUIAnimations
=== `bool`
When enabled, some parts of the UI will be animated.

!!!
This only works on the default UI.
!!!

===

#### Example Section:
```lua
["MiscUISettings"] = {
	["StartCardOnlyMessage"] = "<b>Card Only</b>  No Coins/Notes Accepted",
	["StartCashOnlyMessage"] = "<b>Cash Only</b>  No Debit/Credit Cards Accepted",
	["StartNormMessage"] = "<b>Card</b> and <b>Cash</b> Payments Accepted",
	["TakeItemsMessage"] = "Please take your items",
	["RememberMessage"] = "Don't forget your receipt",
	["RememberMessageCash"] = "Don't forget your change & receipt",
	["FinishMessage"] = "Thanks for using this JSM Self Checkout",
	["PayButtonTotal"] = false,
	["DefaultUIAnimations"] = true,
}
```

---

## RemoteAttendantSettings

!!!warning
This feature is not available yet.
!!!

---

## Scan&ShopSettings

!!!warning
Note: These settings apply **only** if Scan & Shop is installed.
!!!

=== **TerminalSettings**

### IdleMessage
=== `string`
Shown when the terminal is idle.

---

### WelcomeMessage
=== `string`
Displayed when a customer begins a Scan & Shop session.

---

### AutoRelease
=== `bool`
If `true`, handsets are dispensed automatically. If `false`, the customer must manually remove one.

---

### ReleaseTimeout
=== `number`
Time (seconds) the system waits before retracting the handset if not taken.

---

### LowHandsetWarning
=== `number`
Threshold of remaining handsets before a low-inventory warning is triggered.

---

### ShowBoot
=== `bool`
If `true`, the terminal displays a boot animation on startup.
===

---

=== **HandsetSettings**

### WelcomeScreen
=== `bool`
Determines whether a welcome screen appears when the handset initializes.

---

### ShowCurrency
=== `bool`
Shows or hides the currency symbol on handset UI.

---

### ItemLimit
=== `number`
Maximum number of scannable items before the handset automatically clears excess entries.

---

### FinishMessage
=== `string`
Displayed when the handset transfers the transaction to the checkout.
===

---

=== **CheckoutSettings**

### BarcodeType
=== `number`
Controls how barcodes are handled at checkout:

* `0` — No barcode; S&S disabled
* `1` — Physical barcode
* `2` — Physical barcode + UI message
* `3` — Physical barcode + UI message (S&S only)
* `4` — Digital barcode
* `5` — Digital barcode (S&S only)

===

---

### AutoReturn

=== `bool`
If enabled, handsets automatically return to the terminal after transfer.

===

### AllowExternal

=== `bool`
Whether third-party handsets may connect. Disabled by default for security.

===

---

#### Example Section:

```lua
["Scan&ShopSettings"] = {
	["TerminalSettings"] = {
		["IdleMessage"] = "Welcome to JSM Scan & Shop.",
		["WelcomeMessage"] = "Welcome to JSM Scan & Shop.",
		["AutoRelease"] = true,
		["ReleaseTimeout"] = 10,
		["LowHandsetWarning"] = 5,
		["ShowBoot"] = false, 
	},
	["HandsetSettings"] = {
		["WelcomeScreen"] = true,
		["ShowCurrency"] = true, 
		["ItemLimit"] = 200,
		["FinishMessage"] = "Thanks for using JSM Scan & Shop.", 
	},
	["CheckoutSettings"] = {
		["BarcodeType"] = 2,
	},
	["AutoReturn"] = true, 		
	["AllowExternal"] = false,
}
```

---

## HotkeySettings

!!!warning
This feature is not available yet.
!!!

---

!!!success Configuration Complete!

Not working? Make sure you followed the syntax, or visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.
!!!

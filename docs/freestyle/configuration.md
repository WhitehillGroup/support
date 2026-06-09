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
  - Freestyle
---
# Configuring Your Freestyle

![](/static/assets/banners/whg_freestyleconfig.png)

Changing the drinks up? Welcome to the flavour alley.

!!!info
This product is in BETA, everything is subject to change.
!!!
!!!warning
This page assumes the user has basic knowledge of the Roblox scripting language, Luau.
!!!

---

Your default configuration module, found under `JSM | Freestyle Drinks Machine` **->** `Controller` **->** `DrinkData`, is structured as follows:

```lua
local Data = {
	Drink1 = {
		DisplayName = "Coca Cola",
		MainColor = Color3.fromRGB(30,18,0),
		Flavours = {
			{
				DisplayName = "Original",
				ImageID = "97592497897008",
				Color = Color3.fromRGB(30,18,0)
			},
			{
				DisplayName = "Cherry",
				ImageID = "116619151335335",
				Color = Color3.fromRGB(255, 47, 68)
			},
			{
				DisplayName = "Cherry Vanilla",
				ImageID = "76896014820725",
				Color = Color3.fromRGB(255, 60, 118)
			},
			{
				DisplayName = "Lemon",
				ImageID = "105537006678100",
				Color = Color3.fromRGB(138, 145, 0)
			},
			{
				DisplayName = "Lime",
				ImageID = "104122755321328",
				Color = Color3.fromRGB(0, 145, 0)
			},
			{
				DisplayName = "Orange",
				ImageID = "87611829023008",
				Color = Color3.fromRGB(255, 85, 0)
			},
			{
				DisplayName = "Vanilla",
				ImageID = "91132261309340",
				Color = Color3.fromRGB(212, 144, 99)
			},
			{
				DisplayName = "Peach",
				ImageID = "104860694394159",
				Color = Color3.fromRGB(212, 144, 99)
			}
		}
	},
	Drink2 = {
		DisplayName = "Coke Zero",
		MainColor = Color3.fromRGB(30,18,0),
		Flavours = {
            -- Same as above. (Truncated)
		}
	},
	Drink3 = {
		DisplayName = "Diet Coke",
		MainColor = Color3.fromRGB(30,18,0),
		Flavours = {
            -- Same as above. (Truncated)
		}
	},
	Drink4 = {
		DisplayName = "Dr Pepper",
		MainColor = Color3.fromRGB(30,18,0),
		Flavours = {
            -- Same as above. (Truncated)
		}
	},
	Drink5 = {
		DisplayName = "Fanta",
		MainColor = Color3.fromRGB(200,133,0),
		Flavours = {
            -- Same as above. (Truncated)
		}
	},
	Drink6 = {
		DisplayName = "Fanta Zero",
		MainColor = Color3.fromRGB(200,133,0),
		Flavours = {
            -- Same as above. (Truncated)
		}
	},
	Drink7 = {
		DisplayName = "Sprite",
		MainColor = Color3.fromRGB(156,156,156),
		Flavours = {
            -- Same as above. (Truncated)
		}
	},
	Drink8 = {
		DisplayName = "Sprite Zero",
		MainColor = Color3.fromRGB(156,156,156),
		Flavours = {
            -- Same as above. (Truncated)
		}
	}
}
return Data
```

---

## General Settings

### DrinkX
=== `table`
Each drink entry represents a primary beverage option on the machine.  
The machine currently supports only a limited amount of drinks. (`Dink1` - `Drink8`)

A drink entry contains:

- **DisplayName** — `string`  
  The name that will appear on the machine UI.

- **MainColor** — `Color3`  
  The core color theme for the drink’s branding.

- **Flavours** — `{ table }`  
  An array of flavour definitions.  
  Each flavour includes:
    - `DisplayName` — `string`
    - `ImageID` — `string` *(numeric string — without `rbxassetid://` prefix)*
    - `Color` — `Color3`

---

Example block:
```lua
Drink1 = {
	DisplayName = "Example Soda",
	MainColor = Color3.fromRGB(120, 55, 200),
	Flavours = {
		{
			DisplayName = "Original",
			ImageID = "12345678901234",
			Color = Color3.fromRGB(120, 55, 200)
		},
		{
			DisplayName = "Cherry",
			ImageID = "56789012345678",
			Color = Color3.fromRGB(255, 47, 68)
		}
	}
}
```

===

### DisplayName

=== `string`
This will be the user-facing name for the drink or flavour.

---

Example:

```lua
DisplayName = "Cherry"
```

===

### MainColor / Color

=== `Color3`
Defines UI tinting for the drink or flavour.
Use [`Color3`](https://create.roblox.com/docs/reference/engine/datatypes/Color3) values only.

---

Example:

```lua
MainColor = Color3.fromRGB(255,85,0)
```

===

### ImageID

=== `string`
A raw asset ID string used internally by the machine.
Do **not** prefix with `rbxassetid://` — the system handles this automatically.

---

Example:

```lua
ImageID = "12345678901234"
```

!!!warning
Invalid or empty image IDs will break flavour selection thumbnails.
!!!
===

---

## Finalizing

Now, using the examples provided, a complete module will look as follows:

```lua 
local Data = {
	Drink1 = {
		DisplayName = "Example Soda",
		MainColor = Color3.fromRGB(120, 55, 200),
		Flavours = {
			{
				DisplayName = "Original",
				ImageID = "12345678901234",
				Color = Color3.fromRGB(120, 55, 200)
			},
			{
				DisplayName = "Cherry",
				ImageID = "56789012345678",
				Color = Color3.fromRGB(255, 47, 68)
			}
		}
	},

	Drink2 = {
		DisplayName = "Berry Blast",
		MainColor = Color3.fromRGB(99, 0, 148),
		Flavours = {
			{
				DisplayName = "Original",
				ImageID = "98765432100987",
				Color = Color3.fromRGB(99, 0, 148)
			},
			{
				DisplayName = "Raspberry",
				ImageID = "14725836912478",
				Color = Color3.fromRGB(255, 60, 118)
			}
		}
	}
	
	-- And so on. (Truncated)
}

return Data
```

---

!!!success Configuration Complete!

Not working? Make sure you followed the syntax, or visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.

!!!

P---
icon: tools
label: Configuration
order: 95
tags: [Configuration]
image: /static/assets/whg_headbanner.png
authors: 
    - name: louis_vx
      link: https://github.com/louis-vx
      avatar: https://avatars.githubusercontent.com/u/193327234?v=4
categories:
  - JSM
  - CafePOS
  - Lite
---
# Configuring Your CafePOS Lite

![](/static/assets/banners/whg_cafeposlite.png)

!!!alert
All configuration information is from a YouTube video by AlexG_1337 and may be outdated as the video was published in 2022.
!!!

!!!warning
This page assumes the user has basic knowledge of the Roblox scripting language, Luau.
!!!

---

Your default configuration module, found under `JSM | CafePOS-Lite Terminal` **->** `Settings`, is structured as follows:

```lua
--[[ 
	           _______ __  ___
	          / / ___//  |/  /
	     __  / /\__ \/ /|_/ / 
	    / /_/ /___/ / /  / /  
	    \____//____/_/  /_/
 	      CafePOSLite - The Basic POS
 	     For Any Cafe
-------------------------------
]]local CafePOSLite = {
   --------------------------------MainSettings--------------------------------
   ["TillNo"] = 1, -- Till Number
   ["OEM"] = "Demo Cafe", -- Put yozr group name here or a ship name something like Costa or Tesco Cafe.
   --------------------------------HRCallStuff--------------------------------
   ["HRCall"] = true, -- If the HR Call button should be on by default.
   ["DisableNotifications"] = false, --Disables built-in notifications. (good if you only want to use custom actions.)
   ["Group"] = 5150453 -- What group HRCall will check for.
   ["MinimumRank"] = 250, -- What rank HRCall will check for.
   ["CustomActions"] = function() -- CustomActions for the call hr button.
   end
}return CafePOSLite
-------------------------------->Guide To Tools<--------------------------------
--Inside of this settings script you will see 3 bindable functions.
--Put CafePoSLiteAdmin inside an operator card.
--Put CafePOSLiteLogin inside a staff card so they can login.
--Put CafePOSLiteltem inside anything the tills are allowed to scan.
-------------------------------->EXTRA<--------------------------------
--If you dont have a card to use feel free to use a dwprox paxton card.
--just remove the ui off the paxton card.
--I have a tutorial on how to set this up please watch

```

---

## Syntax
---

### TillNo
=== `number`
Enter the POS terminal number. Usually required for the HR call.

---

Example:
```lua
["TillNo"] = 1,
```

!!!alert
Setting this is recommended. (I have no information on whether POS will not work with two or more identical Till IDs.)
!!!
===

### OEM
=== `string`
The name of the cafe that is displayed on the log-in display or in the lower menu bar.

---

Example:
```lua
["OEM"] = "Costa",
```
===

### HR Call
=== `string`
Set this to your preference: whether the HR call should be active by default or deactivated.

---

Example:
```lua
["HRCall"] = true,
```

---

### Default Notifications
=== `number`
Enable this for normal Roblox Core notifications. Disabling is recommended for custom actions.

---

Example:
```lua
["DisableNotifications"] = true,
```

## HR Call Group
=== `number`
Set this to the group that should receive the message or action during an HR call.

---

Example:
```lua
 ["Group"] = 5150453
```

## HR Call Group Rank
=== `number`
Set this to the minimum group rank that should receive the message or action during an HR call.

---

Example:
```lua
 ["MinimumRank"] = 250,
```

---

## Custom Call Actions
=== `string?`
Custom call actions such as an Applegate VoCoVo message via the VoCoVo API.

---

Example:
```lua
["CustomActions"] = function()
    local tillNumber = CafePOSLite.TillNo

    game.ReplicatedStorage.VocovoAPI:Fire(
        "CustomMessage",
        "Till " .. tillNumber .. " requested assistance from HR. Please respond.",
        "HR Call | Till " .. tillNumber,
        "", -- Image or Decal ID (VoCoVo converts automatically)
        "", -- Sound ID
        "AssistReq"
    )
end
```
!!!warning
This example is provided for demonstration purposes only.

A valid VoCoVo Go license issued by the Applegate Centre is required for this functionality to work.

Additionally, the VoCoVo model must be present and correctly configured within the game.
Without the model, the API call will fail.
!!!

===

!!!success Configuration Complete!

Not working? Make sure you followed the syntax, or visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.

!!!warning
CafePOS Lite is outdated, and support is unlikely to be able to help.

Do you know of any bugs or new configuration options in recent updates? Send them to <@1222929536392630309> on Discord.
!!!

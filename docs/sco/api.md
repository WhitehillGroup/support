---
icon: code
label: API
order: 85
tags: [API]
image: /static/assets/whg_headbanner.png
authors:
  - name: everywhxn
    link: https://github.com/everywhxn
    avatar: https://avatars.githubusercontent.com/u/219159259
categories:
  - JSM
  - SelfServ SCO
---
# SelfCheckout API

![](/static/assets/banners/whg_scoapi.png)

What are the SCOs up to now?

!!!info
This is a technical page, and assumes familiarity with Roblox Studio's Explorer, alongside with Roblox's scripting language, Luau.
!!!

!!!warning
Support **will not** be given on the SCO API usage, you're entirely on your own.
!!!

---

Our Self Checkouts represent Whitehill's latest advancement in Self-Checkout technology. This page provides an overview of the `NetworkEvent` [BindableEvent](https://create.roblox.com/docs/reference/engine/classes/BindableEvent), and go over the `JSM-ExternalAPI` [BindableFunction](https://create.roblox.com/docs/reference/engine/classes/BindableFunction) as well as `JSM-BankIntegration` [BindableFunction](https://create.roblox.com/docs/reference/engine/classes/BindableFunction).

## NetworkEvent

Located directly in the root directory of the JSM Self Checkout, it is the primary way the checkout report their states, changes, and so on.

The most basic script to get to know what the checkouts are up to is:
```lua
local NetworkEvent = script.Parent;

NetworkEvent.Event:Connect(function (Sender: string, LaneNumber: number, Command: string, Argument: any): ()
	print("JSM:", Sender, LaneNumber, Command, Argument);
end);
```

This will spit out all the data that is sent to the NetworkEvent, assuming the script is placed under it.

=== The usual schema of it is as follows:
- **Sender**: (`string`) The object sending the command, mostly "RemoteTerminal" for SCO events.
- **LaneNumber**: (`number`) Lane number of the object sending the event.
- **Command**: (`string`) Command to fulfill or action that was taken.
- **Argument**: (`any`) Anything, from numbers, to tables, and strings.
===

---

## JSM-ExternalAPI

Located in the `Integrations` Folder, the ExternalAPI is only used to interface with the Scan & Shop.

!!!warning
For this to work, you need to set `AllowExternal` to `true` in your `SystemConfig` module (see [Configuration](/sco/configuration.md) for more info), otherwise the checkout will refuse to process your request.
!!!

The syntax is as follows:
```lua
workspace["JSM | SelfCheckout V3"].Integrations["JSM-ExternalAPI"]:Invoke(LaneNumber, Protocol, OEMInfo, ProductTable)
```
!!!light What do these mean?
- **LaneNumber**: (`number`) The checkout lane to target.
- **Protocol**: (`string`) Keep it as `"SAYSData"`, otherwise will refuse the request.
- **OEMInfo**: (`string`) Your company/game name.
- **ProductTable**: (`{ Tool }`) A list of `Tool`s to send to the checkout.
!!!

=== Example:
```lua
["JSM-ExternalAPI"]:Invoke(1, "SAYSData", "Whitehill", {Tool1, Tool2, Tool3})
```
===
Where `Tool1`, `Tool2`, and `Tool3` are scannable JSM SCO product tools.

!!!
Something to keep in mind: The checkout **will move** the tools you pass to its own storage during the transaction, and then pass them to the `Player` who completes the transaction. It's worth to keep in mind that, if you plan on making a script to automatically pass item(s) to the checkout (etc.), always keep clones of the tools.
!!!

---

## JSM-BankIntegration

Located in the `Integrations` Folder, the BankIntegration is used for checking the users balance, allowing you to integrate the SCOs into existing banking systems.

!!!
**Note:** It's not you to invoke this BindableFunction, the Checkouts will do it when processing contactless/card payments.
!!!

A barebones example is as follows:
```lua
workspace["JSM | SelfCheckout V3"].Integrations["JSM-BankIntegration"].OnInvoke = function (Player: player, Amount: number): (bool)
    -- Implement balance checks here.
    
    return true
end
```
!!!light What do these mean?
- **Player**: (`player`) The player we need to check.
- **Amount**: (`number`) Payment price.
!!!

!!!info What does it expect?
- **If you `return true`:** The checkout will proceed with the transaction.
- **If you `return false`:** It will deny the transaction.
!!!


---

## Locale

Located in each SCO Terminal, the Locale is used for controlling the TriLight(s). 

```lua
workspace["JSM | SelfCheckout V3"].Terminals["JSM | SeflServ 7350"].Locale.Event:Connect(function (Protocol: string, Action: string): ()
    warn(Protocol, Action);
end);
```

!!!light What do these mean?
- **Protocol**: (`string`) The protocol to be used.
- **Action**: (`string`) Action to take, ie: change TriLight colour.

!!!

---

!!!tip

Something's unclear? Visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.

!!!

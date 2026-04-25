---
icon: code
label: API
order: 85
tags: [API]
image: /static/assets/whg_headbanner.png
authors: 
    - name: roaxcean
      link: https://github.com/roaxcean
      avatar: https://avatars.githubusercontent.com/u/219159259
categories:
  - JSM
  - SelfServ ATM
---
# ATM API

![](/static/assets/banners/whg_atmapi.png)

I can feel the cash flowing though the code.

!!!info
This is a technical page, and assumes familiarity with Roblox Studio's Explorer, alongside with Roblox's scripting language, Luau.
!!!

---

SelfServ ATM is our best companion ATM for the SelfServ SCO, a must for every shopkeeper.

Located directly in the Integrations folder, the Bank Intergration allows you to interface easily with the ATMs.

## Syntax

```lua
workspace["JSM | ATM V3"].Integrations["JSM-BankIntegration"].OnInvoke = function (Request: string, User: player, Amount: number): (bool | number)
	if Request == "withdraw" then
		return true -- returns if the payment should be accepted
	elseif Request == "balance" then
		return math.random(100,1000) -- returns the amount that the user has
	end
end
```
!!!light What do these mean?
- **Request**: (`string`) The player we need to check.
- **Player**: (`player`) The player we need to check.
- **Amount**: (`number`) Payment price.
  !!!

!!!info What does it expect?
For `withdraw`:
- **If you `return true`:** The ATM will proceed with the withdraw.
- **If you `return false`:** It will deny the withdraw.

For `balance`:
- Return a `number` value which will be displayed to the user as their balance.
!!!

---

!!!tip

Something's unclear? Visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.

!!!

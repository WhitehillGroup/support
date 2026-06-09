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
  - Whitehill
  - DWProx
  - KONE Turnstiles
---
# KONE Turnstiles API

![](/static/assets/banners/whg_turnstilesapi.png)

Can you lock the turnstiles? After the alarm goes off? And easily? Yes, yes, and yes!

!!!info
This is a technical page, and assumes familiarity with Roblox Studio's Explorer, alongside with Roblox's scripting language, Luau.
!!!

---

Located directly in the root folder **after game startup**, the API allows you to interface relatively easily with the turnstiles, making script automation possible, and you won't have to strictly rely on Access Cards.

## Syntax

```lua
workspace["DWProx - KONE Turnstile 100 Single"].API:Fire(Event)
```
!!!light What do these mean?
**Event**: (`string`) Function for the turnstile to execute.
!!!
Turnstiles's function list is as follows:
- `"Normal"`: Normal mode of operation. Accepts card scans from both sides.
- `"Lock"`: Denies every card scan from both sides.
- `"Exit"`: Denies every card scan from the "entry" side, making the gate exit-only.
- `"Entry"`: Denies every card scan from the "exit" side, making the gate entry-only.
- `"Hold"`: The gate is constantly open, allowing for free entry/exit.

!!!info Note
Each turnstile has **its own API**. The 100 Single is used as an example model, but this syntax applies to all turnstiles.
!!!

---

!!!tip

Something's unclear? Visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.

!!!

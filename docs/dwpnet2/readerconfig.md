---
icon: tools
label: Reader Configuration
order: 95
tags: [Configuration]
image: /static/assets/whg_headbanner.png
authors:
  - name: Dunbars123
    link: https://github.com/michaeldun123
    avatar: https://avatars.githubusercontent.com/u/42805814
categories:
  - Whitehill
  - DWProx
  - Net2+
---
# Configuring Your Net2+ Readers

![](/static/assets/banners/whg_net2config.png)

Welcome to customization heaven. (#3)

!!!warning
This page assumes the user has basic knowledge of the Roblox scripting language, Luau.
!!!

---

## Reader Settings

### Cards
=== `{ number }`
A table of Access Levels that are whitelisted to use the reader **At Any Time**.

---

Example:
```lua
["Cards"] = {"1", "2", "3", "4", "5", "0"},
```

===

### WhitelistEnabled
=== `boolean`

Whether to enable or disable the reader whitelist.

---

Example:
```lua
["WhitelistEnabled"] = false,
```


===

---

!!!success Configuration Complete!

Not working? Make sure you followed the syntax, or visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.
!!!

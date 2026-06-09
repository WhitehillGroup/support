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
  - Scan & Shop
---
# Scan & Shop API

![](/static/assets/banners/whg_sasapi.png)

Wait... Scan and Shop API?

!!!info
This is a technical page, and assumes familiarity with Roblox Studio's Explorer, alongside with Roblox's scripting language, Luau.
!!!

---

## Locale

Located in each Terminal, the Locale is used for controlling the TriLight(s), as well as returning handsets. 

```lua
workspace["JSM | SelfCheckout V3"].Accessories["JSM | Scan & Shop"]["JSM | S&S Terminal"].Locale.Event:Connect(function (Protocol: string, Action: string): ()
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

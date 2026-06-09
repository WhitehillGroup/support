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
  - AutoPro
---
# AutoPro API

![](/static/assets/banners/whg_apapi.png)

Make the doors open by themselves. Or don't.

!!!info
This is a technical page, and assumes familiarity with Roblox Studio's Explorer, alongside with Roblox's scripting language, Luau.
!!!

---

AutoPro is our most advanced automatic door system designed for convenience and efficiency, providing seamless access control for any environment. Each AutoPro instance has a singular `API` [BindableFunction](https://create.roblox.com/docs/reference/engine/classes/BindableFunction).

Located directly in the root folder after **game startup**, the API allows you to interface easily with the doors.

## Syntax

```lua
workspace["AutoPro v2"]:WaitForChild("API"):Invoke(Protocol, Event)
```
!!!light What do these mean?
- **Protocol**: (`string`) This will always be "api".
- **Event**: (`string`) Function for AutoPro to execute.
!!!
AutoPro's function list is as follows:
- `"Open"`: Used to open the door. _(Door Mode "Normal" or "Exit")_
- `"ReaderOpen"`: For use with access control. _(Door Mode "Locked" or "Exit")_
- `"ReaderClose"`: For use with access control. _(Door Mode "Locked" or "Exit")_

!!!info Note
Changing the mode of operation is only available via the door controller. You can change the start-up mode by following steps in the AutoPro [configuration](/autopro/configuration.md) guide.
!!!

---

!!!tip

Something's unclear? Visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.

!!!

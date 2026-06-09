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
  - Intelli-Sense EAS
---
# Intelli-Sense EAS API

![](/static/assets/banners/whg_easapi.png)

Beep-beep-beep, who stole something!?

!!!info
This is a technical page, and assumes familiarity with Roblox Studio's Explorer, alongside with Roblox's scripting language, Luau.
!!!

---

JSM EAS exposes a simple API for you to interact with, or get the data it's sending. The EAS has a single `Node` [BindableEvent](https://create.roblox.com/docs/reference/engine/classes/BindableEvent).

## Syntax

### Receiving

```lua
workspace["JSM | Intelli-Sense EAS"].Node.Event:Connect(function(eventType: string, source: string, zone: number, player: Player): ()
	print(player.Name, "triggered a", source, "in zone", tostring(zone));
end);
```

EAS supports scripts that listen to events, and will fire them everytime it's triggered.

!!!light What do these mean?
- **eventType**: (`string`) This will always be "ALARM".
- **source**: (`string`) Source location, will always be "Sensor" if coming from JSM EAS.
- **zone**: (`number`) Zone number as set in the Sensor.
- **player**: (`Player`) Player who triggered the event (shoplifting.)
!!!

---

### Sending

```lua
workspace["JSM | Intelli-Sense EAS"].Node.Event:Fire(eventType, source, zone, player);
```

Alternatively, EAS also supports listening to events, allowing you to use external scripts to trigger it manually.

!!!light What do these mean?
- **eventType**: (`string`) This will always be "ALARM".
- **source**: (`string`) Source location, set to anything you like.
- **zone**: (`number`) Zone number to trigger.
- **player**: (`Player`) Player to set as the triggering person.
!!!

---

!!!tip

Something's unclear? Visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.

!!!

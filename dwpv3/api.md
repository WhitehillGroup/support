# DWProx V3 API

![](/static/assets/banners/whg_v3api.png)

Control madness? Check.

!!!info
This is a technical page, and assumes familiarity with Roblox Studio's Explorer, alongside with Roblox's scripting language, Luau.
!!!

---

DWProx V3 is our most advanced Access Control System, a system like this needs a robust API, so we made one.
This page goes over the `DWProxGAPI` [BindableEvent](https://create.roblox.com/docs/reference/engine/classes/BindableEvent) (Global API) 
and `DWPROXAPI` [BindableFunction](https://create.roblox.com/docs/reference/engine/classes/BindableFunction) (Local/Per-Door API; yes, in all-caps).

## DWProxGAPI

Located directly in [Replicated Storage](https://create.roblox.com/docs/reference/engine/classes/ReplicatedStorage) 
**after game start-up**, the Global API controls all V3 doors.

!!!warning
For this to work, you need to **enable GAPI settings** inside the per-door configuration module. (See [Configuration](/dwpnet2/configuration.md) for more information.)
!!!

The syntax is as follows:

```lua
game["ReplicatedStorage"].DWProxGAPI:Fire(Function, Argument)
```
!!!light What do these mean?
- **Function**: (`string`) Function for all doors to execute.
- **Argument**: (`any?`) Any additional parameters.
!!!

GAPI's function list is as follows:
- `"FIRE"`: Fire detected mode. _(Expects a boolean as Argument)_
- `"LOCK"`: Locks all doors. _(Expects a boolean as Argument)_
- `"HOLD"`: Keeps all doors open. _(Expects a boolean as Argument)_
- `"RESETRELEASES"`: Resets all releases.
- `"OPEN"`: Opens all doors. _(Expects a number as Argument, for how long keep the doors open.)_

!!!info
If no argument is provided, it'll toggle the API. Or in case of `"OPEN"`, it'll use the default time set in per-door configuration module.
!!!

=== Example:
```lua
game["ReplicatedStorage"].DWProxGAPI:Fire("OPEN", 16)
```
===

---

## DWPROXAPI

Each V3 door has its own `DWPROXAPI` **after game start-up**, or Local API ("LAPI"), used to control the door. The LAPI is identical to the GAPI in terms of functionality.

```lua
["DWProx"].DWPROXAPI:Invoke(Function, Argument)
```
!!!light What do these mean?
- **Function**: (`string`) Function for all doors to execute.
- **Argument**: (`any?`) Any additional parameters.
  !!!

LAPI's function list is as follows:
- `"FIRE"`: Fire detected mode. _(Expects a boolean as Argument)_
- `"LOCK"`: Locks all doors. _(Expects a boolean as Argument)_
- `"HOLD"`: Keeps all doors open. _(Expects a boolean as Argument)_
- `"RESETRELEASES"`: Resets all releases.
- `"OPEN"`: Opens all doors. _(Expects a number as Argument, for how long keep the doors open.)_

!!!info
If no argument is provided, it'll toggle the API. Or in case of `"OPEN"`, it'll use the default time set in per-door configuration module.
!!!

=== Example:
```lua
["DWProx"].DWPROXAPI:Invoke("FIRE", true)
```
===

---

!!!tip

Something's unclear? Visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.

!!!

---
icon: check-circle
label: Updating
order: 90
tags: [Updating]
image: /static/assets/whg_headbanner.png
authors:
  - name: everywhxn
    link: https://github.com/everywhxn
    avatar: https://avatars.githubusercontent.com/u/219159259
categories:
  - Whitehill
  - AutoPro
---
# Updating Your AutoPro

![](/static/assets/banners/whg_apupdate.png)

Keep your doors opening, keep them updated.

!!!
Before getting started, download the latest version of this product from [Axon](https://axon.whitehill.group).
!!!
!!!warning
This page assumes familiarity with Roblox Studio's Explorer and basic model hierarchy manipulation.
!!!

---

=== Step 1 - Preparations
- Duplicate your `AutoPro V2` model and store it outside your workspace.

In case anything goes south, you will always have a restore point.
===

=== Step 2 - Updating
Main System:
- From the fresh copy of AutoPro, copy the `AutoProV2` script. (Inside `AutoPro V2` **->** `Settings`)
- In your existing installation, delete the old `AutoProV2` script, and paste in the new `AutoProV2` script.

Controller:
- From the fresh copy of AutoPro, locate the same controller _(Whitehill BDE Controller/Whitehill BDE-Lite Controller)_ that you're trying to update, and copy the `WHL-BDE`/`WHL-BDEL` _(respectively)_ script.
- In your existing controller, delete the old `WHL-BDE`/`WHL-BDEL` script, and paste in the new script.

!!!warning
It's important to take the new script from the same controller as your existing one, as mixing the script with a different controller **will** cause issues.
!!!
===

=== Step 3 - Test
After updating, confirm that the AutoPro boots and functions without throwing any errors to the Console.

!!!
In case any errors occur, check the release notes in [**#product-updates**](https://ptb.discord.com/channels/616745092279173151/1169430975911043212) for any special instructions.
!!!
===

---

!!!success Updating Complete!
Your AutoPro has been updated, not working? Visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.
!!!

---
icon: check-circle
label: Updating
order: 75
tags: [Updating]
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
# Updating Your KONE Turnstiles

![](/static/assets/banners/whg_turnstilesupdate.png)

Keep Turnstiles turning.

!!!
Before getting started, download the latest version of this product from [Axon](https://axon.whitehill.group).
!!!
!!!warning
This page assumes familiarity with Roblox Studio's Explorer and basic model hierarchy manipulation.
!!!

---

=== Step 1 - Preparations
- Duplicate your Turnstiles and store them outside your workspace.

In case anything goes south, you will always have a restore point.
===

=== Step 2 - Updating
!!!
As of 17/08/26 the `Loader` script in Turnstiles has been replaced by `KT-Script`.
If updating an older Turnstiles installation, replace `Loader` script with the new `KT-Script`.
!!!

- From a fresh copy of Turnstiles, under each turnstile there's a `KT-Script` script, copy it.
- For every Turnstile, follow the same path, and replace the old `KT-Script` script with the new `KT-Script`.

!!!warning
Turnstiles don't have a deployment/global script. All Turnstiles **need to be updated manually**.
!!!
===

=== Step 3 - Test
After updating all/one of the Turnstiles, test if it boots and functions without throwing any errors to the Console.

!!!
In case any errors occur, check the release notes in [**#product-updates**](https://ptb.discord.com/channels/616745092279173151/1169430975911043212) for any special instructions.
!!!
===

---

!!!success Updating Complete!
Your Turnstiles have been updated. Doesn't work? Visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.
!!!

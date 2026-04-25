---
icon: package
label: Adding Products
order: 96
tags: [Products]
image: /static/assets/whg_headbanner.png
authors: 
    - name: raadtotheraad
      link: https://github.com/raadtotheraad
      avatar: https://avatars.githubusercontent.com/u/149825178
categories:
  - JSM
  - SelfServ SCO
---

# Add Products to your SCO

![](/static/assets/banners/whg_scoproducts.png)

Mmm... scanning...

!!! Tip
We recommend the usage of the Whitehill Tool Configurator Plugin [here](https://create.roblox.com/store/asset/96844493449121). If you use the plugin, the process is fairly straightforward.
!!!
!!!warning
This page assumes familiarity with Roblox Studio's Explorer and basic model hierarchy manipulation.
!!!

---

=== Step 1 - Add the example Tools
Download and import the example Tools from [Axon](https://axon.whitehill.group). You will find an Operator Login Card, a Debit Card and an example Product.

To import your file, simply drag the product file into Roblox Studio once your game is fully loaded.
Alternatively, you can use the Explorer context menu by right-clicking and selecting **Insert > Insert From File**.
===

=== Step 2 - Get the Item Data
Go to the example Product and find a BindableFunction named ``JSM | Item Data``. Inside of the BindableFunction, you will find Attributes. The Attributes are:
- **AgeRestricted**: (``boolean``) Determine if the Product is Age Restricted and if the SCO will need Assistance to continue.
- **Cost**: (``number``) How much the Product should cost when scanned.
- **EASActive**: (``boolean``) If the JSM EAS should alarm if the Product hasn't been paid for yet.
- **ItemImage**: (``string``) The Decal the SCO should show when scanned. Use ``rbxassetid://0``, where ``0`` is the Asset ID of the Decal.
- **LoyaltyCost**: (``number``) How much the Product should cost if a Loyalty Card has been scanned.
- **PaidFor**: (``boolean``) Whether or not the item was already paid for.

You can customize these to your liking.
===

=== Step 3 - Add the BindableFunction
Add the BindableFunction as a child to the Tool of your Product. Once that is done, you can try scanning your Product with your SCO.
===

!!!success Done!
Now your Products should be able to function with your SCO. Doesn't work? Visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.
!!!

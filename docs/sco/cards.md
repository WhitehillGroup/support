---
icon: note
label: Adding Cards
order: 95
tags: [Cards]
image: /static/assets/whg_headbanner.png
authors: 
    - name: raadtotheraad
      link: https://github.com/raadtotheraad
      avatar: https://avatars.githubusercontent.com/u/149825178
categories:
  - JSM
  - SelfServ SCO
---

# Add Cards to your SCO

![](/static/assets/banners/whg_scocards.png)

Even more scanning, but for staff.
Or you're paying..?
Or you're a loyal member???

!!! Tip
We recommend the usage of the Whitehill Tool Configurator Plugin [here](https://create.roblox.com/store/asset/96844493449121). If you use the plugin, the process is fairly straightforward.
!!!
!!!warning
This page assumes familiarity with Roblox Studio's Explorer and basic model hierarchy manipulation.
!!!

---

=== Add the example Tools
Download and import the example Tools from [Axon](https://axon.whitehill.group). You will find an Operator Login Card, a Debit Card and an example Product.

To import your file, simply drag the product file into Roblox Studio once your game is fully loaded.
Alternatively, you can use the Explorer context menu by right-clicking and selecting **Insert > Insert From File**.
===

This is a global step for all three card types.

---

## Operator Login Cards

=== Step 1 - Get the Barcode Data
Go to the Operator Login Card tool and find a BindableFunction named ``JSM | Operator Barcode``. Inside of the BindableFunction, you will find an Attribute.

**AccountID**: (``number``) The account ID the tool should be registered with. You can make different barcodes for each ID.

!!! Not sure what an account ID is?
Go to the [Accounts Page](/sco/accounts.md). You will find more about it there.
!!!
===

=== Step 2 - Add the BindableFunction
Add the BindableFunction as a child to the Tool of your Card. Once that is done, you can try scanning your Card with your SCO.
===

---

## Debit Cards

=== Step 1 - Get the Debit Card Data
Go to the Debit Card tool and find a BindableFunction named ``JSM | Debit Card``.
===

=== Step 2 - Add the BindableFunction
Add the BindableFunction as a child to the Tool of your Card. Once that is done, you can try scanning your Card with your SCO.
===

---

## Loyalty Cards

=== Step 1 - Get the Loyalty Card Data
Go to the Loyalty Card tool and find a BindableFunction named ``JSM | Loyalty Card``.
===

=== Step 2 - Add the BindableFunction
Add the BindableFunction as a child to the Tool of your Card. Once that is done, you can try scanning your Card with your SCO.
===

!!!success Done!
Now your Cards should be able to function with your SCO. Doesn't work? Visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.
!!!
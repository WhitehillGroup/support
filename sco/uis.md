# Add a Custom UI to your SCO

![](/static/assets/banners/whg_scoui.png)

"Sorry, nope, doesn't fit the company theme."

!!!warning
This page assumes familiarity with creating UI's on Roblox Studio and how they function. Furthermore expected is familiarity with Roblox Studio's Explorer and basic model hierarchy manipulation.
!!!

---

=== Step 1 - Add the Custom UI Template

Download and import the custom UI Template or advanced custom UI Template from [Axon](https://axon.whitehill.group). You will find a ``Frame`` inside a Folder named ``JSM | UI Template`` which includes everything you can edit in the SCO UI.

To import your file, simply drag the product file into Roblox Studio once your game is fully loaded.
Alternatively, you can use the Explorer context menu by right-clicking and selecting **Insert > Insert From File**.

!!!danger
If using the **advanced custom UI Template**, support will not be provided to you by Whitehill.
It is all at your own risk.
!!!

!!! Not sure at which custom UI Template to pick?
If you are willing to go as far as editing the intervention popups on your SCO, you can download the advanced custom UI Template.

If it is outside of your comfort zone, you can pick the (normal) custom UI Template.

Use of the advanced custom UI Template is recommended for people with more skills in UI Editing.
!!!

===

=== Step 2 - Edit to your liking

Edit the custom UI Template you chose as much as you like.

Make sure to keep the names, children, parents, objects etc. so the UI doesn't break.

You can set the ``Visible`` option to ``true`` and ``false`` from time to time to view the UI you're currently editing.

!!!danger
Only edit the UI Elements you are allowed to edit!

It is recommended to only use the UI Template(s) provided to you by Whitehill to prevent editing a UI Element which you aren't allowed to edit.

For more information on UI restrictions for JSM/Whitehill products, please refer to the [Terms of Use](../terms.md).
!!!

===

=== Step 3 - Apply the custom UI
Once you are done, move the Folder named ``JSM | UI Template`` into ``ServerStorage``.

Finally, go into the SCO Configuration and set the ``UITheme`` to ``Custom``.

Alternatively, you can set the Folder to any name you'd like and set the ``UITheme`` configuration to the name of your Folder.
(Example: Your Folder with the UI is named ``MySCOUI``. Set the ``UiTheme`` in your SCO Configuration to ``MySCOUI``.)

===

---

!!!success Done!
Now your custom UI should be able to function with your SCO. Doesn't work? Visit our [FAQ Page](/faq.md) for help, or contact Whitehill Support via our [Discord server](https://discord.whitehill.group/) for further assistance.
!!!

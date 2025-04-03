---
title: Saving Your Map
tags: 
keywords: 
last_updated: 
summary: 
sidebar: mydoc_sidebar
permalink: 08_map_functionality.html
---

In order to make your map playable, there are basically two steps:
1. "Create Map" (formerly whitelisting)
2. Map Publishing (private/public)

These two are both done from the Map Manager, which can be accessed within TRIA.os from the main menu.

{% include image.html file ="08_1.jpg" alt="" caption=""%}

Additionally, if you want players to be able to gain awards from beating your map, you must go through the process of **Map Verification**.

## Creating a Map (whitelisting)
This step is required in order to begin testing your map, and this process adds your map to an internal TRIA database, which exists to help TRIA staff moderate maps violating Roblox Terms of Service.

To start, save your map model (in this case, probably just the map kit) and set it to **on sale**, which is necessary for TRIA to obtain your map.

{% include image.html file ="08_2.png" alt="" caption=""%}

From the Map Manager, go to `Create Map` and enter the asset ID of the model you just set on sale. Press enter, and a new map slot should be created, containing the name of the map along with a **short ID**.As the map owner, you're able to use the asset ID to load the map in game. However, anyone else will need to use the short ID.

Once the map is created, you may take the model off sale. To update the map, simply update the map model.

## Map Publishing
Once your map is complete, it's time to publish it, which is necessary to begin the verification process and for the map to appear in the Map List. To do this, click `Publish Map`, and as long as the map meets all the publishing requirements, it'll show up in `Published Maps`. The requirements include, but aren't limited to:
- Name must be 30 characters or less
- Must have a valid difficulty
- You must own the map model
- Account must be verified and at least 30 days old
- Map must be a model
- Unique name
- Unique map image
- Must used optimized structure (essentially the Special folder)
- Must be under 50k instances- for reference, Nos Astra has 49k, so it is highly unlikely you'll run into this one

Go back to `Published Maps`. When you first publish a map, it starts off as private, meaning it isn't visible on the map list. You can toggle it to public and vice versa. 

{% include image.html file ="08_3.jpg" alt="" caption=""%}

The `Manage Creators` menu allows you to add any additional creators to the map, which lets them appear as a creator when loading the map and lets them recieve any map donations.

Note that once you've published a map, the published version (accessible when loading from the map list) will not update even when you update the map model, hence the `Publish Update` button. If a map was previously verified (indicated by the blue icon), publishing an update will cause it to go back to the **Unverified** status (orange icon).

## Map Verification
Map Verification has many benefits for your map. It allows your map to be loaded in **Verified servers**, and it allows players to gain **XP** and **Medal** rewards when beating the map in said Verified server. Verified maps get their own filter in the Map List, and in general, the system ensures that your map is possible to complete and works properly without breaking the game.

Currently the system is in active development. The only way to get a map verified is to join the TRIA discord server and run `/submit_map` inside a channel like `#bot`, which will submit the map for verification. The command comes with three arguments:

- Map ID 
- A link to a verification video with either you or anyone you choose beating the map
- (OPTIONAL) A file containing a license for audio verification

Once your map is submitted, it should take a week or so for the map to become Verified or be rejected.
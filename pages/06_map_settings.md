---
title: Map Settings
tags: 
keywords: 
last_updated: 
summary: 
sidebar: mydoc_sidebar
permalink: 06_map_settings.html
---

The settings are divided into many different sections; let’s go over the ones we haven’t covered yet.

## Main Settings
{% include image.html file ="06_1.png" alt="" caption=""%}

The main settings contain, well, all the main things about your map: name, description, image ID for your map thumbnail, max time in seconds (after which all players who haven’t beaten the map are killed, you can set this up to 10 minutes), and map difficulty number. There are 7 main difficulties:

1. Easy
2. Normal
3. Hard
4. Insane
5. Extreme
6. Divine
7. Eternal

## Music
{% include image.html file ="06_2.png" alt="" caption=""%}

To set the music for your map, make sure there's a `Sound` instance under `Settings` containing the `SoundId` of the desired soundtrack.

If the soundtrack you want to use is not provided by Roblox's standard music library, you'll have to make sure your song is in [TRIA's music library](https://discord.com/channels/565208753914249256/951813104486973490). Steps for audio verification can be found in the TRIA discord server under [audio-verification](https://discord.com/channels/565208753914249256/1047094425911828490).

## Lighting
Lighting settings contain attributes which correspond to different Lighting properties, such as Ambient, Brightness, and the map’s Time of Day. You can also put objects such as Skyboxes, ColorCorrection, and Atmosphere under the Lighting folder, and these will be inserted into the game along with your map. You can modify lighting settings during a round using the TRIA.os Lighting feature.

## Materials
The materials settings allows you to switch between Roblox’s new, 2022 materials or continue using the older ones, which TRIA.os uses by default. You can also insert MaterialVariants into the Materials folder if you want to use custom PBR materials.

## Skills
The skills folder allows you to toggle various abilities, or ‘skills’. 

By default, TRIA comes with two skills, Sliding and Air Diving, which can be toggled individually both in this folder or via scripting. 

You can also toggle the type of sliding your map uses, either Linear sliding or non-linear sliding, which essentially acts as a speedboost ability with a cooldown, allowing you to do much longer jumps.

## UI
{% include image.html file ="06_6.png" alt="" caption=""%}

If your map contains any on-screen UI elements, you can put them here.
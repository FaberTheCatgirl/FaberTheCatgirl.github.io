---
title: CREATION AND POPULATION OF A FULLY FUNCTIONAL SMART-TERRAIN
permalink: /docs/xray/engines/CoP/Guides/Level_Design/smart_terrain_creation/
---

CREATION AND POPULATION OF A FULLY FUNCTIONAL SMART-TERRAIN

In this tutorial, we'll be establishing a stalker base with weapon restrictions, weapon cleaning facilities, emission zones, NPC immortality zones, sleep zones, actor teleportation points, exclusive tasks for NPCs, and unique NPC roles (trader, medic, technician, leader, a specific NPC providing quests). Additionally, we'll set up a base for an opposing faction.

All of these actions will take place in the swamp location from the "Clear Sky" game.

To begin, register your smart-terrains in the game_graphs.ltx file located at the following path: x_ray_sdk\editors\gamedata\configs

Here are the names I've assigned to my smart-terrains for bases and simulation:

153 = "mar_sta_base" - Stalker base
154 = "mar_st1" - for simulation and defense
155 = "mar_st2" - for simulation and defense
156 = "mar_st3" - for simulation and defense
157 = "mar_base_bandit" - Bandit base
158 = "mar_ba1" - for simulation and defense
159 = "mar_ba2" - for simulation and defense
160 = "mar_ba3" - for simulation and defense

Refer to the screenshot for further clarification.

<p align="center">
<img src="/assets/img/ref1.png">
</p>

Next, these smart-terrain names must be added to the same file, but this time within your mod's game directory folder.

After entering the smart-terrain names, save the file, launch the level editor, and open the location you intend to work on.

For instance, I open the swamp location (marsh). In the "Spawn" element section, choose the (AI) option, click on the smart-terrain using the "Add" function, and place it in the location, specifically at the center of the stalker base. This ensures that the base is accurately displayed at the center of the map.

Enter the smart terrain name: mar_sta_base.

In the custom data section, provide a reference to the logic file for this smart-terrain.

[story_object]
story_id = mar_sta_base
[smart_terrain]
cfg = scripts\marsh\smart\mar_sta_base.ltx

Also, set the NOT Restrictor.

Refer to the screenshot for clarification.

<p align="center">
<img src="/assets/img/ref2.png">
</p>

Proceed by positioning a graph point at the center of the smart-terrain, assign it the name "mar_graph_point," and link it to the smart-terrain.

Make sure to establish the connection in section number 4.

Refer to the screenshot for visual guidance.

<p align="center">
<img src="/assets/img/ref3.png">
</p>

Having established the smart-terrain and graph point, the next step is to strategically place additional simple graph points throughout the base area. Create a restrictor and extend its dimensions significantly to cover the entire base and its surrounding territory. Provide it with the name:

Name: mar_sta_base_sr_no_assault

Additionally, configure it as a NOT Restrictor.

Refer to the screenshot for visual assistance.

<p align="center">
<img src="/assets/img/ref4.png">
</p>

Let's implement a restrictor that disarms the actor upon entry. Create a cube-shaped restrictor, adjusting its size and height to cover the area of the stalker base. Assign the name:

Name: mar_sta_base_sr_noweap

Custom data:
[story_object]
story_id = mar_sta_base_sr_noweap

[logic]
cfg = scripts\marsh\mar_sta_base_sr_noweap.ltx

Additionally, designate it as the "In Default" restrictor.

Refer to the screenshot for further clarification.

<p align="center">
<img src="/assets/img/ref5.png">
</p>

Now, let's create another restrictor and configure it to function as an emission zone. Provide it with the name:

Name: mar_surge_hide_b1

Ensure it is set as a NON-Default restrictor.

Refer to the screenshot for visual guidance.

<p align="center">
<img src="/assets/img/ref6.png">
</p>

While the first emission zone has been successfully established, considering the numerous buildings within the base, creating a single, large zone seems impractical. Emission zones are typically configured within buildings or tunnels rather than outdoors. Let's proceed to create three additional zones with the following names:

mar_surge_hide_b2
mar_surge_hide_b3
mar_surge_hide_b4

Ensure that all of these are configured as NON-Default restrictors.

I've positioned four emission zones within a single base, strategically placing them in areas where the leader, technician, trader, and medic are stationed.

Refer to the screenshot for reference.

<p align="center">
<img src="/assets/img/ref7.png">
</p>

ATTENTION: In case you encounter an error while creating a restrictor, please consult the screenshot.

<p align="center">
<img src="/assets/img/ref8.png">
</p>

In case you are following the steps correctly and encounter this error, approach the shape closely with the camera and click the mouse on the corner of the shape. This action will create the restrictor. Refer to the screenshot for visual assistance.

<p align="center">
<img src="/assets/img/ref9.png">
</p>

Now, add a restrictor with dimensions resembling the weapon cleaning zone and give it a name:

Name: mar_sta_base_sr_light

Custom data:
[logic]
cfg = scripts\marsh\mar_sta_base_sr_light.ltx

Additionally, configure it as a NON-Default restrictor.

Refer to the screenshot for visual guidance.

<p align="center">
<img src="/assets/img/ref10.png">
</p>

This restrictor deactivates flashlights for NPCs sitting by the campfire or standing at the bar counter during the night, where there is illumination, etc.

Now, let's establish camp zones for socializing, sharing jokes, dining, drinking, and warming up by the campfire in good company.

In the spawn element section, select the camp option and place it in areas with campfires, bar counters, or generally communal spaces.

For my base, I've designated three camp zones and named them:

mar_sta_base_camp_1
mar_sta_base_camp_2
mar_sta_base_camp_3
In the custom data of each smart-terrain, include a reference to the logic file.

[camp]
cfg = scripts\camp.ltx

Additionally, ensure they are set as NOT Restrictors.

Refer to the screenshot for visual guidance.

<p align="center">
<img src="/assets/img/ref11.png">
</p>

Proceed to set up as many camp zones as required, and remember to number them accordingly.

<p align="center">
<img src="/assets/img/ref12.png">
</p>

Next, establish a restrictor for the sleep zone. Use the camera to locate an appropriate sleeping area, position the restrictor, and expand it vertically above the actor's height and horizontally to fully encompass the actor. Assign the name:

Name: mar_sta_base_sr_sleep

Custom data:
[story_object]
story_id = mar_sta_base_sr_sleep_id

[logic]
cfg = scripts\sr_sleep.ltx

Additionally, ensure it is configured as a NOT Restrictor.

Refer to the screenshot for visual guidance.

<p align="center">
<img src="/assets/img/ref13.png">
</p>

Now, install a small restrictor to indicate the base on the global map, positioning it at the center of the base.

Name: mar_sta_base_spot

Custom data:
[story_object]
story_id = mar_sta_base_spot

Additionally, configure it as a NOT Restrictor.

Refer to the screenshot for visual guidance.

<p align="center">
<img src="/assets/img/ref14.png">
</p>

Now, strategically position smart-covers across the base area for simulation squads that will be directed to these smart points.

Start with the first smart-cover and name it:

Name: mar_sta_base_animpoint_1

Choose the animation, for example, standing at the bar counter, or according to your preference. Remember to uncheck the boxes in the "is combat cover" and "can fire" sections.

Refer to the screenshot for visual guidance.

<p align="center">
<img src="/assets/img/ref15.png">
</p>

Now, let's strategically position these in areas where there are camp zones by the campfire or simply within the base territory.

Install the second one and configure it similarly to the first, choosing the appropriate animation and assigning a name.

Name: mar_sta_base_animpoint_2

Continue this process, adhering to the numbering sequence: 3, 4, 5, and so forth. For a large base, it's recommended to use a sufficient number of smart-covers. This ensures that when the simulation squad arrives, the workspaces are occupied, and they default to sitting, looking down, standing with their weapons piled up, or huddling in a corner.

Here's a list of my smart-covers, and I'll be adding even more.

<p align="center">
<img src="/assets/img/ref16.png">
</p>
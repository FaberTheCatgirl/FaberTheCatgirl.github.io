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

'''[story_object]'''
'''story_id = mar_sta_base'''
'''[smart_terrain]'''
'''cfg = scripts\marsh\smart\mar_sta_base.ltx'''

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


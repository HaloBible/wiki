---
layout: default
title: Sandbox Palette Objects
parent: Reach
nav_order: 9
has_toc: false
---
# Forge World Sandbox Palette Objects

Interpret this list as such:
* Numbers on the left relate to the palette index.
* The middle entries are the name/variant name StringIDs.
* The last part in brackets are comments such as tag types and Palette Object names.

0-14 - ff_weapons_human (.weap tags)
    0-9 - assault_rifle
    1-9 - dmr
    2-9 - grenade_launcher
    3-9 - magnum
    4-9 - rocket_launcher
    5-9 - shotgun
    6-9 - sniper_rifle
    7-9 - spartan_laser
    8-9 - wep_nade_frag (.eqip tag)
    9-9 - wep_machinegun (.vehi tag)

1-14 - ff_weapons_covenant (.weap tags)
    0-13 - concussion_rifle
    1-13 - energy_sword
    2-13 - wep_flakcannon (fuel rod gun)
    3-13 - gravity_hammer
    4-13 - focus_rifle
    5-13 - needle_rifle
    6-13 - needler
    7-13 - wep_plasmalauncher
    8-13 - plasma_pistol
    9-13 - plasma_repeater
    10-13 - plasma_rifle
    11-13 - spike_rifle
    12-13 - wep_nade_plasma (.eqip tag)
    13-13 - wep_plasmaturret (.vehi tag)

2-14 - ff_armor_abilities (.eqip tags)
    0-6 - arm_camo
    1-6 - arm_lock
    2-6 - arm_dropshield
    3-6 - arm_evade
    4-6 - arm_hologram
    5-6 - arm_jetpack
    6-6 - arm_sprint

3-14 - ff_vehicles (.vehi tags)
    0-8 - banshee
    1-8 - falcon
    2-8 - ghost
    3-8 - mongoose
    4-8 - revenant
    5-8 - scorpion
    6-8 - shade
    7-8 - warthogs (warthogs all use the warthog as a base, turrets are variants)
        0-2 - warthog_default (Variant = default)
        1-2 - warthog_gauss (Variant = gauss)
        2-2 - warthog_rocket (Variant = rocket)
    8-8 - wraith

4-14 - ff_gadgets (mostly .bloc tags)
    0-13 - gadget_explosive
        0-3 - exp_fusioncoil
        1-3 - exp_landmine
        2-3 - exp_battery
        3-3 - exp_propanetank
    1-13 - gadget_healthstation (.ctrl tag)
    2-13 - gadget_powerups (.eqip tags)
        0-2 - powerup_blue
        1-2 - powerup_red
        2-2 - powerup_yellow
    3-13 - gadget_mancannons
        0-4 - mancannon_normal (ff_man_cannon_forge)
        1-4 - mancannon_heavy (ff_man_cannon_forge_heavy)
        2-4 - mancannon_light (ff_man_cannon_forge_light)
        3-4 - mancannon_vehicle (ff_veh_man_cannon)
        4-4 - mancannon_gravlift (ff_grav_lift)
    4-13 - door_oneway_small (ff_one_way_door_small)
    5-13 - door_oneway_medium
    6-13 - door_oneway_large
    7-13 - gadget_sfx
        0-8 - sfx_1 (colorblind)
        1-8 - sfx_2 (gloomy)
        2-8 - sfx_3 (juicy)
        3-8 - sfx_4 (nova)
        4-8 - sfx_5 (olde_timey)
        5-8 - sfx_6 (pen_and_ink)
        6-8 - purple (dusk)
        7-8 - green (eerie)
        8-8 - orange (golden_hour)
    8-13 - door_shield_small (ff_two_way_door_small)
    9-13 - door_shield_medium
    10-13 - door_shield_large
    11-13 - gadget_teleporters
        0-2 - teleporter_reciever (ff_teleporter_receiver)
        1-2 - teleporter_sender
        2-2 - teleporter_2way
    12-13 - gadget_toys
        0-5 - toys_die (dice)
        1-5 - toys_golfball
        2-5 - toys_golfclub (.weap tag)
        3-5 - toys_killball (damage_sphere)
        4-5 - toys_soccerball
        5-5 - toys_tincup (golf_cup)
    13-13 - gadget_lights
        0-8 - ff_light_red
        1-8 - ff_light_blue
        2-8 - ff_light_green
        3-8 - ff_light_orange
        4-8 - ff_light_purple
        5-8 - ff_light_yellow
        6-8 - ff_light_white
        7-8 - ff_light_red_flash (ff_light_flash_red)
        8-8 - ff_light_yellow_flash (ff_light_flash_yellow)

5-14 - ff_spawning (.scen tags)
    0-7 - spawning_initial (initial_spawn_point)
    1-7 - spawning_respawn (respawn_point)
    2-7 - spawning_camera (mp_cinematic_camera)
    3-7 - respawn_zone
    4-7 - respawn_zone_weak (weak_respawn_zone)
    5-7 - respawn_zone_anti (weak_anti_respawn_zone)
    6-7 - spawning_boundaries_safe
        0-1 - spawning_safe (safe_volume)
        1-1 - spawning_safe_soft (soft_safe_volume)
    7-7 - spawning_boundaries_kill
        0-1 - spawning_kill (kill_volume)
        1-1 - spawning_kill_soft (soft_kill_volume)

6-14 - ff_objectives (.bloc tags)
    0-2 - obj_flag_base (mp_flag_base)
    1-2 - obj_plate (mp_circle)
    2-2 - obj_hill_marker (mp_hill_beacon)

7-14 - ff_scenery (.bloc tags)
    0-4 - ff_scn_barricades
        0-3 - ff_scn_barricade_small
        1-3 - ff_scn_barricade_large
        2-3 - ff_scn_covenantbarrier (cov_barrier)
        3-3 - ff_scn_cov_shield (cov_portable_shield) (.scen tag)
    1-4 - ff_scn_camping_stool (camping_stool_mp)
    2-4 - ff_scn_crates
        0-3 - ff_scn_space_crate
        1-3 - ff_scn_space_crate_small
        2-3 - ff_scn_cov_crate (crate_space_mp)
        3-3 - ff_scn_cov_crate_a (crate_space_a)
    3-4 - ff_scn_sandbags
        0-4 - ff_scn_sandbag_wall (sandbag_wall)
        1-4 - ff_scn_sandbag_turret (sandbag_wall_turret)
        2-4 - ff_scn_sandbag_45 (sandbag_wall_45corner)
        3-4 - ff_scn_sandbag_90 (sandbag_wall_90corner)
        4-4 - ff_scn_sandbag_end (sandbag_wall_endcap)
    4-4 - ff_scn_street_cone

8-14 - ff_structure (.bloc tags)
    0-7 - structure_blocks
        0-25 - block_1x1 (ff_plat_1x1)
        1-25 - block_1x1_flat
        2-25 - block_1x1_short
        3-25 - block_1x1_tall
        4-25 - block_1x1_tall_thin
        5-25 - block_1x2
        6-25 - block_1x4
        7-25 - block_2x1_flat
        8-25 - block_2x2
        9-25 - block_2x2_flat
        10-25 - block_2x2_short
        11-25 - block_2x2_tall
        12-25 - block_2x3
        13-25 - block_2x4
        14-25 - block_3x1_flat
        15-25 - block_3x3
        16-25 - block_3x3_flat
        17-25 - block_3x3_short
        18-25 - block_3x3_tall
        19-25 - block_3x4
        20-25 - block_4x4
        21-25 - block_4x4_flat
        22-25 - block_4x4_short
        23-25 - block_4x4_tall
        24-25 - block_5x1_flat
        25-25 - block_5x5_flat
    1-7 - structure_bridges
        0-20 - bridge_2x1 (ff_bridge_2x1)
        1-20 - bridge_2x2
        2-20 - bridge_2x3
        3-20 - bridge_2x5
        4-20 - bridge_diag
        5-20 - bridge_diag_short
        6-20 - dish
        7-20 - dish_door
        8-20 - corner_45 (ff_plat_2x2_45)
        9-20 - plat_2x2_corner
        10-20 - plat_4x4_corner
        11-20 - plat_landing_pad (ff_plat_4x6)
        12-20 - plat_ramped (ff_ramp_plat)
        13-20 - plat_4x4_tower
        14-20 - cylinder_small
        15-20 - cylinder_large
        16-20 - plat_y (ff_plat_y_cross)
        17-20 - plat_y_large
        18-20 - sniper_nest (ff_ramp_enclosed)
        19-20 - stair_case
        20-20 - walkway (ff_walkway_small)
    2-7 - structure_buildings
        0-10 - bunker_low
        1-10 - bunker_covered
        2-10 - bunker_full
        3-10 - bunker_gulch (ff_base_round)
        4-10 - bunker_stairs
        5-10 - pyramid
        6-10 - tower
        7-10 - tower_3_story
        8-10 - tower_tall
        9-10 - room_double
        10-10 - room_triple
    3-7 - structure_decorative
        0-15 - antenna
        1-15 - antenna_dish
        2-15 - brace
        3-15 - brace_large
        4-15 - brace_tunnel (ff_arch_brace)
        5-15 - ff_column
        6-15 - crenelation (ff_crenel_full)
        7-15 - crenelation_notched (ff_crenel_notch)
        8-15 - cover_glass (ff_cover_2)
        9-15 - wtf_is_this_thing (ff_ramp_wall_2x1)
        10-15 - railing_short (ff_railing_1)
        11-15 - railing_medium
        12-15 - railing_long
        13-15 - teleporter_frame (ff_teleport_frame)
        14-15 - ff_strut (ff_base_strut)
        15-15 - walkway_cover (ff_walkway_small_cover)
    4-7 - structure_doors
        0-11 - door (ff_door_2)
        1-11 - door_double (ff_wall_2x1_door)
        2-11 - window (ff_wall_2x1_window)
        3-11 - window_double (ff_wall_2x2_window)
        4-11 - wall (ff_wall_2x2)
        5-11 - wall_double (ff_wall_2x4)
        6-11 - wall_corner (ff_wall_2x1_corner)
        7-11 - wall_curved (ff_wall_curve_short)
        8-11 - wall_coliseum (ff_arena_wall)
        9-11 - window_coliseum (ff_arena_window)
        10-11 - tunnel_short (ff_tunnel_2x1)
        11-11 - tunnel_long (ff_tunnel_3x3)
    5-7 - structure_inclines
        0-14 - bank_1x1
        1-14 - bank_1x2
        2-14 - bank_2x1
        3-14 - bank_2x2
        4-14 - ramp_1x2
        5-14 - ramp_1x2_shallow
        6-14 - ramp_2x2
        7-14 - ramp_2x2_steep
        8-14 - ramp_circular_small (ff_ramp_circle_small)
        9-14 - ramp_circular_large
        10-14 - ramp_bridge_small (ff_ramp_3)
        11-14 - ramp_bridge_medium (ff_ramp_4)
        12-14 - ramp_bridge_large (ff_ramp_5)
        13-14 - ramp_4x2
        14-14 - ramp_stunt    (ff_race_stunt_ramp)
    6-7 - structure_natural
        0-7 - rock_small
        1-7 - rock_flat
        2-7 - rock_med1    (ff_rock_med_a)
        3-7 - rock_med2
        4-7 - rock_spire1    (ff_rock_spire_a)
        5-7 - rock_spire2
        6-7 - rock_seastack    (ff_rock_sea_stack)
        7-7 - rock_arch
    7-7 - ff_grid    (ff_grid_object)

9-14 - structure_blocks (hidden, objects have no render model - .bloc tags)
    0-10 - block_2x2 (box_l)
    1-10 - block_1x1 (box_m)
    2-10 - block_3x3 (box_xl)
    3-10 - block_4x4 (box_xxl)
    4-10 - box_5x5_flat (box_xxxl)
    5-10 - box_3x3_flat (wall_l)
    6-10 - box_2x2_flat (wall_m)
    7-10 - box_1x1_flat (wall_s)
    8-10 - box_4x4_flat (wall_xl)
    9-10 - box_4x4_tall (wall_xxl)
    10-10 - block_5x1_flat (wall_xxxl)

10-14 - ff_thorage_vehicles (.vehi tags)
    0-9 - ff_thorage_falcons
          0-2 - ff_thorage_falcon_default    (Variant default)
          1-2 - ff_thorage_falcon_grenade    (Variant grenade)
          2-2 - ff_thorage_falcon_no_guns    (Variant no_guns)
    1-9 - ff_thorage_warthog_troop    (Variant troop)
    2-9 - ff_thorage_sabre
    3-9 - ff_thorage_seraph
    4-9 - ff_thorage_electric_cart    (cart_electric)
    5-9 - ff_thorage_forklift
    6-9 - ff_thorage_pickup
    7-9 - ff_thorage_truck_cab    (Variant bed_long)
    8-9 - ff_thorage_oni_van
    9-9 - ff_thorage_shade_flak_cannon    (Variant flak_cannon)

11-14 - ff_thorage_gadgets (mostly .bloc tags)
    0-16 - gadget_mancannons
          0-5 - mancannon_normal    (dlc_medium_mancannon)
          1-5 - mancannon_heavy    (dlc_medium_mancannon_heavy)
          2-5 - mancannon_light    (dlc_medium_mancannon_light)
          3-5 - ff_cex_gravlift_forerunner    (heh_gravlift_tunnels)
          4-5 - ff_cex_gravlift_tall_forerunner    (heh_gravlift)
          5-5 - ff_cex_mancannon_human ( man_cannon)
    1-16 - door_oneway_xsmall    (ff_one_way_door_xsmall)
    2-16 - door_oneway_xlarge    (ff_one_way_door_garage)
    3-16 - ff_scn_laserwall_small    (frigate_laser_field_small)
    4-16 - ff_scn_laserwall_medium
    5-16 - ff_scn_laserwall_large    (frigate_laser_field_wall)
    6-16 - ff_scn_laserwall_xlarge    (frigate_laser_field_gate)
    7-16 - door_oneway_small    (ff_shield_door_small)
    8-16 - door_oneway_medium    (ff_one_way_door_medium)
    9-16 - door_oneway_large
    10-16 - door_shield_small    (dlc_hangar_shield_repair_s)
    11-16 - door_shield_small1    (dlc_hangar_forcefield_small_solid - the third L in small is a One)
    12-16 - door_shield_large    (dlc_hangar_shield)
    13-16 - door_shield_large1    (dlc_hangar_forcefield_solid)
    14-16 - ff_thorage_ammo_box    (ammo_box - .eqip tag)
    15-16 - ff_thorage_rocket_ammo    (rocket_launcher_ammo - .eqip tag)
    16-16 - ff_thorage_sniper_ammo    (sniper_rifle_ammo - .eqip tag)

12-14 - ff_thorage_scenery    (.bloc tags and some .scen tags)
    0-16 - ff_scn_barricades
          0-2 - ff_scn_jerseybarrier
          1-2 - ff_scn_jerseybarrier_short
          2-2 - dlc_invasion_heavy_shield
    1-16 - ff_scn_crates
          0-5 - ff_scn_crate_small_closed    (container_unsc_small_closed)
          1-5 - ff_scn_crate_metal    (crate_multi)
          2-5 - ff_scn_crate_metal_single
          3-5 - ff_scn_cov_crate_b    (crate_space_b)
          4-5 - ff_cex_crate_forerunner_sm    (ff_prisoner_forecrate_small)
          5-5 - ff_cex_crate_forerunner_lg
    2-16 - ff_scn_pallets
          0-2 - ff_scn_pallet    (industrial)
          1-2 - ff_scn_pallet_large
          2-2 - ff_scn_pallet_metal    (military)
    3-16 - structure_decorative
          0-2 - dlc_medium_driftwood_a
          1-2 - dlc_medium_driftwood_b
          2-2 - dlc_medium_driftwood_c
    4-16 - ff_vehicles    (.scen)
          0-4 - ff_thorage_phantom    (Variant no_turrets)
          1-4 - ff_thorage_spirit    (tuning_fork)
          2-4 - ff_thorage_pelican    (Variant no_interior)
          3-4 - ff_thorage_drop_pod_elite (no_door)
          4-4 - ff_thorage_anti_air_cannon
    5-16 - ff_thorage_destroyed
          0-2 - ff_thorage_cargo_truck_destroyed
          1-2 - ff_thorage_falcon_destroyed
          2-2 - ff_thorage_warthog_destroyed
    6-16 - ff_scn_chair_folding
    7-16 - ff_scn_dumpster
    8-16 - ff_scn_dumpster_tall
    9-16 - ff_thorage_equipment_case    (.scen - Variant empty)
    10-16 - ff_thorage_monitor_flush    (.scen - Variant screen_04)
    11-16 - ff_scn_cov_storage    (bulk_plasma_storage)
    12-16 - ff_scn_cov_stool
    13-16 - ff_scn_cov_antenna    (antennae_comm_mp)
    14-16 - ff_thorage_fuel_storage    (vehicle_fuel_storage)
    15-16 - dlc_slayer_cart_a    (.scen)
    16-16 - dlc_slayer_cart_b    (.scen)

13-14 - ff_thorage_structure    (.bloc tags)
    0-4 - structure_bridges
          0-7 - dlc_bridge_down
          1-7 - ff_cex_platform_cov    (ff_damnation_platform)
          2-7 - ff_cex_catwalk_straight    (ff_prisoner_bridge2)
          3-7 - ff_cex_catwalk_short    (ff_prisoner_bridge3)
          4-7 - ff_cex_catwalk_bend_left    (ff_prisoner_bridge_l)
          5-7 - ff_cex_catwalk_bend_right    (ff_prisoner_bridge_r)
          6-7 - ff_cex_catwalk_angled    (heh_angled_catwalk)
          7-7 - ff_cex_catwalk_lg    (heh_gravlift_catwalk)
    1-4 - structure_buildings
          0-1 - ff_cex_bunker    (ca_timberland_bunker)
          1-1 - ff_cex_gunner_nest    (ca_timberland_turret_base)
    2-4 - structure_decorative
          0-10 - ff_cex_cover_sm    (ca_timberland_toof)
          1-10 - ff_cex_large_block    (heh_bigblock)
          2-10 - ff_cex_hallway_blocker    (heh_large_hallway_blocker)
          3-10 - ff_cex_stone_column    (heh_ramp_column)
          4-10 - ff_cex_tombstone    (heh_tombstones)
          5-10 - ff_cex_stone_block    (heh_blue_cap)
          6-10 - ff_cex_cover_lg    (heh_red_airlift_paneldoor)
          7-10 - ff_thorage_cover_sm    (ff_prisoner_coverwall_sm)
          8-10 - ff_cex_walkway_cover_short    (heh_catwalk_cover)
          9-10 - ff_thorage_cover_lg    (ff_metal_plate)
          10-10 - ff_cex_i_beam    (ff_skill_jump)
    3-4 - structure_doors
          0-12 - wall    (slayer_door_forge)
          1-12 - door    (dlc_invasion_bomb_door - .scen tag)
          2-12 - ff_cex_door_human    (ff_door)
          3-12 - ff_cex_door_forerunner_a    (ff_bluebase_rocks02)
          4-12 - ff_cex_door_forerunner_b    (ff_forerunner_wall)
          5-12 - ff_thorage_door_c    (ff_prisoner_doorblocker_a)
          6-12 - ff_thorage_door_d    (ff_prisoner_doorblocker_b)
          7-12 - ff_thorage_door_e    (ca_heh_large_hallway_blocker2)
          8-12 - ff_thorage_door_f    (heh_hallwayblocker_int)
          9-12 - ff_thorage_door_g    (heh_redbase_door_big)
          10-12 - ff_thorage_door_h    (heh_redbase_door_small)
          11-12 - ff_cex_wall_sm_forerunner    (heh_hallwayblocker)
          12-12 - ff_cex_wall_lg_forerunner    (heh_smallwall)
    4-4 - structure_natural
          0-1 - dlc_medium_stone_b    (dlc_medium_cave_blocking_rock)
          1-1 - ff_cex_tree_life    (ca_timberland_treeoflife)

14-14 - ff_thorage_hidden    (various)
    0-2 - ff_thorage_generator    (generator_x_large - .mach tag)
    1-2 - ff_thorage_vending_machine    (.bloc tag)
    2-2 - ff_thorage_dinghy    (.scen tag)

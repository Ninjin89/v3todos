# Ninjins PvP/PvE backlog

Living list of shipped fixes and open work. Mark items `[x]` when done, `[ ]` when still open.

---

## Done

### Map and zones
- [x] **Optemize RPCs** trace and optimize rpcs.
- [x] **`mapDrawSettings` per zone**, `NearestZones` mesh, nest edges when zones overlap (any priority). Reference: `Bilder > meshing.png`.
- [x] **Toxic zones** (`ContaminatedArea_Dynamic` + `eventHosting`) survive `!rlz`, removed only when the host `EEDelete`s.
- [x] **Zone enter gear** (enter only, no exit restore): `TurnOffListedEnergyOnZoneEnter` + `energyOffItemClassNames`, `ApplyItemListOnZoneEnter` + `itemClassNamesOnZoneEnter`, inventory preorder via `NinjinsUpgraded_EnterFix`.
- [x] **Vehicle teleport desync**, use `transport.Synchronize()` so clients match the server.

### Weapons and damage

- [x] **Weapon restriction, melee**, melee follows the same blocked category as other weapons when configured.
- [x] **`CanFire` desync**, server blocks fire and empties ammo but client showed a full mag, sync ammo and magazine UI so blocked shots stay honest.
- [x] **Bolt and arrow bleed while damage is vetoed**, vanilla crossbow bolts blocked through `ProcessHit` and `AddArrow` when `DisableVanillaBoltBleeding_inPvE` applies.
- [x] **Arrows and bolts in PvP/PvE**, blocked hits no longer stick to player or clothing wrongly, PvP still allows bleed when damage is allowed.
- [x] **Arming explosives**, arming no longer self-damages or kills the armer.
- [x] **Chem gas and 40mm chem**, delete or neutralize so they do not apply unwanted damage.
- [x] **Thrown or shot grenades crossing PvE/PvP**, grenade base, chem gas, M79 40mm, delete or neutralize when crossing modes (both directions).

### Explosives and attribution

- [x] **Improvised explosives in PvE**, respect PvE damage and zone rules.
- [x] **Claymore arming**, store attacker and placer for attribution.
- [x] **Untraceable explosion damage**, if the source cannot be traced to a valid player or chain, deny damage (`allow damage = false`).
- [x] **Fireplace and heat on `ExplosiveBase`**, moving into oven, fireplace, or fire barrel does not pin a player id, ruin by fire keeps attribution empty so PvE veto still blocks when no player is found.
- [x] **Chain reaction**, chained blasts do not wrongly kill PvE players.

### Safe zone items

- [x] **Items in safe zone**, block all damage types on inventory (carrier in SZ) and world footprint, aligned with `ServerAppliesZoneDamageRules`.
- [x] **Ground items in safe zone**, loose ground items in SZ fully protected unless position is in an active scheduled safe zone (early skip).

### World and logging

- [x] **Land fuel stations**, block pump damage in PvE or block damage to players standing in PvE.
- [x] **Log retention**, rotation, max size, days on disk.
- [x] **Expansion AI damage system**, config gates, human vs AI bypass of player pairing, `TrackZoneState` on/off behavior.

### Admin Menu
- [x] **Icon preview** for objects.
- [x] **Live logs for Actions** Adding a WIndow that shows actionnames used and its item/target/door-index to have it copy paste ready.
- [x] **X button behind textbox/editbox** That will fully clear text inside the.
- [x] **Add/remove button overlaps**, resolve layout so buttons do not overlap.
- [x] **Add Zone** create a new zone for selected folder in zone-editor.
- [x] **Remove Zone** remove selected zone in zone-editor.
- [x] **Add Folder** create a new zone folder in zone-editor.
- [x] **Remove Folder** remove a selected zone folder in zone-editor.
- [x] **Coordinate picker** for all coordinate settings (teleport, staylimit, nologout): pressing Add uses player position, checkbox allows map-click as alternative.
- [x] **Territory mode selector** - use `XComboBoxWidget` for Raise, Lowered, Always.
- [x] **ColorPicker** for all admin menu settings that use argb/int color vales.
- [x] **Naming clarity** for all admin menu settings.
- [x] **Vertexes do get cleared** when switching polygon to circle and circle to polygon when close and open zone editr and so on.
- [x] **Icons** for: save,reload,viw raw,add,remove.
- [x] **Item-Search** itemsearch adding back.

---

## Open

- [] **Drawing Logic** maybe move it to core so it can be used by all coming mods again.
- [] **Item-Search** Opening Item-Search and zone-editor can cause zones to draw on Item-Serch - needs fix.

### Admin Menu

- [] **Zone logging** ZoneEditorReceivedLog on client enable/disable.

- [] **Folder Adding** Zone-Editor add popuop for adding new folder for name asking same as for new zone add.


### Missing Stuff

- [ ] **PaintBallMod SUpport** (maybe).
- [ ] **Other State Types and Zone Types**
- [ ] **Lockpicking**
- [ ] **LB Admin Support** for all admin menu settings.
- [ ] **Expansion Spawnselect**, show zones on expansion spawnselect (but no map legend panel there).
- [ ] **Hunterz AI bandits**, damage system hooks and zone behavior still to align.
- [ ] **Remote detonation vs placement zone**, if a mine or charge was placed in PvP but the arming player is in PvE (or the reverse), block detonation when current zone state does not match placement state. Always cross-check placer state at arm time and at trigger time.

### Weapons and damage types

- [ ] Expansion RPG launchers (damage and zone rules as needed).

### Bugs and sync
- [ ] **Client crash on logout/exit** Client crashes when Admin Menu still has open Windows, if not having open windows it doesnt crash.

- [ ] **`blockWeaponRaise` per zone**, zone JSON flag to block weapon raise only (not full fire deny).

### Safe zone

- [ ] **Drowning**, in safe zone, stop drowning stamina drain and pass-out, align vehicle behavior where modules allow (no engine water damage where applicable).
- [ ] **Metabolism**, no hunger, food, or energy drain in safe zone (confirm exact stats in design).

### Vehicles

- [ ] **Vehicle damage tests**, zones, safe zone, water, modules, combat damage, still need a full pass.

### Cross-zone PvE vs PvP

- [ ] 

### PvP damage between zones

- [ ]

### Map drawer (nested, meshed outlines)

- [ ]

### General and logging

- [ ]

---



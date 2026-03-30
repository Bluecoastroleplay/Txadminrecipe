# Bluecoast txAdmin recipe

txAdmin **Server Deployer** recipe (`$engine: 3`): Qbox/Ox/voice **baseline** + **Bluecoastroleplay** GitHub repos. Trimmed heist/minigame/prison/diving packs; **mana_audio** kept (harmless extra).

## Contents

| File | Purpose |
|------|---------|
| `recipe.yaml` | Full task list (downloads + SQL) |
| `server.cfg` | `{{serverEndpoints}}`, `{{svLicense}}`, `{{dbConnectionString}}`, `{{addPrincipalsMaster}}`, … |

## Included (summary)

- **Qbox template:** `txAdminRecipe` → `qbox.sql`, `permissions.cfg`, `ox.cfg`, `voice.cfg`, `misc.cfg`, logo, Qbox **`items.lua`** → `ox_inventory` (then **overwritten** by **`Oxdata`**).
- **`Oxdata` repo:** `Bluecoastroleplay/Oxdata` → your **`items.lua`** + **`web/images`** into `ox_inventory`.
- **CFX default** resources, **bob74_ipl**, **Ox** (lib, target, mysql, doorlock, inventory, fuel).
- **Standalone:** screencapture, Renewed-Banking, **loadscreen**, **mana_audio**, MugShotBase64, Renewed-Weathersync, **vehiclehandler**, scully_emotemenu.
- **Voice:** pma-voice. **qbx_radio** in `[qbx]`.
- **Qbox zips:** core, vehicles, management, smallresources, density, adminmenu, spawn, customs, **qbx_vehiclekeys**.
- **Your GitHub:** `bcrp_satmap` (sat map + `bcrp_satmap_postals.json` for HUD street bar), `illenium-appearance` (fork **`Illenium-appearance-Rework-`**), `qbx_hud`, `qbx_garages`, bc-mdt, policesystem, gs_robbery, bcrp_trucking, drug/blackmarket scripts + their SQL where listed in the recipe.

## Omitted on purpose

- safecracker, mhacking, ultra-voltlab, qbx_truckrobbery, xt-prison, qbx_diving, qbx_divegear, qbx_binoculars.
- **NPWD** / phone stack.

## Use in txAdmin

1. Clone this repo (or download a release ZIP) on the machine that runs txAdmin.
2. **Server Setup** / **Deployer** → **Custom recipe** → point at **`recipe.yaml`** in this folder.  
   Or use a **raw GitHub URL** to `recipe.yaml` on your default branch (txAdmin can fetch recipes from URL).
3. Finish DB + license + admin steps in the wizard.

## After deploy

- Set **`bc_mdt_fivemanage_key`** if you use FiveManage.
- If **`Illenium-appearance-Rework-`** repo layout ≠ a resource root named `illenium-appearance`, fix `dest` / repo structure or `fxmanifest` **name**.
- Add **ambulance / medical / properties / vehicleshop** etc. manually if you need them (no stable public zip matched when this recipe was built).

## Upstream reference

https://github.com/Qbox-project/txAdminRecipe/blob/main/qbox-stable.yaml

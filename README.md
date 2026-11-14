# Arrowhead Stadium: Minecraft Java Edition 1:1 Build Guide

An independently hosted, interactive block-by-block **Minecraft Java Edition** Arrowhead Stadium blueprint viewer, adapted from the [Colosseum blueprint viewer](https://trueyouaura.github.io/minecraft-colosseum/).

**Open the viewer:** https://trueyouaura.github.io/Arrowhead-Stadium/

## Stadium facts (checked November 2026)

- **Official name:** **Arrowhead Stadium**, restored beginning with the 2026 NFL season.
- **Location:** 1 Arrowhead Drive, Kansas City, Missouri.
- **Opened:** 1972; underwent a major renovation completed in 2010.
- **Design:** Open-air NFL stadium with three major spectator levels: Field Level (100 sections), CommunityAmerica Club Level (200 sections), and Upper Level (300 sections).
- **Playing surface:** Natural grass, installed in 1994.
- **NFL playing field:** 120 yards long including two end zones and 53⅓ yards wide, approximately **110 × 49 meters** (Minecraft blocks at the nominal 1 m/block scale).

**Official references:** [Arrowhead Stadium's maps and levels](https://www.arrowheadstadiumkc.com/plan-your-visit/stadium-maps), [Kansas City Chiefs news](https://www.chiefs.com/news/corporate), and [NFL playing rules](https://operations.nfl.com/the-rules/nfl-rulebook/).

The **actual stadium's full footprint and detailed internal layout are not supplied by these sources**. The Minecraft model's 240 × 288 layout, its underground rooms, seating slopes, concourses, ramps, suites, press areas, and roofline details remain creative approximations, not verified as-built measurements.

## Blueprint specifications

| Property | Value |
|---|---|
| Construction site | 240 × 288 blocks |
| World origin (northwest corner) | X 1000, Z 1000 |
| World bounds | X 1000–1239, Z 1000–1287 |
| Ground/field layer | Y 90, relative layer 0 |
| Underground minimum | Y 80, relative layer −10 |
| Maximum build layer | Y 159, relative layer +69 |
| Construction layers | 80 |
| Non-air blocks | 604,037 |
| Model scale | Nominally 1 block ≈ 1 meter |

**Important accuracy note:** This is a Minecraft-friendly visual reconstruction, **not** an official architectural drawing or surveyed CAD model. The regulation football field is modeled at approximately 110 × 49 blocks; the enclosing stadium structures, room layouts, seat risers, suites, ramps, press facilities and underground facilities are **design approximations**. Do not treat their dimensions or construction as verified stadium specifications.

## Features

- One Minecraft block per numbered grid square, both full-layer overview and zoomed detail.
- Select any of 80 Y layers, navigate Z rows and X columns, or jump to a coordinate.
- Generate individual copyable `/fill` and `/setblock` commands.
- Build by material, with expandable Y-layer groups.
- Mark blocks, commands, rows and columns placed. Overall progress counts each block once.
- Resize command and progress panels.
- Export/import saved progress as JSON. Progress is stored **locally in the browser**, not on GitHub.

## How to build

1. Make a Minecraft world backup before clearing any terrain.
2. On the website, set **Start X**, **Field Y**, and **Start Z** in the **Your Minecraft starting coordinates** panel. X and Z mark the northwest corner; Y is the stadium field's ground layer. Choose a location that fits all 240 × 288 blocks and all 80 Y layers.
3. Click **Save coordinates**, press Enter, or finish editing a field to save automatically. Your selected coordinates are restored whenever you reload or reopen the same website in the same browser, subject to that browser retaining site data.
4. Start at relative layer −10 (10 blocks below your chosen Field Y) for underground foundations, then work upward.
5. In the viewer, select a row/column or material to generate commands. Each command is already mapped to the default real-world Minecraft coordinates.
6. Click **Mark placed** only after the corresponding in-game command succeeds. Copying alone does not verify placement.
7. **Air means leave empty where there is interior structure.** Outside the stadium footprint, air squares are just blank canvas and do not mean you need to excavate surrounding land.
8. Back up progress from the Progress Checklist tab before changing computers or browsing origins.

## Saving your starting coordinates

The website has editable fields for the **northwest starting X/Z** and **field Y**. Default values are `X 1000, Y 90, Z 1000`; your own saved values take precedence on the next load.

- Starting coordinates are saved in the browser's `localStorage` under `arrowhead-start-coordinates-v1`, separately from placed-block progress.
- Editing and leaving a field saves automatically; the **Save coordinates** button also saves and applies all three values.
- The layer picker, numbered X/Z grid, world Y labels, `/setblock` commands, row/column `/fill` commands, material-first commands, and coordinate jump limits all update to match.
- **Reset defaults** restores the original X 1000, Y 90, Z 1000 starting position without erasing your progress.
- You may choose negative X/Z coordinates. The chosen field elevation must be between **Y −54 and Y 250** so all 80 model layers fit within the Java overworld height limits (−64 through 319).
- Build progress is recorded relative to each block in the model, so changing coordinates does not erase checkmarks or alter the 604,037-block blueprint.
- Minecraft itself does **not** relocate previously placed blocks when you change the website's origin. Make sure you really intend to use the new location before building further.
- Progress JSON backups still include the coordinates used when exported, but they can now be imported at a different starting position without overwriting the currently saved origin. Prior copied commands from different world coordinates are not restored.
- Browser storage is specific to that browser and site. Clearing site data, using a private window, or changing browsers can remove saved coordinates; progress backup exports do not replace browser settings backups.

## Hosting on GitHub Pages

Site contents are in the repository root as `index.html`. A GitHub Actions workflow deploys this file on pushes to `main`.

In GitHub, visit **Settings → Pages**, and set **Source = GitHub Actions**. Then check the most recent workflow under **Actions**. If needed, manually run **Deploy Arrowhead Blueprint Website**. GitHub Pages publication is separate from committing the code.

The Colosseum project remains hosted separately at https://trueyouaura.github.io/minecraft-colosseum/.

## Reference starting points

- [NFL operations: official football rules and playing field information](https://operations.nfl.com/)
- [Arrowhead Stadium official site](https://www.arrowheadstadiumkc.com/)

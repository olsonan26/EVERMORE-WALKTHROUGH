# AI Visual Reference Handoff

Use this file when handing the Evermore recreation to Claude, Higgsfield, Unreal Engine, or another tool. The purpose is to give those tools image references, not just written descriptions.

## Read First

1. `Reference/visual_boards/00_master_keyframes_contact_sheet.jpg`
2. `Docs/FULL_PATHWAY_ATLAS_GUIDE.md`
3. `Reference/pathway_atlas/`
4. `Reference/youtube_tUMoegiI5_Q/pathway_frames_2sec/`
5. `Reference/visual_boards/01_entry_garden.jpg`
6. `Reference/visual_boards/02_towne_square_shops.jpg`
7. `Reference/visual_boards/03_chapel_activity_yard.jpg`
8. `Reference/visual_boards/04_bridge_ruins_hall.jpg`
9. `Reference/visual_boards/05_big_top_vendor_return.jpg`
10. `Reference/visual_boards/visual_reference_manifest.json`
11. `Docs/EVERMORE_PARK_VIDEO_WALKTHROUGH.md`
12. `Docs/EVERMORE_WORLD_GRAPH.json`
13. `Docs/evermore_video_blockout.png`

## Visual Truth Rules

- The still images are the appearance truth.
- The pathway atlas is the path/turn/sightline truth for everything visible in the walkthrough.
- `Docs/EVERMORE_WORLD_GRAPH.json` is the adjacency/route truth.
- The public map reference gives named zones, but the video frames win for visible ground-level details.
- Do not invent exact dimensions from the images alone.
- Do not fill unseen west/north areas as certain. Mark them as reference gaps until more videos/photos are added.

## For Claude

Claude should treat the image boards as the primary visual input and the route/graph files as structure. When generating Unreal tasks, asset lists, prompts, or scene descriptions, Claude should cite the relevant board and timestamp.

Example task format:

```text
Build Zone 04 from Reference/visual_boards/04_bridge_ruins_hall.jpg.
Use 13:05 for rope bridge approach, 13:20 for tent/ship wheel props,
13:40 for ruins entry, 14:20 for raised hall, and 15:20 for balcony-over-ruins composition.
```

## For Higgsfield

Use each visual board as the image reference for that shot or scene. Keep the camera grounded in the route sequence.

Prompt anchors:

- Zone 01: medieval fantasy park entrance lawn, pumpkin arch, enclosed garden path, skull rock, fire pit, autumn Halloween props.
- Zone 02: stone-paved village square, blue-shutter barter shop, confection/cafe interior, barrels, chalk menus, warm shop lighting.
- Zone 03: chapel tower, hay-bale pumpkin graveyard, twig pumpkin arch, rough activity yard, black cage fencing, mountain backdrop.
- Zone 04: rope bridge beside rocks/water, canvas tent with ship wheel, stacked Celtic ruins, white columns, raised wood hall, balcony overlooking ruins.
- Zone 05: red-striped Big Top, vendor tents, string lights, giant pumpkins, green tents, greenhouse return edge.

## For Unreal Engine

Use the visual boards as reference planes or texture references inside the project. Do not import them as final game textures unless you have rights to use the source footage that way.

Recommended Unreal folder plan once a `.uproject` exists:

```text
Content/Reference/Evermore/VisualBoards/
Content/Reference/Evermore/Keyframes/
Content/Evermore/Blockout/
Content/Evermore/Materials/
Content/Evermore/Props/
Content/Evermore/Architecture/
```

Suggested first blockout pass:

1. Build the route from `Docs/EVERMORE_WORLD_GRAPH.json`.
2. Place beacon silhouettes from `Docs/EVERMORE_LEVEL_BLOCKOUT.md`.
3. Put each visual board on a temporary reference plane near its matching zone.
4. Match path widths, wall heights, sightlines, and prop clusters before making detailed meshes.
5. Compare the in-engine walk to `Reference/youtube_tUMoegiI5_Q/route-notes.csv`.

## Current Visual Pack

The visual pack is already generated at:

```text
Reference/visual_boards/
```

It includes one master keyframe sheet, seven full-video overview sheets, five zone-specific boards, and a machine-readable manifest.

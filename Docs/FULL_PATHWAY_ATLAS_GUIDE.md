# Full Pathway Atlas Guide

This is the dense visual pack for the Evermore walkthrough. Use it when the goal is to recreate all paths, turns, junctions, and sightlines shown in the video.

## What Was Generated

- `Reference/youtube_tUMoegiI5_Q/pathway_frames_2sec/`
  - 629 full-size still images from the whole walkthrough.
  - One image every 2 seconds.
  - Best source for close inspection of path edges, wall turns, side paths, storefront fronts, and prop placement.

- `Reference/pathway_atlas/`
  - 21 pathway sheets.
  - Each sheet covers roughly one minute of the walkthrough.
  - These are easier for Claude, Higgsfield, and humans to scan than hundreds of loose images.

- `Reference/pathway_atlas/pathway_atlas_manifest.json`
  - Machine-readable list of every pathway sheet and every frame inside it.

- `Reference/pathway_atlas/pathway_frame_index.csv`
  - Spreadsheet-style index: frame name, timestamp, seconds, source image, and sheet.

## How To Use

For a true route blockout, use the files in this order:

1. Open `Docs/evermore_video_blockout.png` for the rough top-down path.
2. Open `Docs/EVERMORE_WORLD_GRAPH.json` for route order.
3. Open `Reference/pathway_atlas/pathway_sheet_01_00m.jpg` and continue sheet-by-sheet through `pathway_sheet_21_20m.jpg`.
4. When a specific view matters, open the matching full-size still from `Reference/youtube_tUMoegiI5_Q/pathway_frames_2sec/`.
5. Use `Docs/EVERMORE_PARK_VIDEO_WALKTHROUGH.md` for named landmarks and uncertainty notes.

## Important Accuracy Note

This atlas covers all pathways visible in this specific YouTube walkthrough. It cannot show paths the camera never visits or areas hidden behind people, props, walls, tents, or turns. Those must stay marked as unknown until another walkthrough, old map, aerial image, or photo set fills them in.

## Tool Handoff Prompt

```text
Use Reference/pathway_atlas as the complete visual pathway reference.
Follow pathway_sheet_01_00m.jpg through pathway_sheet_21_20m.jpg in order.
Use the full-size stills in Reference/youtube_tUMoegiI5_Q/pathway_frames_2sec for close visual inspection.
Recreate all visible paths, turns, junctions, walls, path materials, side-path hints, and sightline landmarks.
Do not invent exact off-camera paths. Mark unseen areas as reference gaps.
```

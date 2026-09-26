# Project Audit: Evermore Walkthrough Reconstruction

## Executive Finding

This folder is a reference-forensics and video-frame extraction package, not an Unreal Engine project. It contains enough evidence for a limited gray-box walkthrough of the captured route through Evermore Park, and enough mood/landmark material for selected mid-fidelity experiments in visible areas. It does not contain enough evidence for a genuinely accurate full high-fidelity reconstruction of the entire park.

The strongest usable evidence is the local 720p walkthrough video, the 629 sequential 1280x720 pathway frames sampled every 2 seconds, the illustrated park map, the route notes, and the generated world graph. The main weakness is coverage: this is mostly one walked route, with many off-camera paths and named zones missing or only map-inferred.

## Project Type

- Type: image/reference pack plus video/frame extraction and reconstruction planning docs.
- Valid `.uproject`: none found.
- Unreal build artifacts: none found. No `.umap`, `.uasset`, `.uplugin`, `Content/`, `Source/`, `Config/`, target files, or Unreal maps were found.
- Code: no project code found. `.agents`, `.codex`, and local `.git` directories contain no files in this checkout.
- Source video: present at `Reference/youtube_tUMoegiI5_Q/source_720p.mp4`, verified locally as 1280x720, about 20:58.5 long.
- Source metadata: present at `Reference/youtube_tUMoegiI5_Q/source.info.json`; metadata describes the original YouTube stream as 4K, but the local working MP4 is 720p.
- Maps: one illustrated park map PDF plus one rendered JPG. No true aerial, survey, satellite, lidar, drone, or georeferenced map was found.
- Route frames: present and sequential.
- Generated world layouts: present as `Docs/evermore_video_blockout.png`, `Docs/evermore_video_blockout.svg`, and `Docs/EVERMORE_WORLD_GRAPH.json`.
- Documentation: several handoff and blockout docs are present under `Docs/` and `Reference/README.md`.

## Evidence Inventory

| Category | Evidence Found | Count / Dimensions | Reconstruction Value |
|---|---:|---|---|
| Aerial maps | None | 0 | Missing. No aerial/satellite/survey-grade layout evidence. |
| Park maps | Illustrated map PDF and rendered JPG | 1 image at 4800x3600 plus 1 PDF | Useful for named topology and rough adjacency; not reliable for exact scale, angles, or dimensions. |
| Walkthrough frames | 629 pathway frames, 126 low-res frames, 69 dense low-res 11-16 minute frames, 21 keyframes | 650 images at 1280x720 across path/keyframe sets; 195 low-res images at 320x180 across sparse/dense sets | Best actual ground-level evidence. 720p frames support gray-box path and approximate landmarks; 320x180 frames are overview/mood only. |
| Gatehouse / entrance | Entry lawn, gazebo/tower, pumpkin arch, garden approach | 119 images: 100 at 1280x720, 19 at 320x180 | Good for the captured entrance/garden approach. Vander's Keep/gatehouse itself is map-only or partial, so this supports approximate reconstruction only. |
| Central plaza | Towne Square approach, sign cluster, Barter's Post side, chapel frontage assigned to central route coverage | 111 images: 88 at 1280x720, 23 at 320x180 | Good for route-facing facades and plaza surfaces; incomplete for full plaza backsides and exact dimensions. |
| Market / tavern | Confection/cafe, food/shop frontage, vendor return, greenhouse edge | 263 images: 220 at 1280x720, 43 at 320x180 | Strongest coverage by volume, but Crooked Lantern Tavern itself is not ground-confirmed. Good for approximate visible market/vendor lanes only. |
| Water / bridge / ruins | Rope bridge/tent, water/rock edge, Celtic Ruins, raised hall, balcony, ruin courtyard | 180 images: 114 at 1280x720, 66 at 320x180 | Strong visible evidence for approximate geometry and vertical composition. Still not exact enough for measured high-fidelity work. |
| Archery | Back activity yard, fenced lanes, open field, rustic booths | 78 images: 49 at 1280x720, 29 at 320x180 | Supports an approximate activity-yard/archery-area blockout, but signs and exact archery layout are not clear. |
| Pavilion / stage | Gravel stage courtyard, Big Top/festival field, entry tower/gazebo sightlines | 94 images: 79 at 1280x720, 15 at 320x180 | Big Top is clear; main/circus/performance stage is partial and not enough for exact staging. |
| Railway / train | Visible on illustrated park map only | 0 direct ground-level images | Not build-ready beyond map placement. No station/train/track geometry evidence from the walkthrough. |
| Mythos | None found | 0 | Not usable yet. |
| Lore | None found | 0 | Not usable yet. |
| Aurora | None found | 0 | Not usable yet. |
| Generated reconstruction assets | Visual boards, contact sheets, pathway atlas sheets, world graph, blockout diagram, route docs/manifests | 48 images plus docs/json/csv | Useful as indices and planning aids. These should not be treated as new visual truth beyond the original map/video frames. |
| Unknown / unclassified | No meaningful visual files remained unclassified after timestamp routing | 0 images | Support files are documented in the manifest. |

## Usable Visual Evidence Quality

The usable geometry evidence is mainly 720p video-derived stills. These are clear enough for route order, path bends, major walls, facade silhouettes, material changes, and approximate prop placement. They are not clear enough for exact mesh dimensions, high-resolution facade detailing, small sign text, or hidden sides of buildings.

The 320x180 frame set is too low-resolution for geometry decisions. It is useful only as quick overview/mood reference.

Several interior and late-day frames are dark, occluded by guests, or motion-blurred. Those frames can support mood and rough object placement, but not reliable geometry. The best reconstruction sources are the 1280x720 path frames and keyframes, cross-checked against the map and route graph.

## Route Continuity

- Primary path series: `Reference/youtube_tUMoegiI5_Q/pathway_frames_2sec/path_0001.jpg` through `path_0629.jpg`.
- Numbering: complete, no missing path frame numbers from 1 to 629.
- Timestamp coverage: 00:00 through 20:56 at 2-second intervals.
- Route metadata: `Reference/pathway_atlas/pathway_frame_index.csv`, `Reference/youtube_tUMoegiI5_Q/route-notes.csv`, and `Docs/EVERMORE_WORLD_GRAPH.json` provide ordering and adjacency.
- Beginning coverage: entry/festival lawn, pumpkin arch, garden path.
- Middle coverage: Towne Square, chapel/activity yard, rope bridge, ruins, raised hall.
- End coverage: Big Top/vendor return, green tents, greenhouse/final board edge.

Missing route continuity:

- The west/north loops shown on the park map are not fully walked.
- Crooked Lantern Tavern, Nettleton Mill, Slanting Shanty, Loudon's Rest, Pigmyweeds Inn, Hex Trove, End of Haunt, and full railway/train coverage are not ground-confirmed.
- Side paths, backstage/service gaps, rear faces of buildings, exact intersections, and hidden junctions remain inferred.
- The path is one camera route, not a complete navigable survey.

Duplicate/repeated material:

- No exact duplicate files were found in the primary `pathway_frames_2sec` route series.
- Eight exact duplicate contact/overview sheets exist because the same contact sheets are mirrored into `Reference/visual_boards/` and the YouTube extraction folders.
- Many adjacent frames are intentionally near-duplicates because the camera pauses or moves slowly. That is useful for continuity but should not be counted as independent landmark coverage.

## Landmark Coverage Scores

| Landmark | Score | Evidence Supports | Notes |
|---|---:|---|---|
| Gatehouse / entrance | 5/10 | Approximate reconstruction | Entry lawn, pumpkin arch, tower/gazebo and garden approach are visible. Vander's Keep/gatehouse is not sufficiently covered for exact reconstruction. |
| Central plaza | 7/10 | Approximate reconstruction | Towne Square, Barter's Post side, paving, planters, and plaza-facing facades are visible. Exact full plaza footprint and hidden facades are not known. |
| Circus / stage area | 6/10 | Approximate reconstruction | Big Top and festival field are clear. Main/circus stage geometry is partial and mostly inferred from map plus sightlines. |
| Market lane | 6/10 | Approximate reconstruction | Barter's Post, food/shop frontage, vendor return and greenhouse edge are visible. Full market/tavern lane is incomplete. |
| Tavern | 1/10 | Not usable yet | Crooked Lantern Tavern appears on the illustrated map but is not ground-confirmed in the inspected evidence. |
| Water edge / bridge / ruins | 8/10 | Approximate reconstruction | Rope bridge, rock/water edge, Celtic Ruins, columns, raised hall and balcony relationship are well represented for gray-box and mid-fidelity silhouette work. |
| Archery grounds | 4/10 | Mood-only to approximate | Activity yard/fenced lanes are visible, but exact archery targets/range layout and signs are unclear. |
| Pavilion / performance stage | 4/10 | Mood-only to approximate | Entry gazebo/tower and gravel stage courtyard are visible, but performance-stage dimensions and complete stage design are not. |
| Railway / station / train | 2/10 | Mood-only/map placement | The illustrated map shows Evermore Express/rail, but the video frames do not provide usable ground-level railway geometry. |
| Forest paths | 4/10 | Approximate for visited garden paths only | Entry/garden paths are visible; the outer forest and north/west path loops are not fully captured. |
| Mythos | 0/10 | Not usable yet | No direct files found. |
| Lore | 0/10 | Not usable yet | No direct files found. |
| Aurora | 0/10 | Not usable yet | No direct files found. |

## Game-Readiness Ratings

| Area | Score | Reason |
|---|---:|---|
| Map topology | 5/10 | Illustrated map plus route graph gives rough adjacency, but no aerial/survey data or full path coverage. |
| Player route accuracy | 7/10 | The captured route is continuous and timestamped; off-route segments remain unknown. |
| Landmark accuracy | 5/10 | Several visible landmarks are usable approximately; many named landmarks are map-only or missing. |
| Seasonal accuracy | 7/10 | October/Haunt seasonal dressing is well represented in visible zones. Other seasons are not represented. |
| Environment mood | 7/10 | Strong mood evidence from pumpkins, tents, ruins, lighting, props, and guest-scale context. |
| Actual Unreal build readiness | 1/10 | No `.uproject`, no Unreal content, no maps, no source, no assets. This is not a runnable build. |

## Build Readiness Decision

1. Reference-forensics only: ready.
2. Gray-box walkthrough build: ready for the captured route only.
3. Mid-fidelity visual build: partially ready for visible zones, especially entrance/garden, Towne Square/market-facing facades, ruins/raised hall, and Big Top/vendor return.
4. Full high-fidelity Evermore reconstruction: not ready.

## Final Recommendation

Fable Five should not start a full real-world Evermore reconstruction from this pack alone. The evidence is strong enough to start a limited gray-box route prototype that follows the captured walkthrough, while clearly marking unknown zones and avoiding claims of exact scale. Fable should wait for more reference extraction before building high-fidelity landmarks or full-park topology.

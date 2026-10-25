# Checkpoint Screening Game

A first-person checkpoint-screening game built as part of a larger team project ("Team Immortal") at the BWSI SGAI 2026 program. At each station you scan a subject and decide PERMIT or REJECT under a time limit; in one experimental condition you also see a CNN classifier's recommendation, hedged ("AI LEANS" vs. "AI RECOMMENDS") based on how confident the model actually is. The game logs every decision, pairing it with pre/post surveys on AI trust, to study how people rely on (or override) AI advice under pressure.

## What's in this repo

This is the subset of a larger team codebase that I personally built — `screen.html`, the checkpoint-screening game itself (first-person movement, scan/PERMIT/REJECT mechanic, the AI-assist UI, trust surveys, and the Google Sheets logging wiring).

The full team project also includes a CNN image classifier and RL triage agent (BWSI SGAI program-provided starter, extended by teammates), an adversarial RL agent that generates the game's graded-difficulty subject images, and a data analysis pipeline — built by teammates and not included here, since that work isn't mine to publish.

## Build history

`build-history/` contains real snapshots of `screen.html` pulled from git history at several milestones, showing how the game evolved — including two real bugs hit along the way and how they were fixed:

| File | Stage |
|---|---|
| `01-placeholder.html` | First prototype — walkable room, placeholder kiosk, buttons not yet wired |
| `02-3d-map-linked-bug.html` | Real 3D map linked in — but broken: `MAP_PATH` pointed at `mapRework2.glb` with no folder prefix, so the loader couldn't find it |
| `03-real-images.html` | Subject images loading from the real dataset |
| `04-ai-recommendation.html` | AI-assist recommendation panel added |
| `05-image-floating-bug.html` | Bug: subject image floated as a flat 2D panel over the screen instead of appearing on the in-world monitor — the GLB screen mesh's UVs ran outside the normal 0-1 range |
| `06-image-floating-fixed.html` | Fix: added `normalizeMeshUVs()` to rescale mesh UVs back to 0-1 so the image renders correctly on the physical screen |
| `07-final.html` | Finished checkpoint flow |

These are read-only historical snapshots kept for reference — some may not fully render without the full team repo's asset paths.

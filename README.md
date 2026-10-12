# Kilter Climb Real2Sim: 4D viewer

Interactive viewer for the [Kilter Climb Real2Sim dataset](https://huggingface.co/datasets/knightnemo/kilter-climb-real2sim):
103 Kilter Board climbing videos, each reconstructed into a replayable 4D scene with the board and its holds under a
calibrated camera, the climber's SMPL-X motion, hand and foot contacts, and the motion retargeted to a Unitree G1.

Live site: https://knightnemo.github.io/kilter-climb-real2sim/

## What the page shows

- **Scene**: the wall and SAM 2 hold domes, textured by projecting the climber-free median frame through the calibrated
  camera; Kilter LED rings mark the route's holds and light up while a hand or foot is on them.
- **Climber**: an SMPL-X body skinned in the browser, coloured from the video.
- **G1**: the Unitree G1 retarget on the same wall (scaled by the robot-to-climber size ratio), alone or side by side.
- **Metrics**: per-clip quality tier, human / G1 scores, lit holds touched, G1 contact accuracy, penetration,
  self-collision and support feasibility.

## Files

- `index.html`: the page (three.js r128): the promo video, then the viewer.
- `promo.mp4`: the 66 s promo video (720p).
- `clips.json`: one entry per clip with its metadata, scene and G1 descriptors.
- `shared/`: the SMPL-X skinning rig and the G1 meshes.
- `media/<id>/`: per clip
  - `scene.bin`: rest shape, joint rotations, vertex colours and hold domes;
  - `g1.bin`: G1 part poses at 15 fps;
  - `wall.jpg`: the median frame;
  - `video.mp4`: a small copy of the source video.

Binaries are stored as base64 text.

## Licence

The source videos and the frames derived from them belong to their original uploaders (see each clip's source link)
and are shown for research reference only. Uploaders who want a clip removed can open an issue naming the clip id.
Board and climb data come from the Kilter Board app (Aurora Climbing).

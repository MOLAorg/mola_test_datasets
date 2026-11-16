# Loop closure registration cases

Pairs of point cloud fragments (`.mm` metric maps) with their relative pose, for
unit tests of loop closure registration (global registration and ICP).

- `dataset.yaml` and the `kitti*` / `mulran*` files: local map pairs with good
  and bad ICP solutions (KITTI and MulRan licenses: see `../kitti` and
  `../mulran`).
- `vbr/`: 55 cases (single scans and small local maps) from the VBR dataset,
  CC BY-SA 4.0. See `vbr/README.md` and `vbr/cases.yaml`.

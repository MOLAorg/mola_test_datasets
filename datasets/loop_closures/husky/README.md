# Loop closure cases from Husky runs

Single LiDAR scans and small local maps from two runs of a Clearpath Husky A200
(University of Almeria) with an Ouster LiDAR, outdoors, each driving a loop
back to its start, with the relative pose between them, for unit tests of loop
closure registration. Cases and file format: `cases.yaml`.

- Fragments: as in `../vbr/README.md` (de-skewed, [1, 80] m, 0.25 m voxels, one
  layer `points`, in the frame of the (central) keyframe, `base_link`).
- Reference poses: from RTK GNSS (position) and an odometry-to-RTK track fit
  (yaw), refined by ICP between local maps of 21 keyframes around both ends.
  The LiDAR-inertial odometry of these runs drifts up to 38 m, and most pairs are
  8-15 m apart, which makes them hard cases for loop closure.
- No geographic coordinates are included.

## License

CC BY 3.0 (`LICENSE`).

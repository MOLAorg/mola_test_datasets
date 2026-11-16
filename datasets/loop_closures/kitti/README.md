# Loop closure cases from KITTI

Single LiDAR scans and small local maps cut from the KITTI odometry sequences
with loops (00, 02, 05, 06, 07, 08), with the relative pose between them, for
unit tests of loop closure registration. Cases and file format: `cases.yaml`.

- Fragments: the Velodyne HDL-64E scan of one keyframe (or 21 consecutive ones,
  `*_map.mm`), range limited to [1, 80] m and voxel decimated to 0.25 m, in one
  layer named `points`, in the frame of the (central) keyframe.
- Reference poses: dataset ground truth at the keyframe times, refined by ICP
  between the fragments (corrections up to 1.5 m at some revisits). In the
  `gterr<N>` cases the ground truth is 3.7-6.6 m off: their reference comes from
  ICP alone, which converges to the same pose from the ground truth and from the
  loop a mapper accepted (`gt_pose` keeps the original ground truth).
- Keyframes and initial guesses come from MOLA LiDAR-only odometry, so the roll
  and pitch of `global_odometry_pose` and `local_odometry_pose` are estimated,
  not absolute (they drift little on these mostly level roads).
- There are no `wrong_match` cases: every loop accepted in the source runs that
  disagreed with the ground truth turned out to be a ground truth error.

## License

CC BY-NC-SA 3.0 (`LICENSE`), as the original dataset: attribution,
non-commercial use only, and adaptations under the same license. These files
are an adaptation of it (cropped, decimated, re-encoded).

## Original authors

Project website: https://www.cvlibs.net/datasets/kitti/eval_odometry.php

Citation:

```
@INPROCEEDINGS{Geiger2012CVPR,
  author = {Andreas Geiger and Philip Lenz and Raquel Urtasun},
  title = {Are we ready for Autonomous Driving? The KITTI Vision Benchmark Suite},
  booktitle = {Conference on Computer Vision and Pattern Recognition (CVPR)},
  year = {2012}
}
```

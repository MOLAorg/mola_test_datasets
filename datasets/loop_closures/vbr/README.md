# Loop closure cases from VBR

Single LiDAR scans and small local maps cut from the 8 VBR training sequences
(campus_train0/1, ciampino_train0/1, colosseo_train0, diag_train0,
pincio_train0, spagna_train0), with the relative pose between them, for unit
tests of loop closure registration. Cases and file format: `cases.yaml`.

- Fragments: the Ouster OS0-128 scan of one keyframe (or 21 consecutive ones,
  `*_map.mm`), de-skewed, range limited to [1, 80] m and voxel decimated to
  0.25 m, in one layer named `points`, in the frame of the (central) keyframe.
- Reference poses: dataset ground truth at the keyframe times, refined by ICP
  between the fragments. ICP corrections are typically 0.1-0.4 m and 0.5-2 deg,
  consistent with a lever arm between the ground truth and LiDAR frames.
- Keyframes and initial guesses come from MOLA LiDAR-inertial odometry; the
  wrong solutions were returned by loop closure registration in those runs.

## License

CC BY-SA 4.0 (`LICENSE`), as the original dataset. These files are an
adaptation of it (cropped, decimated, re-encoded), and they are distributed
under the same license, with permission confirmed by the dataset authors.

## Original authors

Project website: https://rvp-group.net/ , devkit: https://github.com/rvp-group/vbr-devkit

Citation:

```
@inproceedings{brizi2024vbr,
  title     = {VBR: A Vision Benchmark in Rome},
  author    = {Brizi, Leonardo and Giacomini, Emanuele and Di Giammarino, Luca and Ferrari, Simone and Salem, Omar and De Rebotti, Lorenzo and Grisetti, Giorgio},
  booktitle = {IEEE International Conference on Robotics and Automation (ICRA)},
  year      = {2024}
}
```

# Base Model and Interface Layer

English | [中文](./README.zh-CN.md)

---

![Cover](./image/cover.gif)


This layer contains the lowest-level shared definitions used by the chassis stack: the robot model, frame layout, ros2_control resource description, and custom ROS 2 services.

## Packages

- `swerve_description`: URDF/Xacro model, sensor mounting frames, RViz assets, and ros2_control hardware resource description for the 4-wheel 4-steer chassis.
- `interface`: ROS 2 service definitions for map saving, pose saving, map refinement, validity checks, and relocalization.

## Boundary

This layer describes what the robot is and what cross-package service contracts exist. It does not implement motor drivers, controllers, SLAM, navigation, or simulation behavior.

## Main Conventions

- Body frame: `base_link`; planar projection: `base_footprint`.
- Module order: `fl`, `fr`, `bl`, `br`.
- Steering joints: `<prefix>_steering_joint`.
- Drive joints: `<prefix>_wheel_joint`.
- MID-360 frames: `mid360_link`, `livox_frame`.
- D435-compatible frames expose both `d435_*` and `camera_*` names.
- Current geometry baseline: wheelbase 0.42 m, track width 0.52 m, wheel radius 0.075 m.

This layer is normally launched indirectly by the bringup layer.

## License

This package is licensed under Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License (CC BY-NC-SA 4.0).

Copyright (c) 2026 Chengdu Changshu Robot Co., Ltd.

For details, please refer to the [LICENSE](LICENSE) file or visit: http://creativecommons.org/licenses/by-nc-sa/4.0/

## Acknowledgments

This package is part of the OpenFlex full-body humanoid robot platform ecosystem, developed specifically for research and industrial applications in the humanoid robotics field.

---

## 📞 Contact Us

### Chengdu Changshu Robot Co., Ltd.
**Chengdu Changshu Robotics Co., Ltd.**

| Contact | Information |
|---------|-------------|
| 📧 Email | openarmrobot@gmail.com |
| 📱 Phone/WeChat | +86-17746530375 |
| 🌐 Website | https://openarmx.com/ |
| 🌐 Docs | http://docs.openarmx.com/ |
| 📍 Address | Tianjin Xiqing District · Daochao Robot Experience Base (City of Tomorrow) · Tianjin Humanoid Robot Center |
| 👤 Contact Person | Mr. Wang |

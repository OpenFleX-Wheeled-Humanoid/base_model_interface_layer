# interface

English | [中文](./README-CN.md)

---

ROS 2 service interface definitions for the swerve navigation system.

## Description

This package provides custom service definitions used across the swerve chassis navigation stack (mapping, relocalization, and map management).

## Service Definitions

| Service | Request | Response | Purpose |
|---------|---------|----------|---------|
| `SaveMaps.srv` | `string file_path`, `bool save_patches` | `bool success`, `string message` | Save map data to file |
| `Relocalize.srv` | `string pcd_path`, `float32 x/y/z/yaw/pitch/roll` | `bool success`, `string message` | Trigger relocalization with initial pose hint |
| `IsValid.srv` | `int32 code` | `bool valid` | Query validity status by code |
| `RefineMap.srv` | `string maps_path` | `bool success`, `string message` | Refine an existing map |
| `SavePoses.srv` | `string file_path` | `bool success`, `string message` | Save pose data to file |

## Build

```bash
cd ~/openflex_all/openflex_ws
colcon build --packages-select interface
source install/setup.bash
```

## Usage

After building, you can use these service types in other ROS 2 packages:

```cpp
#include "interface/srv/save_maps.hpp"
#include "interface/srv/relocalize.hpp"
```

```python
from interface.srv import SaveMaps, Relocalize, IsValid, RefineMap, SavePoses
```

## Dependencies

- `std_msgs`
- `rosidl_default_generators` / `rosidl_default_runtime`

## License

MIT

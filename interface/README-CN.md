# interface

[English](./README.md) | 中文

---

舵轮导航系统 ROS 2 服务接口定义包。

## 简介

本包提供舵轮底盘导航栈（建图、重定位、地图管理）所使用的自定义服务定义。

## 服务定义

| 服务 | 请求 | 响应 | 用途 |
|------|------|------|------|
| `SaveMaps.srv` | `string file_path`, `bool save_patches` | `bool success`, `string message` | 保存地图数据到文件 |
| `Relocalize.srv` | `string pcd_path`, `float32 x/y/z/yaw/pitch/roll` | `bool success`, `string message` | 以初始位姿提示触发重定位 |
| `IsValid.srv` | `int32 code` | `bool valid` | 通过编码查询有效性状态 |
| `RefineMap.srv` | `string maps_path` | `bool success`, `string message` | 精化现有地图 |
| `SavePoses.srv` | `string file_path` | `bool success`, `string message` | 保存位姿数据到文件 |

## 编译

```bash
cd ~/openflex_all/openflex_ws
colcon build --packages-select interface
source install/setup.bash
```

## 使用方式

编译后，可在其他 ROS 2 包中使用这些服务类型：

```cpp
#include "interface/srv/save_maps.hpp"
#include "interface/srv/relocalize.hpp"
```

```python
from interface.srv import SaveMaps, Relocalize, IsValid, RefineMap, SavePoses
```

## 依赖

- `std_msgs`
- `rosidl_default_generators` / `rosidl_default_runtime`

## 许可证

MIT

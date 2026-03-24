# Point-LIO-ROS2

原仓库：https://github.com/hku-mars/Point-LIO

ROS2版仓库：https://github.com/dfloreaa/point_lio_ros2

基于 dfloreaa / point_lio_ros2 增加了对 Livox HAP 通过 livox_ros_driver2 发布的 PointCloud2 点云格式（PointXYZRTLT）的支持。

## 构建

```bash
mkdir -p point_lio/src
cd point_lio/src
git clone https://github.com/Franklif1/point_lio_ros2.git
cd ..
colcon build --symlink-install
```

- 构建前请先 source livox_ros_driver2

## 运行

```bash
source install/setup.bash
#ros2 launch point_lio mapping_pointsraw.launch.py
ros2 launch point_lio mapping_hap.launch.py
```


**保存点云pcd文件：**
将 yaml 文件中的 pcd_save_enable 设置为 1 。Point-LIO 终止后，所有扫描（在全局坐标系中）将被累积并保存到文件 Point-LIO/PCD/scans.pcd 中。 `pcl_viewer scans.pcd` 可以可视化点云。

关于 pcl_viewer 的提示：通过在 pcl_viewer 运行时按下键盘 1、2、3、4、5 来更改可视化/着色内容。


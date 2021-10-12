# VIO (Visual Inertial Odometry)

[ссылка на оригинальный проект VIO (Visual Inertial Odometry)](https://github.com/era-team/VIO)

Для корректной работы VIO px4 bridge необходимо выполнить предварительную устоновку пакетов для ROS и Ubuntu:

## 1. Перед запуском

1.1. Пакеты для ROS

   ```bash
   sudo apt-get install ros-kinetic-mavros ros-kinetic-mavros-extras
   ```

1.2. Пакеты geographiclib для Ubuntu

   ```bash
   wget https://raw.githubusercontent.com/mavlink/mavros/master/mavros/scripts/install_geographiclib_datasets.sh

   sudo bash ./install_geographiclib_datasets.sh   
   ```

> **Note** Подробная статья по настройке px4 и предстартовой подготовке находится на оффициальной странице [docs.px4.io](https://docs.px4.io/master/en/computer_vision/visual_inertial_odometry.html)

## 2. Запуск

2.1 Клонируем репозиторий
   ```bash
   cd ~/catkin_ws/src
   git clone https://github.com/Auterion/VIO.git
   ```

2.2 Производим сборку ROS узлов
   ```bash
   cd ~/catkin_ws/src
   catkin build px4_realsense_bridge
   ```
2.3 Запускаем px4 bridge

   ```bash
   cd ~/catkin_ws/src
   roslaunch px4_realsense_bridge bridge_mavros.launch
   ```
   
> **Важно!** Перед запуском дрона необходимо провести предстартовую проверку как указано на странице [docs.px4.io](https://docs.px4.io/master/en/computer_vision/visual_inertial_odometry.html) в разделе "Check/Verify VIO Estimate"
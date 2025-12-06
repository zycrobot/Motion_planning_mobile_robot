# Motion_planning_mobile_robot
ROS c++ code for mobile robot

## TODO

- convex optimazition for swarm 
- basic framework for trajectory/motion planning
- final project

# 移动机器人运动规划

## 项目简介

本仓库包含移动机器人运动规划课程的完整学习资料和实践代码。该项目涵盖了从基础导论到高级局部规划的全面内容，旨在帮助学习者系统掌握移动机器人路径规划和轨迹生成的核心算法与实现技术。

## 项目特点

- **系统性学习**：按章节组织的完整课程内容，从基础到高级
- **理论与实践结合**：每章包含PPT理论讲解和对应的代码实现
- **多种规划算法**：覆盖搜索算法、采样算法、动力学约束规划等
- **ROS环境开发**：基于机器人操作系统(ROS)的实际开发环境
- **可视化工具**：集成RViz等可视化工具，便于算法调试和结果展示

## 技术栈

- **主要编程语言**：C++
- **开发框架**：ROS (Robot Operating System)
- **辅助工具**：MATLAB (部分章节)
- **优化库**：OSQP (用于模型预测控制)
- **可视化工具**：RViz

## 目录结构

```
├── 1_导论/                # 课程介绍和环境搭建
│   ├── hw_1/              # 第一章作业
│   └── ppt/               # 课程PPT和环境配置文档
├── 2_基于搜索的路径规划/     # 搜索类路径规划算法
│   ├── CODE/              # 源代码实现
│   └── ppt/               # 算法理论讲解
├── 3_基于采样的路径规划/     # 采样类路径规划算法
│   ├── mycode/            # 源代码实现
│   └── ppt/               # 算法理论讲解
├── 4_动力学约束的路径规划/    # 考虑机器人动力学的路径规划
│   ├── mycode/            # 源代码实现
│   └── ppt/               # 算法理论讲解
├── 5_最优轨迹的生成/        # 轨迹优化生成技术
│   ├── mycode/            # 源代码实现
│   └── ppt/               # 算法理论讲解
├── 6_模型预测控制与运动规划/   # MPC控制算法
│   ├── mycode/            # 源代码实现
│   └── ppt/               # 算法理论讲解
├── 7_集群机器人运动规划/      # 多机器人协调规划
│   └── L7*                # 课程PPT和论文资料
├── 8_移动机器人局部规划：经典框架及案例/ # 局部规划框架
│   └── L8*.pdf            # 课程PPT
└── README.md              # 项目说明文档
```

## 各章节内容概述

### 1. 导论
- 课程介绍和学习路径
- 开发环境准备（Ubuntu + ROS）
- 基础概念介绍

### 2. 基于搜索的路径规划
- A*算法及其变体
- Dijkstra算法
- 栅格地图表示
- 搜索算法在ROS中的实现

### 3. 基于采样的路径规划
- RRT (Rapidly-exploring Random Tree)
- RRT*算法
- PRM (Probabilistic Roadmap)
- 采样策略优化

### 4. 动力学约束的路径规划
- 机器人运动学模型
- 动力学约束条件
- 考虑约束的路径生成

### 5. 最优轨迹的生成
- 轨迹优化理论
- 基于优化的路径平滑
- 时间分配和速度规划

### 6. 模型预测控制与运动规划
- MPC基本原理
- 基于OSQP的优化求解
- 车辆运动控制实现

### 7. 集群机器人运动规划
- 多机器人协作理论
- 分布式规划算法
- 集群行为协调

### 8. 移动机器人局部规划：经典框架及案例
- Fast Planner等经典框架
- 前端路径搜索
- 后端轨迹优化
- 实际应用案例分析

## 环境配置

### 推荐开发环境
- **操作系统**：Ubuntu 18.04 / 20.04
- **ROS版本**：Melodic / Noetic
- **编译器**：GCC 7.5+
- **开发工具**：VSCode / CLion

### 安装步骤
1. 安装Ubuntu操作系统
2. 按照ROS官方文档安装对应版本的ROS
3. 安装依赖包：
   ```bash
   sudo apt-get install ros-${ROS_DISTRO}-navigation
   sudo apt-get install ros-${ROS_DISTRO}-robot-state-publisher
   sudo apt-get install ros-${ROS_DISTRO}-rviz
   ```
4. 克隆本仓库到工作空间
5. 编译工作空间：
   ```bash
   cd ~/catkin_ws
   catkin_make
   source devel/setup.bash
   ```

## 使用指南

### 运行示例代码
以第二章基于搜索的路径规划为例：

```bash
# 启动ROS Master
source ~/catkin_ws/devel/setup.bash
roscore

# 在新终端中运行路径规划节点
roslaunch grid_path_searcher demo.launch

# 在RViz中可视化路径规划结果
rosrun rviz rviz -d $(rospack find grid_path_searcher)/launch/rviz-config.rviz
```

### 各章节代码使用
每个章节的代码包都有自己的README文档，详细说明了使用方法和参数配置。请参考各章节下的README文件获取特定算法的使用指南。

## 学习路径

### 推荐学习顺序
1. 先阅读各章节的PPT，了解算法理论基础
2. 分析对应章节的代码实现
3. 尝试运行示例，观察算法效果
4. 完成各章节的作业，加深理解
5. 尝试修改和扩展代码，实现自己的功能

### 学习建议
- 从基础章节开始，循序渐进
- 理论与实践结合，理解算法原理后再看代码
- 利用RViz等可视化工具观察算法运行过程
- 遇到问题时，可以参考助教分享的作业思路

## 未来工作计划

- [ ] 完善集群机器人的凸优化实现
- [ ] 构建轨迹/运动规划的基础框架
- [ ] 开发最终项目

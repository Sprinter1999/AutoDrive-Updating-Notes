# 《自动驾驶更新笔记 Autopilot Updating Notes》

![封面](./imgs/1.jpg)
### 重点
**由于作者水平有限，希望大家积极提交改进意见**, 您可对相关xxx.md进行修改,并将意见记录在modify_log.txt中。**我将对修改内容进行整理，确保文档的准确性**。

## 一、内容简介
随着各大科技公司积极布局，自动驾驶成为新的风口。本文旨在总结分享自动驾驶的技术方案，希望帮助大家对相关知识的学习了解。

## 二、自动驾驶分级（SAE 美国汽车工程协会）
![自动驾驶分级](./imgs/2.jpg)

## 三、架构
![架构](./imgs/3.jpg)
自动驾驶系统主要包含三部分：环境感知、决策规划以及运动控制。感知层对车辆周边环境进行感知识别，用于获取环境信息；决策层充当人类驾驶员的角色，主要解决三个核心问题：“我在哪？我要去哪？我该如何去？”；控制层保证各项硬件系统稳定的运行在计算好的最佳设定值上；保证各项子系统的运行维持在最优的区间范围；规避可能性风险，精准调控至最佳路径。


## 四、目录

**1.基础** \
|-- 1.1 知识铺垫 \
|---- [1.1 Frenet坐标系](./ch01_%E5%9F%BA%E7%A1%80/1.1%20%E7%9F%A5%E8%AF%86%E9%93%BA%E5%9E%AB/1.1.1%20Frenet%E5%9D%90%E6%A0%87%E7%B3%BB.md) \
|---- [1.1.2 卡尔曼滤波-KalmanFilter](./ch01_%E5%9F%BA%E7%A1%80/1.1%20%E7%9F%A5%E8%AF%86%E9%93%BA%E5%9E%AB/1.1.2%20%E5%8D%A1%E5%B0%94%E6%9B%BC%E6%BB%A4%E6%B3%A2-KalmanFilter.md) \
|-- 1.2 数据集 \
|---- [1.2.1 Argoverse](./ch01_%E5%9F%BA%E7%A1%80/1.2%20%E6%95%B0%E6%8D%AE%E9%9B%86/1.2.1%20Argoverse.md) \
[**2. 硬件**](./ch02_%E7%A1%AC%E4%BB%B6/README.md) \
|-- [2.1 传感器](./ch02_%E7%A1%AC%E4%BB%B6/2.1%20%E4%BC%A0%E6%84%9F%E5%99%A8/README.md) \
|---- [2.1.1 摄像头](./ch02_%E7%A1%AC%E4%BB%B6/2.1%20%E4%BC%A0%E6%84%9F%E5%99%A8/2.1.1%20%E6%91%84%E5%83%8F%E5%A4%B4.md) \
|---- [2.1.2 激光雷达](./ch02_%E7%A1%AC%E4%BB%B6/2.1%20%E4%BC%A0%E6%84%9F%E5%99%A8/2.1.2%20%E6%BF%80%E5%85%89%E9%9B%B7%E8%BE%BE.md) \
|---- [2.1.3 毫米波雷达](./ch02_%E7%A1%AC%E4%BB%B6/2.1%20%E4%BC%A0%E6%84%9F%E5%99%A8/2.1.3%20%E6%AF%AB%E7%B1%B3%E6%B3%A2%E9%9B%B7%E8%BE%BE.md) \
|---- [2.1.4 超声波雷达](./ch02_%E7%A1%AC%E4%BB%B6/2.1%20%E4%BC%A0%E6%84%9F%E5%99%A8/2.1.4%20%E8%B6%85%E5%A3%B0%E6%B3%A2%E9%9B%B7%E8%BE%BE.md) \
|---- [2.1.5 GPS定位导航](./ch02_%E7%A1%AC%E4%BB%B6/2.1%20%E4%BC%A0%E6%84%9F%E5%99%A8/2.1.5%20GPS%E5%AE%9A%E4%BD%8D%E5%AF%BC%E8%88%AA.md) \
|---- [2.1.6 IMU惯性传感器](./ch02_%E7%A1%AC%E4%BB%B6/2.1%20%E4%BC%A0%E6%84%9F%E5%99%A8/2.1.6%20IMU%E6%83%AF%E6%80%A7%E4%BC%A0%E6%84%9F%E5%99%A8.md) \
|-- [2.2 计算设备](./ch02_%E7%A1%AC%E4%BB%B6/2.2%20%E8%AE%A1%E7%AE%97%E5%8D%95%E5%85%83/README.md) \
|-- 2.3 辅助单元 \
|---- [2.3.1 V2X](./ch02_%E7%A1%AC%E4%BB%B6/2.3%20%E8%BE%85%E5%8A%A9%E5%8D%95%E5%85%83/2.3.1%20V2X.md) \
|---- [2.3.2 黑匣子](./ch02_%E7%A1%AC%E4%BB%B6/2.3%20%E8%BE%85%E5%8A%A9%E5%8D%95%E5%85%83/2.3.2%20%E9%BB%91%E5%8C%A3%E5%AD%90.md) \
**3. 感知** \
|-- 3.1 2D目标检测 \
|-- 3.2 3D目标检测 \
**4.预测** \
|-- 4.1 基于车道序列的预测 \
**5. 策略规划** \
|-- 5.1 路线规划 \
|-- 5.2 轨迹规划 \
|-- 5.2.1 笛卡尔坐标下的规划 \
|-- 5.2.2 Lattice规划 \
**6. 控制** \
|-- 6.1 PID控制 \
|-- 6.2 线性二次调节器（LQR）\
|-- 6.3 模型控制预测（MPC）\
[**7. ADAS**](./ch07_ADAS/README.md)




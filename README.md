# 🏆 2025年全国大学生光电设计竞赛 - 赛题A：激光对抗小车

> **硬件平台**: Jetson Orin Nano / NX  
> **核心组件**: PCA9685A 驱动舵机、12mm 长焦摄像头  
> **软件优化**: 包含原始代码 (224.py) 及 Claude 分块优化版本

---

<h1>🚩 第 1 部分 研究目标</h1>

<h2>1. 总体目标</h2>
[cite_start]<h3>设计并实现一套基于智能车的激光对抗系统，使智能车能够在竞赛场地中准确识别对手并进行有效“攻击”，同时具备避障能力 [cite: 20]。</h3>

<h2>1.1 功能目标</h2>
<ul>
  [cite_start]<li><h3><b>快速识别</b>：探测距离 ≥ 5 米，覆盖范围达到 180° [cite: 22]。</h3></li>
  [cite_start]<li><h3><b>高效躲避</b>：2 秒内完成转向/加减速动作，成功率 ≥ 80° [cite: 23]。</h3></li>
</ul>

<h2>1.2 性能目标</h2>
<ul>
  [cite_start]<li><h3><b>机动性</b>：直线速度 ≥ 1.5m/s，转弯速度 ≥ 1m/s [cite: 25]。</h3></li>
  [cite_start]<li><h3><b>稳定性</b>：系统功耗控制在 30W 以内，持续运行 20 分钟以上 [cite: 26]。</h3></li>
</ul>

---

<h1>🛠️ 第 2 部分 研究方案</h1>

<h2>1. 目标跟踪打击系统</h2>
[cite_start]<h3>通过 YOLOv5 配合 1000 张样本训练，实现在 6 米内精准识别 [cite: 31][cite_start]。利用交互式多模型 (IMM) 与卡尔曼滤波，在目标丢失时主动预测跟踪 [cite: 35]。</h3>

<h2>2. 路径规划与通信</h2>
[cite_start]<h3>基于 STM32 + MPU6050 实时控制方向 [cite: 39][cite_start]。Jetson 使用 Python struct 库传输数据，配合 UART 中断提高响应效率 [cite: 41]。</h3>

---

<h1>🔬 第 3 部分 技术路线及可行性分析</h1>
<h3>1. [cite_start]硬件支撑：市面成熟的半导体激光器与底控芯片完全满足设计要求 [cite: 47]。</h3>
<h3>2. [cite_start]软件基础：YOLOv5 与路径规划算法已有成熟实践经验 [cite: 48]。</h3>

---

<h1>⚠️ 第 4 部分 拟解决的关键问题</h1>
<h3>1. [cite_start]运动目标的精准识别：改进信号处理算法以提升复杂环境下的准确率 [cite: 52]。</h3>
<h3>2. [cite_start]硬件连接优化：采用 TTL-USB 转接方式解决引脚连接需求，增强抗干扰能力 [cite: 63]。</h3>

---

---

<img width="2284" height="1157" alt="image" src="https://github.com/user-attachments/assets/121d1c7b-e952-443a-a5c1-ba97f174f48f" />
<img width="2366" height="1305" alt="image" src="https://github.com/user-attachments/assets/45ba5d87-509d-4858-b25b-737ca382dc49" />
<img width="2366" height="1305" alt="image" src="https://github.com/user-attachments/assets/dac564e3-e907-4c05-97e2-df104101bc8c" />




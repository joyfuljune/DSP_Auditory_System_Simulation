<h1><align='center'>人耳听觉系统仿真实验一 —— 外耳和中耳滤波器设计</align></h1>

<h3>目录</h3>

- [人耳听觉系统简介](#人耳听觉系统简介)  
- [外耳和中耳模型](#外耳和中耳模型)  
- [零极点和频谱](#零极点和频谱)
- [实验内容](#实验内容)


## 人耳听觉系统简介

<div align="center">
  <img src="https://hearinghealthmatters.org/wp-content/uploads/2017/03/featurd-2023-07-08T140848.184.jpg" width="600" height="300">
</div>

我们人类的耳朵是复杂的听觉器官，让我们能够听到声音，从而沟通和感知世界。耳朵的构造包括外耳、中耳和内耳，每个部分都扮演着关键的角色：

**外耳** 是我们耳朵的可见部分，包括耳廓和外耳道。耳廓帮助收集来自环境的声音，然后将声音引导到外耳道。外耳道是一条通向内耳的管道。

**中耳** 包括鼓膜、听小骨链和鼓室。声音从外耳道传递到鼓膜，引起鼓膜振动。这些振动随后传递到三块小骨：锤骨、砧骨和副锤骨，它们组成了听小骨链。中耳的任务是将声音从外耳传递到内耳。

**内耳** 包括耳蜗和前庭。耳蜗是一个螺旋状的器官，内含听觉感受器细胞。当听小骨链传递振动到内耳时，液体在耳蜗内开始波动。这些液体波动刺激听觉感受器细胞，导致它们产生电信号。

整个听觉系统工作在协调一致的过程中，将声音从外部世界传递到我们的大脑，让我们能够感知和理解声音的来源和内容。这个复杂的结构和机制使我们能够欣赏音乐、交流和感知周围环境中的声音。

同学们可通过以下视频（或自行搜索）了解更多关于耳朵的信息，本次实验的重点关注“外耳”以及“中耳”部分。

![视频资料：人耳系统3d动画](https://github.com/joyfuljune/DSP_Auditory_System_Simulation/blob/main/Human%20ear%20-%20structure%20working%20Sound%20Physics%20Khan%20Academy%20(1).mp4)

## 外耳和中耳模型
### 外耳
外耳包括耳廓和耳道，它有以下主要功能：

- 声波反射和减弱：外耳的形状帮助反射和减弱来自周围环境的声波，以便它们更好地进入内耳。

- 声音放大：耳道是一个管道，可以将声音放大，使声音更清晰可闻。

以下是外耳相关数值和其说明：

1. 外耳长度（L）：大约2.8 cm。这个数值表示了外耳的尺寸。

2. 外耳道直径：7 mm。这是耳道的宽度，它对声音进入的方式有影响。

3. 声音传播速度（c）：340.3 m/s。这是声音在外耳道中的传播速度。

4. 耳道的共振频率（f）：3038 Hz。这是耳道内声音共振的频率，它影响了声音的清晰度。

5. 外耳最敏感频率：大约3000 Hz。这是人类外耳对声音的最敏感频率，这意味着我们在这个频率下能够更容易地听到声音。

6. 外耳为鼓膜提供的增益：约20 dB。这是外耳的声音放大作用，它帮助声音更清晰地传达到鼓膜。

举个例子，当我们听到高音乐器的声音时，外耳可以更好地捕捉和传递这些高频声音，使它们在我们的内耳中变得更明显。外耳的形状和尺寸在这一过程中起着关键作用。

### 中耳
中耳是人耳的一个关键部分，它具有将声波传递到内耳的重要功能。

- 中耳通过两个微小的骨头，锤骨（malleus）和砧骨（incus），将鼓膜振动转化为砧骨的运动，从而传递声音信号。
- 这是一个关键的过程，有助于声音的传导和放大。

以下是中耳相关数值和其说明：

1. 鼓膜和耳蜗之间的压力差： 声音波动在鼓膜上产生压力，然后将这些压力传递到内耳的耳蜗上。值得注意的是，声音波在耳蜗上的压力大约是在鼓膜上的25倍。这意味着声音波在进入内耳前经过了一个非常重要的放大过程。

2. 声音强度与压力平方的关系： 声音强度（I）与压力的平方成正比。这是声音传导的一个基本物理原理。具体来说，声音强度与压力的平方成正比，即 $I ∝ P^2$ 。因此，如果声音波在中耳中经历25倍的压力增加，那么声音强度将增加625倍。

3. 声音强度增加和分贝（dB）： 625倍的声音强度增加相当于约28分贝的增加。分贝是一种用于描述声音强度的单位，通常用于测量声音的响度。这个增加说明了中耳在声音传导中的重要作用，确保声音足够强，以便我们能够听到和理解来自外界的声音。

4. 中耳的能量转化： 中耳不仅将声音转化为机械运动，还将机械能量转化为液体能量，进一步将声音信号传递到内耳的耳蜗。这个多层次的转化过程确保了声音在内耳中得以处理和解释，以便我们能够感知和理解来自外界的声音。

综上所述，中耳在听觉传导中扮演着至关重要的角色，通过将声音波的压力增加和能量转化，确保了我们能够有效地感知和理解外界的声音。这些数值和过程的理解有助于我们更好地理解听觉系统的工作原理和声音传导的重要性。

## 实验内容



### A - 中耳滤波器模型：

根据图1，中耳可以被建模为两个复数零点对（用于去除非常高和非常低频率）和一个复数极点对（提供中等频率上的低Q增益）。

- 使用数字信号处理的知识，在Z平面选择合适的零点和极点以创建中耳滤波器的传递函数，使其近似图中中耳滤波器频率响应图。

- 编写MATLAB脚本来创建中耳滤波器的传递函数，并验证其频率响应。这可以通过使用MATLAB内置函数或者自定义函数来实现。确保选择适当的极点和零点位置以匹配理论描述中的中耳模型。

- 使用MATLAB绘制频率响应图表，以确认中耳滤波器的效果。

### B - 外耳模型与中耳级联：

- 使用相同的方法，将外耳模型的零点和极点适当地放置在Z平面上，以创建外耳模型的传递函数。

- 将中耳滤波器和外耳模型级联，得到整体的传递函数。

- 使用MATLAB编写脚本来计算级联滤波器的频率响应，并与问题描述中的图表进行比较。

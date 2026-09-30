# 镜头语言

适用：运镜选择、构图描述、运动失败诊断。依据 S1–S3，来源见 [sources.md](sources.md)。

## 先区分景别、角度、运动

景别描述画面范围；角度描述观察位置；运镜描述相机如何移动。三者可以组合，但不是同一类指令。

| 类型 | 术语 | 使用方式 |
| --- | --- | --- |
| 景别 | extreme wide shot / wide shot / medium wide shot | 建立空间、显示全身与环境关系 |
| 景别 | medium shot / medium close-up / close-up / extreme close-up | 从动作互动到脸部、手部或物体细节 |
| 角度 | eye level / low-angle / high-angle | 与景别组合，例如 `low-angle medium shot` |
| 俯视构图 | overhead view | 指定从上方观察，不等同于起重机运动 |
| 肩后构图 | over-the-shoulder | 给出前景人物和被观看主体，避免说话者混淆 |
| 建立镜头 | wide establishing shot | 强调地点和主体的空间关系 |

## 官方公布的相机词汇

下列英文词汇来自官方指南；“如何描述”列是本 Skill 的操作性解释，不是性能保证。

| 术语 | 含义与如何描述 |
| --- | --- |
| follows | 跟随主体；说明从后方、前方还是侧面跟随 |
| tracks | 随主体移动或横向移动；写明相对位置、相机高度和主体在画面中的位置 |
| pans across | 相机转动扫过场景；说明扫过什么、向哪边、最终停在谁身上 |
| circles around | 绕主体移动；说明从哪个视角到哪个视角，短镜头可用小幅弧线 |
| tilts upward | 镜头向上转动；说明由底部什么内容揭示到顶部什么内容 |
| pushes in | 相机向主体靠近；说明最终景别、主体占画面的位置和背景 |
| pulls back | 相机后退；说明最终揭示的环境以及主体在其中的大小 |
| handheld movement | 手持机位的运动风格；说明跟随方式和幅度，不等同于一定剧烈摇晃 |
| static frame | 固定构图；让主体动作推进画面 |

优先使用已公布的词汇，避免只用含糊同义词。`overhead view`、`over-the-shoulder`、`wide establishing shot` 同样在官方 Camera Language 列表里，但属于视角/构图，不能当作运动路径。

`pushes in` 是机位向前移动，不是光学 `zoom in`；`pans across` 是转动观察方向，不是横向 `tracks`。用户明确需要变焦或其他电影术语时，可以保留准确术语，不要擅自换成另一种物理运动。

## 给运动一个终点

写清：何时开始、相对谁移动、速度/幅度，以及结束后主体如何出现在画面里。

弱：`The camera pushes in.`

更具体的自编示例：

```text
The camera pushes in toward the watchmaker as she raises the open watch; as the move settles, her hands fill the lower half of frame and her face remains visible above them against the softly lit workbench.
```

主体调度放在动作描述里：`She moves from the left third of frame to the center, then turns toward the doorway.` 相机描述则说明机位如何响应。不要让主体和相机被同一句含糊的“向左移动”混淆。

## 运动复杂度与镜头连续性

默认每镜头一个主运动。短片段内叠加平移、推近、环绕和变焦会挤压完成时间。用户需要连续复合运动时，明确顺序和停顿，确认可用时长；需要独立构图则使用多镜头，并在切镜后重新建立机位。

从远景持续推近到近景仍可以是一镜到底；这不同于把两个未解释的景别标签堆在同一开场描述里。

对于参考视频驱动的精确运动，读取 [workflows.md](workflows.md) 的“参考运动与适配器”。纯文字描述不保证可重复的相机轨迹。

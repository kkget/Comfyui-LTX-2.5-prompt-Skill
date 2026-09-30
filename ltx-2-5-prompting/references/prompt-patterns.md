# 六要素与场景结构

适用：普通文生视频、提示词改写、对白场景、多镜头。来源编号见 [sources.md](sources.md) 的 S1、S2。

## 六要素

| 要素 | 应写出的内容 | 常见修正 |
| --- | --- | --- |
| Establish the Shot | 景别、角度、镜头类型或视觉类别 | 用 `medium close-up, eye level` 代替只有 `cinematic` |
| Set the Scene | 地点、时间、光照、色彩、材质、天气/氛围 | 把“高级感”落实为可见光线、表面和配色 |
| Describe the Action | 主动作、先后顺序、停顿、画面内位置变化 | 给静态描述添加实际发生的行为 |
| Define the Character(s) | 必要的年龄、发型、衣着、特征、身体表情 | 无人物镜头描述物体；重复主体使用相同识别特征 |
| Identify Camera Movement(s) | 相对主体的方向、开始时机、速度与结束构图 | 运镜词之后写清最终画面；不要把变焦当作移动机位 |
| Describe the Audio | 环境声、音效、音乐、说话者和引号对白 | 说明声源和延续关系；用户要静音时保留静音 |

这是一种信息组织顺序，而不是参数语法。使用一个流畅段落，避免把表格字段原样送入模型。只加入对当前镜头有用的细节，特写可以强调眼神、手部、材质，远景侧重空间与主体动作。

同一镜头的光源应互相解释得通。混合光源并非一律禁止，例如室内钨丝灯配合窗外冷光可以成立；避免同时要求互相矛盾的时间、阴影方向和色温。

## 单镜头

按“开场画面 -> 主体动作 -> 镜头响应 -> 结束画面 -> 声音”检查时间线。默认约 4–8 句是建议，不是上下限。

以下是写作模板，交付时替换全部占位符并合并成自然段：

```text
A [shot scale and angle] frames [subject] in [setting]. [Coherent light, palette, and relevant texture]. [Subject performs a concrete action, then a second beat if time permits]. [Stable identifying details and physical emotion cues]. The camera [documented movement] relative to [subject]; as the move settles, [final composition]. [Ambient sound, music, and any quoted dialogue or explicit silence].
```

描述运动时用现在时。`She pauses, takes a breath, then opens the door` 给出了可执行的节拍；`a thoughtful atmosphere` 没有说明发生什么。

## 剧本式对白场景

适用于用户需要对白、角色提示和明确节拍的场景。场景头不自动意味着切镜：连续镜头要明确说明，发生切镜则仍需自然语言转场。

```text
INT. REPAIR SHOP - AFTERNOON
A continuous medium shot frames a technician at a workbench under a single overhead task light. She lifts a repaired pocket watch, closes its cover, and turns toward the customer just off-screen.
Technician, speaking softly in English: "It is running again."
She pauses and places the watch on the counter. The camera remains in a static frame as her fingers release the chain. A steady clock tick and the small click of the cover are audible; there is no music.
```

这是本 Skill 自编示例。多角色对白应清楚标注谁说哪句、谁在画面内，减少同时说话；普通生成的多角色能力不要与 Dub-It 的单说话者限制混淆。

## 多镜头

每次切镜至少覆盖：

1. **转场**：例如 `A hard cut transitions to...`、`A match cut connects...`、`The image dissolves into...`。
2. **新构图**：重新写景别、角度、画面里的主体，光照改变时说明原因。
3. **身份/空间连续**：同一人物继续使用相同衣着和外观标识，保持视线和动作关系；时间或地点跳转要解释。
4. **声音关系**：说明音乐、环境声、对白是延续、变轻、停止还是换成新声场。

通常 2–4 镜头较易保持清晰。每镜头承担一个明确任务，例如建立环境、展示细节、给出反应。不是每个镜头都需要对白或运动。

```text
A [wide establishing shot] shows [subject and setting] as [action]; [audio]. A hard cut transitions to a [new scale and angle] of [the same identified subject] as [next beat]; [what sound continues or changes]. A match cut connects [a matching visible shape or motion] to [the next framing and subject], where [final action]; [final audio state].
```

匹配剪辑要有实际对应的形状或动作。不要仅添加 `match cut` 却没有可匹配的画面。

## 诊断与改写

| 观察到的问题 | 优先修改 |
| --- | --- |
| 人物几乎不动 | 用走、转身、伸手、呼气等具体动作替换纯外观描述 |
| 运镜结果模糊 | 给出相对主体的位置变化和最终构图，保留一个主运镜 |
| 切镜没有发生 | 把裸镜头编号改成明确的自然语言切镜 |
| 人物跨镜头变装 | 复用外观标识；明确解释有意的时间跳转 |
| 声音在切镜处中断 | 逐次声明音乐、环境声或对白是否继续 |
| 节拍过快、对白被挤压 | 减少动作/台词或增加允许时长，把必要停顿写进正文 |
| 来自其他模型的标签提示词效果差 | 保留画面意图，移除未验证标签，重写成 LTX 的连续描述 |

优先解决影响最大的冲突；不要为了“优化”重写用户已经明确而合理的设计。

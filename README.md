# LTX-2.5 Prompting Skill

一个面向 LTX-2.5 的视频提示词 Skill，依据 LTX 官方指南，将创意、已有提示词或画面参考整理成可直接使用的自然语言提示词。

适合为 ComfyUI、LTX 本地管线及其他已确认支持 LTX-2.5 的生成入口准备提示词。本项目是独立整理的 Agent Skill，不是 LTX 官方发布的 Skill，也不是 ComfyUI 自定义节点。

## 适用场景

| 场景 | 提供的帮助 |
| --- | --- |
| 文生视频 | 将创意组织成包含画面、动作、运镜与声音的提示词 |
| 首帧图生视频 | 根据实际首帧描述后续动作，保持主体、构图与光照一致 |
| 连续单镜头 | 明确动作顺序、主运镜和结束构图 |
| 多镜头与对白 | 描述切镜、人物连续性、停顿和声音衔接，保留目标语言台词 |
| 提示词诊断与迁移 | 修正动作不清、运镜冲突、切镜缺失等问题，改写其他视频模型的提示词 |
| 已有视频配音与编辑 | 为 Dub-It 和 Video Editing 提供对应的提示词格式与边界说明 |
| 工作流适配 | 按需解释 Prompt Enhancer、参考运动及已知参数约束 |

本 Skill 负责提示词写作和已知工作流的适配，不负责安装模型、配置 ComfyUI、下载权重或自动执行视频生成。具体节点、接口和模型兼容性以实际工作流为准。

## 安装

### 前提

使用支持 Skills 的 Codex 环境，并下载或克隆本仓库。Skill 本身由 Markdown 和 YAML 文件组成，无需安装 Python、Node.js 或额外依赖。

以下命令均在本仓库根目录执行，适用于 Windows PowerShell。选择用户级或项目级安装即可。

### 用户级安装

将 Skill 安装到当前用户的 `.agents/skills`，供该用户的不同项目使用：

```powershell
$skillTarget = Join-Path $HOME '.agents/skills/ltx-2-5-prompting'
New-Item -ItemType Directory -Path $skillTarget -Force | Out-Null
Copy-Item -LiteralPath './ltx-2-5-prompting/SKILL.md', './ltx-2-5-prompting/agents', './ltx-2-5-prompting/references' -Destination $skillTarget -Recurse -Force
```

命令会更新目标目录中的同名文件；如有自行修改的版本，请先备份。

### 项目级安装

将 Skill 放在需要使用它的项目根目录下的 `.agents/skills/ltx-2-5-prompting/`。下面的命令会安装到当前仓库：

```powershell
$skillTarget = Join-Path (Get-Location).Path '.agents/skills/ltx-2-5-prompting'
New-Item -ItemType Directory -Path $skillTarget -Force | Out-Null
Copy-Item -LiteralPath './ltx-2-5-prompting/SKILL.md', './ltx-2-5-prompting/agents', './ltx-2-5-prompting/references' -Destination $skillTarget -Recurse -Force
```

其他系统可将同样的 `SKILL.md`、`agents/` 和 `references/` 放入 `~/.agents/skills/ltx-2-5-prompting/`，或目标项目的 `.agents/skills/ltx-2-5-prompting/`。

Codex 会自动检测 Skill 变化；如果安装或更新后没有显示，重启 Codex。安装目录与加载机制参见 [Codex Skills 官方文档](https://developers.openai.com/codex/skills/)。

## 快速使用

在 Codex 对话中使用 `$ltx-2-5-prompting` 显式调用，也可从 Skill 选择器中选择显示名称 **LTX 2.5 提示词**。

```text
使用 $ltx-2-5-prompting，为 LTX-2.5 写一个连续单镜头提示词：
银色机械腕表放在深灰色展示架上，白色背景，展示金属材质。
镜头从左前方缓慢绕到正面，只有轻微滴答声，没有对白和音乐。
只输出英文提示词。
```

输出示例：

```text
A close-up at tabletop height frames a silver mechanical wristwatch on a charcoal display stand. A large softbox above and to the left creates a clean highlight along the brushed metal case, with a matte white background. The second hand advances steadily while the crown and engraved dial markers remain sharply visible. The camera circles around the watch in a small arc from its front-left side toward a frontal view; as the movement settles, the dial faces the center of frame and the strap extends toward the lower right. A faint mechanical ticking is audible with no speech or music.
```

这是本 Skill 的自编教学示例，未经过视频生成效果验证。生成时，将提示词正文填入实际工作流的文本输入节点或接口；时长、分辨率、帧数等参数在对应工作流中单独设置。

## 更多请求示例

### 改写与诊断

```text
使用 $ltx-2-5-prompting，诊断并改写下面的提示词。
保留人物和情节，指出影响最大的两个问题，再给修订版：
一个穿绿色外套的女人站在雨夜街头，cinematic，镜头又推近又拉远，
突然切到她的手，再回到远景，有音乐。
```

### 首帧图生视频

先在对话中提供可访问的首帧图像，再提出动作要求：

```text
使用 $ltx-2-5-prompting，基于这张首帧写图生视频提示词。
人物打开桌上的书，再低头阅读。保持首帧中的衣着、构图和光照，
固定机位，无对白，只保留翻书声。
```

### 多镜头与中文对白

```text
使用 $ltx-2-5-prompting，写一个三镜头的雨夜电车站场景。
同一位穿深绿色外套的女人先走进候车亭，再查看地图，最后与朋友会合。
她用普通话说：“就是这一站。”朋友回答：“我们还有时间。”
明确每次切镜，让雨声和钢琴音乐自然衔接。视觉描述用英文，台词保留中文。
```

### Dub-It 配音替换

```text
使用 $ltx-2-5-prompting，为已有视频中的单个女性说话者写 Dub-It 提示词。
目标语言为英语，美式口音，语气平静。完整台词是：
“The doors open at nine. I will meet you outside.”
```

Dub-It 面向已有视频的对白替换，需要源视频和完整目标台词。多人配音、语言验证范围和台词时长匹配等边界见 [工作流说明](ltx-2-5-prompting/references/workflows.md)。

## 输出约定

- 默认以中文说明、英文视觉描述交付；用户指定其他语言时遵从用户，对白保留目标语言的原生文字。
- 默认先提供一个可直接使用的提示词代码块，必要时补充关键假设；要求“只要提示词”时只输出提示词。
- 按景别、场景、动作、主体特征、运镜和音频六要素组织内容，最终写成自然语言，而非固定字段表。
- 单镜头保持连续；多镜头使用明确的自然语言转场，并交代新构图、主体连续性和声音变化。
- 时长、分辨率、帧数、seed 和采样设置与提示词正文分开；具体参数需核对所用接口。
- JSON、权重标签和负面提示词按需处理，并先确认工作流支持；默认不自动添加。

详细执行规则见 [SKILL.md](ltx-2-5-prompting/SKILL.md)。

## 目录结构

```text
.
|-- README.md
`-- ltx-2-5-prompting/
    |-- SKILL.md
    |-- agents/
    |   `-- openai.yaml
    `-- references/
        |-- camera-language.md
        |-- examples.md
        |-- prompt-patterns.md
        |-- sources.md
        `-- workflows.md
```

| 文件 | 用途 |
| --- | --- |
| [SKILL.md](ltx-2-5-prompting/SKILL.md) | Skill 名称、触发描述、任务流程与交付检查 |
| [agents/openai.yaml](ltx-2-5-prompting/agents/openai.yaml) | Codex 显示名称、简短说明与默认调用提示 |
| [prompt-patterns.md](ltx-2-5-prompting/references/prompt-patterns.md) | 六要素、单镜头、对白、多镜头与诊断规则 |
| [camera-language.md](ltx-2-5-prompting/references/camera-language.md) | 运镜词汇、主体调度与结束构图 |
| [examples.md](ltx-2-5-prompting/references/examples.md) | 自编或改写的完整提示词示例 |
| [workflows.md](ltx-2-5-prompting/references/workflows.md) | 图生视频、Enhancer、Dub-It、编辑与参数边界 |
| [sources.md](ltx-2-5-prompting/references/sources.md) | 官方来源、核验日期与不同页面措辞的处理 |

## 常见问题

**安装后找不到 Skill？**

检查 `SKILL.md` 是否直接位于 `.agents/skills/ltx-2-5-prompting/`，并确认 `agents/` 和 `references/` 完整复制。项目级安装需要在对应项目中使用；仍未显示时重启 Codex。

**需要联网或 API Key 吗？**

普通提示词写作可使用随附参考，无需联网；Skill 本身不调用视频生成 API，也不需要 API Key。核对新功能、接口参数或支持范围时需要查阅当前官方资料；实际生成所需条件由所选工作流决定。

**可以直接放进 ComfyUI 的 `custom_nodes` 吗？**

Skill 安装在 Agent 的技能目录。它产出的提示词可用于相应的 ComfyUI 工作流，但仓库不提供可在 `custom_nodes` 中加载的节点代码。

**是否保证模型严格按提示词生成？**

提示词需要结合成片验证。复杂物理、屏幕文字和精确标志可能不稳定；关键字幕、标签或品牌文字建议后期处理。参考中的示例是写作示范，不代表已验证的生成结果。

## 官方参考与维护

当前参考资料的核验日期为 **2026-09-30**：

- [LTX-2.5 Prompt Guide](https://ltx.io/blog/ltx-2-5-prompt-guide)
- [LTX 官方文档：Prompting Guide](https://docs.ltx.io/open-source-model/usage-guides/prompting-guide)
- [Camera Movement Prompt Guide](https://ltx.io/blog/camera-movement-prompt-guide)
- [LTX Prompting 分类页](https://ltx.io/blog-category/prompting)

各来源的具体使用范围见 [sources.md](ltx-2-5-prompting/references/sources.md)。更新时应核对 LTX-2.5 及对应功能的当前官方说明，区分提示词建议、模型能力和接口参数，并记录核验日期；新增示例需标明来源及是否经过实际生成验证。

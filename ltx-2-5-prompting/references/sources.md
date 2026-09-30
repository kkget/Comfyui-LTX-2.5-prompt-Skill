# 官方来源与核验范围

核验日期：2026-09-30。以下四个页面均已读取正文或分类链接；本 Skill 是针对提示词任务的归纳，不是官方发布的 Skill，也不保存整页副本。

| 编号 | 来源 | 本 Skill 使用的内容 |
| --- | --- | --- |
| S1 | [LTX-2.5 Prompt Guide](https://ltx.io/blog/ltx-2-5-prompt-guide) | 六要素、单镜头、剧本式结构、多镜头转场与声音连续、雨中城市示例、Dub-It、模型限制；Video Editing 建议仅见页面摘要 |
| S2 | [官方文档 Prompting Guide](https://docs.ltx.io/open-source-model/usage-guides/prompting-guide) | 六要素与动作动词、其他模型提示词迁移、节拍/时长预测、Prompt Enhancer、本地与 API 区分、Dub-It、新闻直播 Sample Prompt |
| S3 | [Camera Movement Prompt Guide](https://ltx.io/blog/camera-movement-prompt-guide) | 公布的相机词汇、主体调度、运动终点、帧数/尺寸约束、运动参考与相机适配器 |
| S4 | [LTX Prompting 分类页](https://ltx.io/blog-category/prompting) | 发现更多官方文章；分类页本身不作为模型能力或接口参数的证据 |

## 阅读原始示例

- 雨中城市多镜头：S1 或 S2 的 `Multi-Shot Example`。
- 新闻直播：S2 的 `Sample Prompts / Example 1`。
- 运镜示例：S3 的 `An annotated example`。

[examples.md](examples.md) 提供的是自编或改写提示词，明确区别于官方原文。用户要求官方完整原文时，提供页面和对应章节链接；避免将改写内容标成官方原文。

## 对不同页面措辞的处理

1. S1、S2 同时接受连续段落与较长剧本式场景。S3 更强调单镜头的顺序和一个主运镜。将其应用为默认写作建议，不把它变成禁止复杂连续运动或剧本格式的模型硬限制。
2. S3 的“一种景别”指避免未解释的构图堆叠。多镜头按切镜重建景别，连续推近也可以解释景别变化。
3. S1、S2 的雨中城市示例在持物等细节上有差异。可以分别指向原页面，不拼接成所谓唯一的官方提示词。
4. S1 摘要提到 Video Editing，正文在核验时没有完整相关章节；本 Skill 只归纳摘要中明确出现的提示词建议。
5. Dub-It 的已验证语言列表与“使用原生文字”的示例是两种不同信息。后者不证明未列出的语言已验证。
6. 本地开源标志、ComfyUI 节点与 API 请求字段互不替代。接口和模型版本变化时，重新核对所用路径。

## 分类页的使用

S4 还列出负面提示词、常见错误、JSON 提示词和早期 LTX 版本等文章。这些条目可以按需继续阅读，不能仅凭标题推导 LTX-2.5 支持某种语法。升级本 Skill 时优先核对 LTX-2.5 主指南及对应功能的当前官方文档。

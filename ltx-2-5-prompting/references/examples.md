# 示例与迁移

以下完整提示词均为本 Skill 自编或按官方结构改写的教学示例，不是官方原文，也没有经过视频生成效果验证。保持结构和因果关系，按用户素材替换内容，不要机械照搬角色或美术风格。

## 雨夜城市：单镜头

```text
A medium wide shot at eye level frames a woman waiting beneath the awning of a closed city bookstore at night. Rain glistens on the pavement, and the bookstore's white sign casts a steady light across her dark green coat. She folds a paper map, tucks it into her pocket, and steps from the left third of frame to the center. Her short black hair is damp at the edges, and she presses her lips together before looking toward the street. The camera pushes in toward her as she stops; as the move settles, her face occupies the center of a medium close-up with the illuminated doorway softly visible behind her. Rain patters on the awning, a passing car hisses across the wet road, and a quiet piano phrase plays underneath; she does not speak.
```

覆盖六要素；机位前移有结束构图；画面以主体动作推进。人物表情用可见线索描述。

## 雨夜城市：三镜头

S1、S2 官方多镜头示例均使用雨中城市，但主体持物等细节略有差异。下面保留建立、细节、反应的功能，重新设计人物和情节。

```text
A wide establishing shot frames a tram stop on a rain-soaked city street at night, with cool white shelter lights reflecting on the pavement. A woman with short black hair in a dark green coat walks beneath the shelter, carrying a folded paper map, while rain and a low piano melody fill the soundscape. A hard cut transitions to an eye-level close-up of the same woman beneath the shelter light; she opens the map, traces a street with her finger, then looks off-screen right. The piano melody continues across the cut while the rain sounds softer under the roof, and she says quietly in English, "This is the right stop." A second hard cut transitions to a medium two-shot from beside the shelter as a man in a gray rain jacket enters from frame right and stands next to the woman in the dark green coat. She lowers the map and gives a small smile; both remain under the same white shelter light. The piano continues, the tram's approaching motor grows louder, and the man replies in English, "We still have time."
```

两个切镜均重新建立构图和声音关系；识别特征跨镜头一致。它不是同时运镜的单镜头。

## 新闻直播：对白与节拍

S2 的官方 Sample Prompts 使用新闻现场、记者对白和现场揭示。下面是不同事件的简化改写，使用一个平移运动。

```text
EXT. CITY RIVERBANK - MORNING - LIVE NEWS BROADCAST
A continuous eye-level medium shot frames a reporter beside a newly opened pedestrian bridge in clear morning light. He wears a navy field jacket, holds a microphone at chest height, and looks into the lens as his free hand tightens around a small notepad. Soft crowd chatter and footsteps on the bridge are audible.
The reporter speaks in clear Mandarin: "新桥今天正式开放。我们一起看看现场。"
He turns his head to the right and gestures toward the bridge, then pauses. The camera pans across to the right, revealing a small group of pedestrians walking over the wooden deck; as the pan settles, the bridge fills the center of a wide view and the reporter is just outside frame left. The same crowd ambience continues, and the reporter adds from off-screen in Mandarin, "第一批市民已经走上桥面。" There is no music.
```

中文台词保留汉字；对白、停顿和机位响应有因果关系。画外记者继续讲话属于音频延续，不是切镜。

## 产品细节：无人物主体

```text
A close-up at tabletop height frames a silver mechanical wristwatch on a charcoal display stand. A large softbox above and to the left creates a clean highlight along the brushed metal case, with a matte white background. The second hand advances steadily while the crown and engraved dial markers remain sharply visible. The camera circles around the watch in a small arc from its front-left side toward a frontal view; as the movement settles, the dial faces the center of frame and the strap extends toward the lower right. A faint mechanical ticking is audible with no speech or music.
```

物体特征代替人物特征；小幅弧线具有明确终点。精确刻字依然需要逐帧检查，关键品牌文字可后期添加。

## 图生视频：必须基于实际首帧

假设用户提供的首帧确实是“桌边坐着一位穿灰色上衣、戴圆框眼镜的男子，桌面有一本合上的书”，可写：

```text
A continuous medium shot preserves the man with round glasses and a gray shirt seated beside the closed book in the opening image. He rests his right hand on the cover, opens the book, then lowers his gaze toward the first page. The camera remains in a static frame as his fingertips settle along the edge of the page, keeping the opening image's composition and lighting. A soft cover creak and a brief page rustle are audible; there is no speech or music.
```

这是条件示例，不是对用户图片的观察结果。实际使用时先查看首帧，修正衣着、位置、书本和光照。

## Dub-It：简短替换对白

假设源视频是一位女性的短句，目标时长与下列台词接近：

```text
A woman is speaking English with a neutral American accent, saying: "The doors open at nine. I will meet you outside." She speaks calmly at a natural conversational pace.
```

它面向已有视频的配音替换，因此没有添加景别、背景或运镜。是否匹配源音节与时长，需要实际核对源视频。

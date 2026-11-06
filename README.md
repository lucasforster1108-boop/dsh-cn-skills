# dsh-cn-skills

**给 DeepSeek Harness 的中文技能包。15 个技能，都是日常真正用得上的事。**

## 这是什么

DeepSeek Harness（简称 dsh，口号「一切皆插件」）是深度求索推出的 AI 助手框架：
你对它说话，它按「技能」里写好的流程和规矩替你干活。官方自带的技能全是给程序员用的
（代码审查、CI、文档），中文日常技能几乎是空白。

这个包补的就是这块：15 个技能，全是普通人一年到头真正用得上的事——写周报、做述职、
润色文字、发小红书、改简历、记会议纪要、看合同……每个技能都是一份写给 AI 的操作手册
（`SKILL.md`）：什么时候触发、按什么步骤做、交付什么格式、哪些红线不能碰，全部写死，
让 AI 每次产出都稳定、成型、不编造。

技能的格式是通用的 Agent Skills 标准（`.agents/skills/<技能名>/SKILL.md`），
除了 DeepSeek Harness，在 Claude Code 等支持该标准的工具里同样能用。

## 技能一览（15 个）

### 办公类

| 技能 | 干什么 | 你可以这样说 |
|---|---|---|
| `weekly-report` 周报 | 把一周的零散记录整理成有成果、有数据的成型周报 | 「把这周的工作整理成周报」 |
| `annual-review` 述职总结 | 年终总结、述职报告、转正述职：成果量化、不足点到为止、附一分钟电梯版 | 「帮我写今年的年终总结」 |
| `meeting-notes` 会议纪要 | 从会议记录里提炼决议、待办（带负责人和期限）、未定事项 | 「把这份会议记录整理成纪要」 |
| `speech-draft` 发言稿 | 会议发言、年会讲话、婚礼致辞、主持词，按时长出可直接念的稿 | 「写个年会发言稿，5 分钟」 |
| `ppt-outline` PPT 大纲 | 先给一页纸结构，再展开逐页标题、要点、配图建议和演讲备注 | 「给这个汇报做个 PPT 大纲」 |
| `excel-helper` 公式助手 | 中文描述需求，直接给 Excel/WPS 能粘贴的公式、解释和避坑提醒 | 「怎么把重复的订单号标出来」 |
| `resume-cn` 简历优化 | 拿目标岗位 JD 对齐改写，经历变成果条目，不编造 | 「按这个 JD 帮我改简历」 |

### 内容类

| 技能 | 干什么 | 你可以这样说 |
|---|---|---|
| `xiaohongshu-post` 小红书 | 没定主题先给 5 个选题；定题后出标题、正文、标签、3 组封面文案，带广告法违禁词检查 | 「给我写篇小红书，主题是自装避坑」 |
| `wechat-article` 公众号 | 选题、标题、正文（带排版标记）、摘要、封面文案一次给齐 | 「写篇公众号文章，讲职场沟通」 |
| `short-video-script` 短视频脚本 | 抖音/视频号口播稿：前 3 秒钩子、逐段时间标注、画面提示、发布标题 | 「写个 1 分钟的口播脚本」 |
| `moments-copy` 朋友圈 | 晒娃、旅行、工作、生意、节日，一次给 5 条不同风格挑着发 | 「给这组照片配个朋友圈文案」 |

### 工具类

| 技能 | 干什么 | 你可以这样说 |
|---|---|---|
| `zh-polish` 中文润色 | 去翻译腔、改病句、长句拆短，正式/口语风格可选，不改事实 | 「帮我润色一下这段话」 |
| `translate-zh` 中英互译 | 地道翻译，专治中式英语与翻译腔，附术语对照表 | 「把这封邮件译成英文」 |
| `digest-cn` 长文摘要 | 长文、英文材料压成中文摘要＋关键点＋术语对照 | 「把这篇文章总结成中文」 |
| `contract-scan` 合同速览 | 签字前把金额、期限、自动续约、违约金、管辖地等坑点挑出来列清单 | 「帮我看看这份租房合同有什么坑」 |

## 全包统一规矩

每个技能都写死了这几条，这是这个包和「随便问问 AI」的区别：

1. **不编造**：没做过的事、没给的数字，绝不替你写进周报、简历、合同摘要；缺素材会明确标注「待补」，不会瞎填。
2. **给成品不给毛坯**：产出都是能直接复制使用的终稿格式（周报分行、纪要带表格、公式能直接粘贴）。
3. **合规先行**：小红书、公众号、短视频、朋友圈文案交付前过一遍广告法违禁词；合同只做阅读提示并注明「不是法律意见」。
4. **中文优先**：按中国人的表达习惯和国内平台规则写，不套国外模板。

## 安装

### DeepSeek Harness

把 `.agents/skills/` 下的技能文件夹复制到你项目的 `.agents/skills/` 目录：

```bash
git clone https://github.com/lucasforster1108-boop/dsh-cn-skills.git
cp -r dsh-cn-skills/.agents/skills/* 你的项目/.agents/skills/
```

只装其中几个也可以，挑文件夹复制即可。然后直接用中文对 dsh 说话，
它会按你的话自动匹配技能（匹配规则写在每个技能的说明里）。

### 其他支持 Agent Skills 的工具

同样的文件夹复制到该工具的技能目录即可（如 Claude Code 的 `.claude/skills/`
或个人技能目录），格式通用，无需改动。

## 目录结构

```
dsh-cn-skills/
├── README.md
└── .agents/skills/
    ├── weekly-report/      SKILL.md
    ├── annual-review/      SKILL.md
    ├── meeting-notes/      SKILL.md
    ├── speech-draft/       SKILL.md
    ├── ppt-outline/        SKILL.md
    ├── excel-helper/       SKILL.md
    ├── resume-cn/          SKILL.md
    ├── xiaohongshu-post/   SKILL.md
    ├── wechat-article/     SKILL.md
    ├── short-video-script/ SKILL.md
    ├── moments-copy/       SKILL.md
    ├── zh-polish/          SKILL.md
    ├── translate-zh/       SKILL.md
    ├── digest-cn/          SKILL.md
    └── contract-scan/      SKILL.md
```

## 后续计划

- 继续按「中国人常用」补技能（求职面试准备、请假与申请文案、家长群沟通等）
- 收集实际使用反馈，迭代每个技能的红线与交付格式

## License

MIT

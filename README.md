<p align="center">
  <img src="assets/icon.svg" width="88" height="88" alt="放大镜中的音符" />
</p>

# Music Comment Research

[项目仓库](https://github.com/Harmonese/music-comment-research-skill) · [CC BY 4.0](LICENSE)

为音乐评论与作品讨论准备可追溯研究资料的 Agent Skill。支持歌曲、专辑、合辑及具体发行版本，不限定评论发布平台。

先研究作品，再围绕你的观点核查和讨论；明确要求时才协助写成评论。默认使用中文，也可以指定其他回答语言。

## 能做什么

- **确认作品与版本**：区分原版、再版、remix、重录和现场版本，解释合辑构成及发行记录差异。
- **研究创作与制作**：查找艺人自述、人员署名、录音过程、采样和相关背景。
- **整理音乐与歌词分析**：交代分析依据，区分创作者解释、评论者观点与模型推断。
- **阅读乐评和社区讨论**：保留针对具体曲目、声音与结构的观察、理由和个人听感。
- **厘清相关权利关系**：遇到相关资料时说明版权、出版管理或发行授权，不预设存在争议。
- **讨论或修改评论**：核查你的判断，补充支持与反例；按要求改写，保留个人观察。

报告按资料组织，不套固定章节，不为普通事实附加宏大意义。歌曲推荐和榜单推荐不属于主要用途。

## 使用要求

这是一个以 Markdown 指令和参考文件组成的 Skill，没有需要单独运行的程序或服务。

运行它的 AI 工具需要支持加载 Skill，并具备联网搜索、打开来源页面的能力。具体来源是否可访问取决于运行环境；文件读写能力仅在你要求保存个人偏好时需要。

格式依据 [Agent Skills 规范](https://agentskills.io/specification)。不同工具的安装入口、联网能力与模型表现可能不同，格式兼容不代表研究效果相同。

## 安装

### Codex 本地安装

下载并解压[项目仓库](https://github.com/Harmonese/music-comment-research-skill)，将包含 `SKILL.md` 的目录命名为 `music-comment-research`，放入以下位置之一：

- 个人使用：`~/.agents/skills/music-comment-research/`
- 项目内使用：`<项目根目录>/.agents/skills/music-comment-research/`

仓库名称是 `music-comment-research-skill`，安装时的 Skill 目录与调用名称是 `music-comment-research`。

复制完整目录，保留 `references/`、`agents/` 与 `assets/` 的相对位置。不要只复制 `SKILL.md`，也不要让解压产生的额外目录层级隔开 Skill 目录与其入口文件。

安装后在 Codex 中使用 `$music-comment-research` 调用；若未出现，重启后再查看。也可以让内置的 `$skill-installer` 从本项目的 GitHub 仓库安装。安装路径与调用方式以 [OpenAI 官方文档](https://learn.chatgpt.com/docs/build-skills) 为准。

### 其他支持 Skills 的工具

按所用工具的文档导入完整 Skill 目录。若工具支持上传 Skill 包，使用其要求的文件夹或压缩包格式；产品内插件发布与直接导入 Skill 是不同的分发方式。

## 使用示例

明确调用 Skill 后，可以提供作品名、艺人名或具体发行链接：

```text
$music-comment-research
研究 deadmau5 的《Full Circle & Vexillology》2015 年双 CD 合辑。
请同时研究两部原作的制作背景、乐评和听众讨论。
```

继续追问某一问题：

```text
这些页面给出的发行日期不同。请分别说明记录对应哪个版本，哪些差异还无法解释。
```

讨论自己的判断：

```text
我觉得这首歌的重复既带来沉浸感，也削弱了后半段的变化。
请查找相关讨论，补充支持或反对这个判断的具体理由。
```

需要成稿时明确提出：

```text
根据前面的研究，把我的草稿改成一段约 200 字的评论。
保留我的判断，不添加我没有表达过的私人经历。
```

## 个人偏好

[个人偏好档案](references/comment-style-profile.md) 默认留空，你可以自行填写研究资料的呈现要求与最终评论的文风偏好。也可以明确要求 AI 协助维护；普通研究对话不会自动写入档案。

更新 Skill 前请备份已填写的档案，更新后合并或恢复个人内容。提交反馈或修改建议时，无须上传你的私人档案。

## 资料与分析的边界

重要事实应就近提供来源；未确认的信息保留其具体疑点。社区观点属于发言者，不自动代表共识；没有实际分析音频时，不声称已经试听。研究结果仍可能受来源质量、访问限制和模型判断影响，可沿引用进一步核对。

## 文件结构

```text
music-comment-research/
├── SKILL.md                            # 核心工作流与行为要求
├── references/
│   ├── research-method.md              # 检索、证据与资料组织方法
│   └── comment-style-profile.md        # 使用者自行维护的个人偏好
├── agents/
│   └── openai.yaml                     # 界面名称、图标与调用配置
├── assets/
│   └── icon.svg                        # 音乐与研究图标
├── LICENSE                             # CC BY 4.0 完整许可证
└── README.md                           # 安装与使用说明
```

## 反馈与改进

欢迎通过仓库的 [Issues](https://github.com/Harmonese/music-comment-research-skill/issues) 或 [Pull Requests](https://github.com/Harmonese/music-comment-research-skill/pulls) 提供问题与修改建议。反馈时附上使用的工具和模型、研究对象、原始请求、具体问题片段及期望行为；涉及事实错误时，尽量附上能够核对的来源。

## 许可证

本项目的 Skill 指令、参考文档和图标采用 **Creative Commons Attribution 4.0 International（CC BY 4.0）**。完整条款见 [LICENSE](LICENSE)，易读说明见 [Creative Commons 官方页面](https://creativecommons.org/licenses/by/4.0/deed.zh-hans)。

允许复制、修改和再分发，包括商业用途；分享原文或修改版本时，请适当署名、提供许可证链接，并注明是否修改。署名可使用项目维护者 **Harmonese**，并链接到本仓库。

署名示例：

> 基于 [Harmonese 的 Music Comment Research](https://github.com/Harmonese/music-comment-research-skill)，按 [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) 使用。已修改研究流程。

请按实际情况说明改动。本项目的许可不涵盖研究时引用的第三方文章、歌词、录音或其他外部材料，也不因使用本 Skill 就自动要求将生成的评论按相同许可证发布。

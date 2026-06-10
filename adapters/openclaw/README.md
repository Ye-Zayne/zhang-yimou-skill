# OpenClaw Adapter

这个目录用于让 `张艺谋Skill` 在 OpenClaw 类 agent/runtime 中稳定运行。

## 安装方式

把仓库放到 OpenClaw 可读取的 skills 或 workspace skills 目录，例如：

```bash
git clone https://github.com/Ye-Zayne/zhang-yimou-skill ~/.openclaw/workspace/skills/zhang-yimou-skill
```

如果 OpenClaw 使用项目级 workspace，可以放在：

```text
{workspace}/.openclaw/skills/zhang-yimou-skill/
```

## 入口文件

OpenClaw 应优先读取：

1. `SKILL.md`
2. `references/pipeline-output-standard.md`
3. `references/output-templates.md`
4. `examples/complete-case/gray-bell-campus/README.md`

## 推荐调用词

```text
使用 zhang-yimou-skill，把这个短剧创意做成完整导演项目包。
先输出剧本与流程清单，再输出镜头表与单元切分、站位图、图片故事版/3x3九宫格、Seedance Prompt。
第六步视频生成和第七步自动剪辑必须先询问我是否需要。
```

## 输出约束

- 所有阶段输出 Markdown 文件。
- 图片资产使用 SVG/PNG/JPG/WebP 均可，但故事版和九宫格必须是可渲染图片。
- 九宫格视频参考图必须无字幕、无镜号、无标题、无水印。
- 如果 OpenClaw 没有图片生成能力，则输出可执行 image prompt，并把图片路径留为待生成状态。

## 推荐项目结构

```text
storyboard_pipeline/{项目名}/
├── 00_流程清单.md
├── docs/
├── characters/
├── scenes/
├── blocking/
├── storyboards/
├── video_grids/
├── adapters/
├── manifests/
├── videos/
└── edit/
```

# Runtime Compatibility

`张艺谋Skill` 的兼容策略是：核心规则保持为普通文件，输出保持为 Markdown/SVG/JSON/图片资产，不绑定某一个模型或 agent。

| 平台 / Runtime | 支持方式 | 注意事项 |
| --- | --- | --- |
| Codex | 读取 `SKILL.md` 和 `references/`，直接生成文件、图片、manifest | 适合完整项目包和 GitHub 更新 |
| Claude Code | 作为本地 skill 目录读取 | 图片生成能力取决于当前工具链 |
| OpenClaw | 使用 `adapters/openclaw/README.md` | 推荐项目级 `.openclaw/skills/` |
| Hermes Desktop | 使用 `adapters/hermes-desktop/README.md` | 图片资产用 SVG/PNG，Markdown 直接预览 |
| Kimi | 使用分层 Markdown 上下文包 | 长上下文适合带完整剧本和镜头表 |
| GLM | 使用视觉审核、分镜诊断、prompt 改写 | 可结合图片理解做风格一致性检查 |
| MiniMax | 使用逐单元视频 prompt 和 JSON manifest | 视频生成前需确认参数和额度 |
| Seedance / 即梦 | 使用 `docs/05_Seedance_Prompt_逐单元.md` | 第六步必须询问用户是否执行 |
| ffmpeg / CapCut / 剪映 | 使用剪辑 manifest | 第七步必须询问用户是否执行 |

## 最小兼容包

一个 runtime 只要能读取文本，就至少可以使用：

```text
SKILL.md
references/director-system.md
references/output-templates.md
references/pipeline-output-standard.md
examples/complete-case/gray-bell-campus/README.md
```

一个 runtime 只要能预览图片，就可以使用：

```text
examples/complete-case/gray-bell-campus/images/*.svg
```

一个 runtime 只要能调用视频模型，就可以使用：

```text
docs/05_Seedance_Prompt_逐单元.md
manifests/*.json
```

# 通用真人角色提示词 Skill

这是一个用于 Codex 的角色资产 Skill。它把一个真人角色整理成可复用的 C01 母本，再生成三视图、四格设定图或单张人物参考图提示词，并给出摄影参数、一致性规则和禁止项。

它只管静态人物设定图。图生视频、动作、剪辑和发布交给对应的视频制作 Skill。

## 能做什么

- 从人物描述中拆出身份、身体、面部、发型、服装和固定配饰。
- 建立可复用的 C01 角色母本。
- 生成正面、侧面、背面的三视图提示词。
- 生成头像或胸像加正面、侧面、背面的四格设定板提示词。
- 检查脸、发型、体型、服装和配饰是否一致。
- 在脸部、服装或手脚出问题时，给出单变量修改方向。

## 安装

安装前先确认目标目录不存在，或者在 `.codex/skills/` 下给旧版本改名备份。

Windows PowerShell：

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.codex\skills" | Out-Null
git clone https://github.com/m54358922/generate-real-person-character-prompt.git "$env:USERPROFILE\.codex\skills\generate-real-person-character-prompt"
```

macOS 或 Linux：

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/m54358922/generate-real-person-character-prompt.git ~/.codex/skills/generate-real-person-character-prompt
```

安装完成后重启 Codex。

## 调用

直接点名 Skill，再说清人物和要生成的视图：

```text
使用 $generate-real-person-character-prompt，帮我建立一个 32 岁女性纪录片导演的角色母本。
人物是短发、小麦肤色、身高 168 厘米，常穿深灰色工装夹克。
先给我角色母本，再生成正面、侧面、背面的三视图提示词。
```

如果只要最终提示词，可以直接说：

```text
使用 $generate-real-person-character-prompt。
保留 C01 母本、视图任务、摄影参数和禁止项，不要展开分析。
```

## 文件结构

```text
.
├── SKILL.md
├── agents/
│   └── openai.yaml
├── references/
│   └── character-prompt-template.md
└── packages/
    └── shengcai-mcp-project-research-1.0.0.zip
```

## 生财 MCP 项目调研 Skill 发布包

`packages/shengcai-mcp-project-research-1.0.0.zip` 是“生财 MCP 项目调研”Skill 的发布包，和上面的角色资产 Skill 分开使用。

- 下载地址：[shengcai-mcp-project-research-1.0.0.zip](https://github.com/m54358922/generate-real-person-character-prompt/raw/main/packages/shengcai-mcp-project-research-1.0.0.zip)
- SHA-256：`e764866be1deb881bc456611568e940b0577cb1ea7495428831ea22fba2b59c8`


# generated-artifact-naming

一个 Codex skill，用于将生成文档与项目源码分开，并按北京时间归档：

```text
generated/
└── 261009/
    ├── 1841_启动指南.md
    ├── 1845_三类记忆实现与区别.md
    └── requirements.txt
```

日期目录格式为 `YYMMDD`，Markdown 文件格式为 `HHmm_主题.md`。时间使用生成当时的北京时间，示例数字不会成为固定前缀。完整规则见 [SKILL.md](SKILL.md)。

## 安装

Windows PowerShell：

```powershell
git clone https://github.com/shuaibilx/generated-artifact-naming.git "$HOME/.codex/skills/generated-artifact-naming"
```

macOS / Linux：

```bash
git clone https://github.com/shuaibilx/generated-artifact-naming.git ~/.codex/skills/generated-artifact-naming
```

如果配置了自定义 `CODEX_HOME`，请改用该目录下的 `skills/generated-artifact-naming`。目标目录已存在时不要重复克隆或覆盖，先确认它是否为此仓库的安装目录。

## 使用

安装后在能发现该 skill 的 Codex 会话中引用：

```text
使用 $generated-artifact-naming，将本次项目启动说明持久化到本地。
```

如果当前会话尚未列出这个新 skill，可以新建会话，或直接提供本地 `SKILL.md` 的路径供 Codex 读取。默认允许自动发现，也支持明确引用。

修改已有文件保留原路径；另存文档使用新的时间；重名追加序号。`requirements.txt`、`SKILL.md` 等必要的固定文件名及项目运行数据保留原有约定。该 skill 无需安装额外的 Python 包。

## 仓库结构

```text
generated-artifact-naming/
├── SKILL.md             # 可复用规则与触发条件
├── agents/openai.yaml   # Codex 显示名称与调用示例
└── README.md            # GitHub 安装和使用说明
```

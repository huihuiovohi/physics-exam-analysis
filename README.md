# 高中物理试卷分析 Skill

供 Codex 使用的高中物理试卷分析技能：按学生文件夹串行处理材料，核实错题和课程对应，修改原有 Word 报告并检查实际排版。

## 安装

下载本仓库，将 `physics-exam-analysis` 技能文件夹放到用户目录下的 `.codex/skills/`。技能文件夹内应直接包含 `SKILL.md`，避免多套一层目录。重新打开对话后确认技能可用。

## 使用

```text
使用 $physics-exam-analysis，处理截图中的学生文件夹，
按顺序串行修改原有 Word 并渲染检查。
本次补充错题号：……
已授课范围：……
```

每次提供样例 Word、原报告、原卷、课程 Excel，以及已有的错题信息或学生作答材料。技能不包含学生数据和私有课程表。

## 包含内容

- `SKILL.md`：执行流程和任务边界。
- `references/`：报告内容、排版要求和交付检查清单。
- `scripts/report_tools.py`：材料盘点、标签与表格格式修复、部分规则检查。
- `scripts/render_word.ps1`：通过 Windows Microsoft Word 导出 PDF。

Python 依赖为 `python-docx`、`openpyxl`、`Pillow`；PDF 读取可使用 `pypdf`、`pypdfium2`。渲染需要可用的 Word 或其他文档渲染工具，及对应字体。

辅助脚本不生成教学判断，不能替代题目核实、课程核实和逐页视觉检查。运行格式修复前应备份原报告。更多说明见 [使用与分享说明](使用与分享说明.md)。

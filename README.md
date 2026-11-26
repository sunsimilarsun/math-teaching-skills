# Math Teaching Skills

面向数学教学资料工作流的七个实验性 Agent Skill，涵盖数学资料制作、审校与家长反馈。

## 内容

- [`math-review`](skills/math-review/SKILL.md)：独立求解、条件与边界检查、答案完整性、图文关系和分层证据报告。审查默认只读。
- [`math-handout-author`](skills/math-handout-author/SKILL.md)：依据目标教学库的现行规范编写、改编或装配讲义；区分产品类型、标准答案、补充解析和独立检测。
- [`math-item-ingest`](skills/math-item-ingest/SKILL.md)：从原稿或返回包吸收题目，核对稳定身份、重复、跨页、图片答案和题族关系；候选检查不修改正式库，正式接入遵循目标产品契约及授权。

- [weekly-student-feedback](skills/weekly-student-feedback/SKILL.md) — 五段家长周反馈。
- [learning-report-author](skills/learning-report-author/SKILL.md) — 三页学员学习报告。
- [math-exam-analysis](skills/math-exam-analysis/SKILL.md) — 单次考试卷面分析。
- [stage-learning-feedback](skills/stage-learning-feedback/SKILL.md) — 单页阶段学情反馈。

## 一键安装四个家长反馈 Skill

复制下面整段提示词，发给要安装这些 Skill 的 Agent。

```text
请从 GitHub 公开仓库 https://github.com/sunsimilarsun/math-teaching-skills 的 main 分支，一次性为当前 Agent 安装以下四个 Skill 和各自的配套模板、规范。请直接执行安装。

- 周反馈：skills/weekly-student-feedback
- 学习报告：skills/learning-report-author
- 试卷分析：skills/math-exam-analysis
- 阶段学情分析：skills/stage-learning-feedback

使用当前 Agent 支持的 Skill 安装方式。若使用 Codex，优先用 skill-installer。只安装以上四个目录，每个目录完整保留，包括 SKILL.md 以及包内已有的 assets/、references/，确保相对链接仍然有效。遇到同名旧版时，先比较差异；有本地修改的先备份，再更新。

安装后，请从实际安装位置逐项检查：
1. 周反馈的五段文字骨架、课堂采集简表和反馈规范可以读取。
2. 学习报告的三页 Word 模板和制作规范可以打开。
3. 试卷分析的 A4 横向单页 Word 模板和审核规范可以打开。
4. 阶段学情分析的单页 Word 模板、制作规范和教师采集审核单可以打开。

最后列出四个 Skill 的安装位置和检查结果，说明是否需要重启 Agent 或新开会话，并给出一句可以直接试用的中文指令。
```

## 使用与适配

本仓库不包含题库、学生数据或插件，也不会自动安装、覆盖文件或部署任何软件。

四个家长反馈 Skill 可独立安装。周反馈附五段文字骨架和课堂采集规范；其余三个各附空白 Word 母版和制作规范，阶段反馈另附教师审核单。安装时保留完整目录，包括 assets/ 和 references/。制作时提供获准使用的学生材料即可，也可以指定自己的模板。

1. 阅读所需 `SKILL.md` 和引用文件。
2. 按所用 Agent 客户端的 Skill 安装方式，选择性导入对应目录。目录应保留 `SKILL.md` 与 `references/` 的相对位置；已有同名目录先比对，不盲目覆盖。
3. 在任务中提供目标文件／教学库、当前规范入口、产品类型、交付范围和检查或修订权限。需要项目专用规范时，请提供相应文件。
4. 使用小范围副本试验，再人工检查成果。不要将含答案的母稿直接分发给学生。

示例请求：

> 使用 math-review 审查这三道题的条件、分类、答案和证明，只输出问题清单，不修改原稿。

> 使用 math-handout-author 按指定教学库的现行复习讲义规范制作一份 20 分钟草稿；保留来源，标出未核实的属性和检测独立性。

> 使用 math-item-ingest 核对这个返回包与既有题目索引，只整理候选、复用和待核清单，不修改正式库。

Mathsemble 说明是可选适配参考，不是该插件所有版本的统一契约。请核对实际版本和设置；普通 Obsidian 折叠不等于学生版删除答案。

## 验证状态

初始个人候选完成了结构与参考链接检查、10 个虚构数学审校场景，以及两项讲义前向试作（最值微讲义、行列式阅读提纲）。另做了规范一致性复核。

本公开版移除了个人姓名、私有仓库／对话地址与环境快照，并将规范导航改为可配置说明；发布准备进行了结构、引用和隐私字符串检查。**上述历史行为测试不是公开脱敏版的重新全量行为验证。**

新增 `math-item-ingest` 完成结构、引用和针对性隐私检查，以及独立只读复核。隔离前向任务覆盖 7 组虚构来源、8 条片段，另增补不可读取的图片答案场景；已核对实际输出，未修改正式题库。任务与边界见 [题目吸收定向回归](evals/item-ingest.md)。这是单次定向验证，不代表真实自动路由、OCR／图片识别或正式接入已经通过。

尚未完成有／无 Skill 对照、广泛真实教学库试用、复杂图形全量核验、真实 Obsidian／双版 PDF／打印或课堂效果验证。Skill 指令不能保证数学正确，工具检查不能替代独立证明及人工判断。

## 来源与许可状态

见 [设计参考](REFERENCES.md)。本仓库公开可见，但当前未选择开源许可证；不应视为已经授予 MIT、Apache 等通用复用许可。后续许可由作者决定。

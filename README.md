# lhg-net · 互联网取数层

> **一句话**：给 AI 智能体装上中文优先的互联网取数能力：14 个平台后端链，工具→流程双轨降级，取不到就诚实说。
>
> **一键安装**：`npx skills add lhg-skills/lhg-net`


给 AI Agent 装"互联网眼睛"的 skill：**只负责把公开内容取回来，不负责分析**（lhg-skills 出品，能力层方法论借鉴 Panniantong/Agent-Reach（MIT），文本独立重写）。

**核心机制**：① 中文优先——抖音/微博/B 站/小红书/雪球/V2EX/小宇宙/微信公众号等 8 个中文平台为一等公民，另保留 Twitter/X、Reddit、YouTube、GitHub、HN、LinkedIn，每平台一条"首选→备选→纯流程降级"有序后端链；② 工具→流程双轨制——有外部工具走工具链，无工具/容器环境走纯流程（联网搜索定位 → 抓取全文 → 公开 API/网页版直取），零外部依赖也能跑；③ 触发收窄——开放式调研/热点选题/写作分别指路 lhg-deep-research / lhg-trend / lhg-writing，lhg-net 只做"取数"；④ 动手前先做能力体检（真实探测后端可用性，坏掉的给修复处方）；⑤ 常驻规则：开工声明"用 X 平台/Y 后端"、失败按重试链处理不瞎猜、多平台并行收集再汇总；⑥ 安全默认：只读不发帖、Cookie 只存本地、登录态建议用小号。

**触发**：用户说"帮我搜一下某平台的内容 / 抓个网页全文 / 拉个视频字幕 / 看看某话题在各平台的讨论 / 某账号最近发了什么"时使用——先过 NOT for 清单，需要分析结论的走 lhg-deep-research。

## 安装

一键安装：`npx skills add lhg-skills/lhg-net`

- 通用：将本仓库放到各平台的 skill 目录（如 `~/.agents/skills/lhg-net/`，注意 SKILL.md 须在目录根）。
- Coze：在扣子编程（code.coze.cn）→ 导入项目 → 本地上传本仓库 zip 包，平台会识别为 skill 类型。
- Trae：设置 → 技能 → 上传技能，选择本仓库 zip 包（或把目录放到 `~/.trae-cn/skills/`，国区版注意路径）。
- 平台无关：本 skill 写法平台中立（联网搜索/抓取全文/只读子 agent/任务清单/文件搜索/编辑），不依赖任何单一生态的专有工具名。

## 自检与反馈

本 skill 每次执行后自动做一次轻量自检（对照 NOT for 清单/后端链顺序/常驻规则/安全默认）；只有发现疑似自身缺陷时，才运行 `references/smoke-test.md` 标准用例并输出质检报告。报告经你确认后，可一键向 GitHub 提交 `[QC]` issue（模板见 `.github/ISSUE_TEMPLATE/qc-report.md`）。

## 与 lhg 系列的分工

- lhg-net：眼睛，只取数（本 skill）
- lhg-deep-research：脑子，开放式调研与深度分析
- lhg-trend：雷达，近 30 天热点扫描与选题
- lhg-writing：笔，写作与去 AI 味
- lhg-craft / lhg-debug / lhg-secure：代码工程、调试、安全审计

## 版本

- 1.0.0（2026-09-29）：首版。中文优先 14 平台后端链 + 工具→流程双轨制 + 触发收窄（NOT for 清单）+ 能力体检 + 常驻规则 + 安全默认 + 冒烟脚本；能力层方法论借鉴 Panniantong/Agent-Reach（MIT），文本独立重写。

## 什么时候用 / 什么时候不用

**用它，当你**：
- 需要 AI 帮你查中文互联网的信息（新闻、社媒、商品、论文）
- 做热点扫描、竞品监控等需要稳定取数的任务

**别用它，当你**：
- 只需要英文 Google 搜索就够了

---

## lhg-skills 矩阵

刘洪光出品的中文 Agent Skills，全开源：

| Skill | 名称 | 一句话 |
|---|---|---|
| `lhg-writing` | 中文写作 | 风格指纹 → Orwell 六规则 → AI 味诊断，写出有人味的中文 |
| `lhg-slides` | HTML 演示文稿 | 大纲/文档一键生成可编辑的单文件 HTML slides |
| `lhg-trend` | 近30天热点扫描 | 话题火不火、为什么火、还能不能追 |
| `lhg-deep-research` | 深度调研 | 多源检索 → 结构化中文调研报告 |
| `lhg-benchmark-topic-factory` | 对标拆解选题工厂 | 找对标 → 逆向 100 条选题库 → 口播文案 |
| `lhg-net` | 互联网能力层 | 中文优先多平台取数，取不到诚实说 |
| `lhg-craft` | AI 编程工程规范 | 分级澄清 → TDD → 独立评审 → 证据门禁 |
| `lhg-debug` | 系统化调试 | 复现 → 定位 → 修复 → 验证 |
| `lhg-secure` | 代码安全审计 | 九维度扫描 + 对抗验证，分级风险清单 |
| `lhg-finder` | 找 skill 质检门 | 装第三方 skill 前的 blocker 检查 + 六维评分 |

安装任意一个：`npx skills add lhg-skills/<上表 slug>`

---

## 出品：刘洪光

本 skill 由真人出镜 IP「刘洪光」（安徽合肥）出品，归属 [lhg-skills](https://github.com/lhg-skills)。

- GitHub 主页：https://github.com/lhg-skills —— 全部 skill 开源在此，欢迎 star
- 视频号：搜「刘洪光实名上网」
- 微信：lhgsmsw

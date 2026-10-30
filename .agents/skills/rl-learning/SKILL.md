---
name: rl-learning
description: Teach and resume the Mathematical Foundation of Reinforcement Learning textbook through bilingual interactive study, derivations, exercises, and evidence-based progress. Use when starting, continuing, reviewing, or practicing this specific course.
---

# 强化学习数学基础协作学习

## 接续与准备

读取仓库根 `AGENTS.md`、`LEARNING.md`、`LEARNING-GUIDE.md`；以 `LEARNING.md` 为唯一断点权威。若有未答问题，重述并等待用户作答，不泄露答案。首次开始时了解目标，针对概率、线代、微积分或优化做适量诊断；诊断只指示补课，不宣称掌握或自动跳章。根据用户选择调整节奏，不预设已有基础。

读取正在学习的英文教材 PDF、适用的勘误和必要的先修上下文；明确文件、版本、章节和书中页码（与 PDF 页码有差异时同时写明）。使用实际内容，不凭记忆编章节、定理、符号或题目。遇到 PDF 提取不完整时检查原页；不能确认时明说。按需使用课件与 Grid World 代码，标明它们与正文的关系。学习状态中的来源版本用于追溯，作者更新之后保留原记录并标记待复核。

## 互动教学

保留 English terms、notation 与必要短句，用中文解释和反馈；解释术语与公式含义，不要求逐章全文翻译。一次推进可理解的小段，先联系直觉或 tiny MDP，再逐步展开符号、条件、推导与结论；在关键点提出一个可回答的问题，等待用户本人回答后判断并继续。用户说没懂时，定位具体卡点，换例子或分级提示，再用新问题复检；不因助手讲完而宣布掌握。

强化学习尤其要区分 state、action、policy、transition、reward、return 及其条件分布；核对 Markov 假设、时间范围、discount 和收敛条件。推导 Bellman 方程时明确条件期望与求和索引；最优性中的 max 与期望顺序按教材假设检查。涉及采样、行为策略、目标策略、on/off-policy 或收敛定理时，讲清各自条件及结论的范围。将直觉、定理证明、代码模拟和实验结果分开。

习题先给问题和必要条件，隐藏答案。讲解中逐步互动；课后测验默认一次展示整组题目，等待集中回答后逐题反馈，用户可调整节奏。优先让用户手算、预测、解释或推导，再按需运行小规模代码；不将选择题正确当作证明能力。对代码结果明确手算预测、实际执行和用户独立完成的区别；运行前说清环境和资源成本，不擅自启动昂贵训练。

## 协作、记录与暂停

主 Agent 对教材和答案负责，可按需委派独立资料核对、公式复算、习题设计或实验复核；子 Agent 不能代替用户作答。不同 Agent 不并发写同一文件，主 Agent 审阅冲突与证据后整合。无子 Agent 时可自行完成。

课末、暂停或上下文切换时更新 `LEARNING.md`：来源文件、实际版本／页码、已完成与证据、困难、待复习、下一步，以及未答问题及其状态。保留既有记录，不造成绩或结果；用户只问一个问题且没有状态变化时不写。产物放 `learning-artifacts/` 并保留来源；实验注明代码版本、环境、seed、预算、指标、实际输出与限制。此 fork 可能公开，不记录私密内容或凭据。后续提交、推送按当次授权和仓库规则执行。

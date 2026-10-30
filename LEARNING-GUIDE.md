# 学习指南

## 开始和继续

在仓库对 Agent 说“开始学强化学习数学基础”或“继续学习”。Agent 先读 [学习状态](LEARNING.md)，核对教材和勘误，再以中英混合方式分小节互动。未开始时先针对目标、概率与线代基础做轻量摸底；它只决定补什么，不自动跳章。暂停时会留下可直接恢复的问题和来源位置。

## 学习路径

以 [目录](1%20-%20Table%20of%20contents.pdf) 和各章实际内容为准，按依赖推进：

1. [基本概念](3%20-%20Chapter%201%20Basic%20Concepts.pdf) → [状态价值与 Bellman 方程](3%20-%20Chapter%202%20State%20Values%20and%20Bellman%20Equation.pdf) → [最优价值与 Bellman 最优方程](3%20-%20Chapter%203%20Optimal%20State%20Values%20and%20Bellman%20Optimality%20Equation.pdf)。
2. [价值迭代与策略迭代](3%20-%20Chapter%204%20Value%20Iteration%20and%20Policy%20Iteration.pdf) → [Monte Carlo](3%20-%20Chapter%205%20Monte%20Carlo%20Methods.pdf) → [随机逼近](3%20-%20Chapter%206%20Stochastic%20Approximation.pdf)。
3. [Temporal-Difference](3%20-%20Chapter%207%20Temporal-Difference%20Methods.pdf) → [价值函数方法](3%20-%20Chapter%208%20Value%20Function%20Methods.pdf) → [Policy Gradient](3%20-%20Chapter%209%20Policy%20Gradient%20Methods.pdf) → [Actor-Critic](3%20-%20Chapter%2010%20Actor-Critic%20Methods.pdf)。

必要时查 [附录](4%20-%20Appendix.pdf)、[课件](Lecture%20slides/) 和 [Grid World 代码](Code%20for%20grid%20world/)。参考书与勘误可能更新，页码和版本需核对。讲解从直觉和小例子进入，再依需要推导；用户先预测再检查或运行，课后测验默认一次给出整组题目，作答后反馈，不提前泄露答案。遇到困难逐级提示并复检。

## 协作与产物

主 Agent 负责教学、核对来源和保持断点；可按需让其他 Agent 独立核查公式、设计不泄题的练习或复核实验，再由主 Agent 核实并合并结果。子 Agent 不代替学习者作答，也不并发改同一文件。学习产物放 `learning-artifacts/`，写明原文文件、页码和提交；可记录手算或可复现代码，明确区分未运行、实际运行与学习者独立完成。

同步上游时调用 `rl-upstream-sync` 或说“检查并同步教材上游”；先检查状态与差异，审阅冲突和受影响的学习材料。推送单独受当次授权约束。

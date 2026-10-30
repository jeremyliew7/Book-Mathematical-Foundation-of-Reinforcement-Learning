---
name: rl-upstream-sync
description: Inspect and safely synchronize this reinforcement learning textbook fork with its author upstream, including effects on personal learning materials. Use for requests to check or merge textbook updates.
---

# 同步教材上游

先读仓库 `AGENTS.md` 和 `LEARNING.md`。确认 Git 根、当前分支、HEAD、`origin` 与 `upstream` 的 fetch/push 地址、跟踪分支、工作区、暂存区、进行中的合并或 rebase 及并发活动。不得动其他会话的暂存、改动或 stash；不自动 stash、reset、clean、切分支或强推。状态不安全或目的不明时停止，报告具体阻碍。

执行本次授权的 fetch，分别比较 `origin/main`、`upstream/main` 与本地历史；检查上游新增提交及其父子差异，不把两棵端点树的差异直接当成上游变更。查看将受影响的教材、勘误、代码和个人学习材料，必要时用 merge-tree 预检。仅要求检查时不合并；获得同步授权且状态安全时，将 `upstream/main` 合并到个人 main，保留个人提交。若出现冲突，逐项理解和解决，保留上游原件与个人材料，不静默选边；无法确认时保留冲突并说明。

检查学习笔记、练习与实验的来源文件、页码、版本与新教材是否漂移；受影响而尚未核实的标为待复核，不能改写既有学习证据或成绩。验证远程配置、合并结果、个人资料和链接；只暂存本次明确路径，检查完整暂存差异、凭据、私密信息和生成物。提交按仓库规则；只有当次明确授权才推送，普通 push 且检查目标和结果。报告上游版本、实际变更、验证、冲突和未完成事项；仅 fetch 或进程存活不等于同步完成。

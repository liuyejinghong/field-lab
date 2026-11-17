# 实战工坊 / Field Lab

Tools for working with AI coding agents, built and refined on real projects. Each tool started as a workaround for a failure we actually hit, and keeps changing as we use it.

---

给 AI 编程 Agent 用的工具集，都在真实项目里做出来、用下来，再持续改。每个工具都源自一次真实踩坑：先在项目里临时解决，确认是反复出现的问题后，整理成通用的做法和工具，再在后续工作中边用边修。

这里收的工具有三个共同点：

- **通用**：不绑定特定项目、语言框架或模型。项目自己的规则由工具读取，不写进工具里。
- **有依据**：规则说明来源与证据强度；实测数据来自哪里、样本多大、哪些阈值还没校准，都写明。
- **小而独立**：每个工具是独立仓库、独立版本，可以单独安装和使用。

## 工具

| 工具 | 做什么 | 形态 |
| --- | --- | --- |
| [review-standard](https://github.com/liuyejinghong/review-standard) | 代码审查标准：按风险分级决定审几人、怎么分工，规定什么问题值得报、怎么核实、何时停；支持改动审查与存量审查 | Agent skill（Markdown） |
| [maintainability-scorecard](https://github.com/liuyejinghong/maintainability-scorecard) | Python 项目结构体检：巨型函数与文件、循环依赖、改动热点、异常与兼容残留、测试写法，可跨提交对比 | 命令行 + Agent skill（Python 标准库） |

两者可以配合：审查标准在需要量化结构变化时调用记分卡取数。

已归档：[full-spectrum-review](https://github.com/liuyejinghong/full-spectrum-review)（v0.13.0，通用规则已并入 review-standard 0.2.0）。

## 安装

每个工具的 README 有各自的安装说明。作为 Claude Code skill 使用时，把仓库克隆到任意目录，再在 `~/.claude/skills/` 下建一个指向它的链接：

```bash
git clone https://github.com/liuyejinghong/review-standard.git ~/field-lab/review-standard
ln -s ~/field-lab/review-standard ~/.claude/skills/review-standard
```

## 同一作者的其他项目

- [Tripwire Bench · 踩雷榜](https://liuyejinghong.github.io/tripwire-bench-site/)：量化交易系统 coding benchmark，比较哪个模型最适合写和维护交易系统。

## 许可证

各工具分别以 MIT 许可证发布。

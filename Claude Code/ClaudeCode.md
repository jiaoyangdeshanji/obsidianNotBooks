1.安装
2.agents(子代理)
3.skills(技能)
4.hooks(钩子)
5.commands(命令)
6.规则
7.MCP配置
8.插件

8.项目开发流程



经验
### 1.合理使用Agents
利用项目中的 Agents 配置，把 Claude 分裂成===不同的角色=== ：
1.Planner Agent：负责在写代码前由 AI 自动生成架构图和实施计划，避免了盲目编码导致的返工，在黑客松中这个很重要。

2.Code Reviewer Agent：在代码提交前自动审查，确保演示时不会因为低级错误，比如语法错误、未捕获的异常啥的，导致 Demo 失败。
### 2.克服上下文腐烂
在长达 8 小时的连续 Coding 中，普通 AI 往往会忘记之前的设定

利用配置中的 Skills 和 Rules，强制 AI 始终遵循特定的 TDD测试驱动开发模式，保持了代码逻辑的一致性。
### 3.MCP的使用
通过配置 MCP 工具，比如 GitHub MCP, Supabase MCP等。

让 Claude 直接操作数据库和代码仓库。这意味着他们几乎不需要手动去数据库建表或在 IDE 之间来回切换，极大缩短了开发周期

项目开发
1.新项目启动阶段:
	用/plan命令调用planner/architect 等 agents，帮助梳理目标功能、选择技术栈并划分模块边界。
	
2.启用 coding-style.md、security.md、testing.md 等规则文件，把团队统一的编码规范、安全要求和测试标准固化下来，让后续所有对话和生成代码都在同一工程轨道上运行

3.
	在具体开发过程中，采用 TDD + 验证循环的方式：通过 /tdd 命令让 Claude 按 RED → GREEN → REFACTOR → VERIFY 的流程推进开发。

4.
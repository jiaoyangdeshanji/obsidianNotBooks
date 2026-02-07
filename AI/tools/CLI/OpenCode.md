# 优势
开箱即用的免费模型,通过简单配置可以接入Gemini 3 pro和Claude 4.0 Opus等顶级编程模型,open code可以看作是一个开源版的cloud code,几乎具备了cloud code的一切功能,而且对中国用户友好,不会遇到cloud code里面限速,封号等一系列麻烦的事情,而且不限制模型

# 1.形态
## 1.命令行
1.安装
2.开启
在终端输入opencode命令,即可进入opencode
```
	opencode
```
安装目录
```
C:\Users\boss\.config\opencode
```
2.桌面客户端 -- 不推荐
	BUG多

## 3.插件
	基于已经安装命令行方式,
### 1.vscode



4.云端运行环境
# 2.命令行

|           |                                                                                                   |
| --------- | ------------------------------------------------------------------------------------------------- |
| /models   | 查看模型(带free标签的都是免费使用的)                                                                             |
| /connect  | 查看大模型接入的方式                                                                                        |
| /new      | 在运行的线程中开启新的线程                                                                                     |
| /session  | 查看正在运行的线程                                                                                         |
| /share    | 把当前窗口的对话记录分享成一个网页(网页地址默认到粘切版,用浏览器打开即可)                                                            |
| /unshare  | 网页地址失效                                                                                            |
| /export   | 把所有窗口对话记录做成文件输出                                                                                   |
| /timeline | 时间线/检查点,看到对于AI聊天的时间节点,选择某个对话记录,<br>选择'revert undo messages and file changes'把代码跟聊天内容一起回滚这次对话之前的状态 |
| /mcp      | 查看已安装的mcp                                                                                         |
|           |                                                                                                   |

# 3.接入其他模型方式
```
	使用/connect 查看大模型接入的方式
```
## 1.Gemini 3 pro和Claude 4.0

	使用opencode-antigravity-auth插件把Gemini 3 pro和Claude 4.0 Opus两个顶级模型免费的接入入open code里面使用
### 安装
1.在github复制安装命令
2.把命复制到opencode对话框,让AI帮忙安装

## 2.codex
	安装

## 3.open router
# 4.亮点
1.先做开发计划,分步完成

```
	在开始编程前,先咨询关键问题(有哪些功能是必须实现,调用哪个I模型,环境变量是怎么保存的),把所有的需求细节询问清楚,列出了一个详细的开发计划,并且分步骤完成,每完成一步都会标记出完成
```

2.命令行版的代码比对界面
5.概念
1.session
我们每次跟AI开启了一个新的对话,就是一个全新的session,session可以后台运行,而且可以多个session并行运行
在第一个功能实现过程中,我们输入/new命令打开一个新的窗口,然后输入第二个功能的需求后,输入/session命令,就可以看到正在运行的任务数量,任务名称前面在打转的符号(表示它正在后台运行)
2.share

# 5.MCP
1.local -- 本地命令执行
进入opencode的安装目录(C:\Users\boss\.config\opencode)打开opencode.json文件在里面输入

2.remote -- 远程调用

```
{

"$schema": "https://opencode.ai/config.json",

"mcp": {
--本地本地命令执行方式

"第一个mcp的名字": {

"type": "local",

// Or ["bun", "x", "my-mcp-command"]

"command": ["npx", "-y", "my-mcp-command"],
--启动

"enabled": true,
--环境变量

"environment": {

"MY_ENV_VAR": "my_env_var_value",

},

},

},
--远程方式
"第二个mcp的名字": {

"jira": {

"type": "remote",

"url": "https://jira.example.com/mcp",

"enabled": true

}

}

}

```
# 6.推荐插件
1.oh my openCode
本质上就是一系列的工具加MCP,加编程agent的组合捆绑包
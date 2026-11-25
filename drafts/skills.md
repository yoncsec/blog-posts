# 【必出洞的渗透skills分享】零基础挖漏洞，赚赏金，就来网络安全透视镜

AI时代挖漏洞真的没那么难。挖漏洞的第一性原理是：

你自己得会挖，至少得懂一些，没AI时候你都挖不到漏洞，有AI了，你上来也是一脸茫然。

稍微懂一点后，就好办了。想靠挖漏洞赚赏金的第一性原理就是

强的AI模型+Skills

有些人还花几千买skills，这里分享一些免费又实用的skills，实测src都出货了。

                                        AI的选择

国外的模型基本都有限制，但不是不可用，国外模型推荐：grok-4.5, grok-4.6, claude-opus-4.6 这些限制低，能力还不错的模型。

开源模型推荐：glm-5.3, glm-5.3-flash, deepseek-v4-pro, deepseek-v4-flash。 kimi-3也很不错，就是太贵了。

AI推荐：https://coding101.site

                                         AI工具的选择

也不必追求网上各种AI渗透工具，其实常见的codex ,claude code, workbuddy , trae 这些都是够用的。下期再做AI工具的推荐

                                          Skills推荐

🥇 No.1

Claude-BugHunter

elementalsouls / Claude-BugHunter

4,017 ★

目前 GitHub 上 bug bounty 领域最热的 skill 包。

**82 个 skill + 15 个 slash command**，覆盖 24 个核心漏洞类别，内置 681 份已披露报告模式，直接复用真实 hunter 的攻击路径。

对企业身份攻击和基础设施攻击单独做了矩阵，适合大规模红队外部渗透。

git clone https://github.com/elementalsouls/Claude-BugHunter ~/.claude/skills/bughunter

┄┄┄

🥈 No.2

Raptor

gadievron / raptor

3,690 ★

GitHub Trending 榜首级别的存在。

和 BugHunter 不太一样，Raptor 不是「工具集」，而是**把 Claude Code 改造成通用 AI 攻防 agent 的方法论框架**。通过 Claude.md + 子 agent + skills 三层架构，自动编排完整攻击链。

侦察 → 入侵 → 横向移动 → 后渗透，全程能看 demo 视频，攻防双模式，既能攻也能演练防御。

git clone https://github.com/gadievron/raptor ~/.claude/skills/raptor

┄┄┄

🥉 No.3

Claude-Red

SnailSploit / Claude-Red

3,011 ★

SnailSploit 是专门做 GenAI 安全研究的团队，Claude-Red 是他们的攻击性技能库。

**37 个 drop-in 技能**，每个独立可用，覆盖 SQLi/XSS/SSRF/SSTI/XXE/Shellcode/EDR 规避/漏洞利用开发。

分类是它最大的亮点：Web 应用、Auth、AD、Wireless、Cloud、Mobile、IoT、基础设施 8 大类全打通，需要什么 load 什么，绝不拖泥带水。

git clone https://github.com/SnailSploit/Claude-Red ~/.claude/skills/claude-red

┄┄┄

No.4

Claude-OSINT

elementalsouls / Claude-OSINT

2,479 ★

和 No.1 是同一个作者，OSINT 是 BugHunter 的姊妹篇。

8 个 skill 文件，**100+ 侦察能力**，80 个 secret-regex 模式，80+ Google dorks，9 个只读凭据验证器，27 个攻击路径模板。

专做授权红队和 bug bounty 侦察阶段。和 BugHunter 配对使用，组成完整「侦察 + 挖掘」工作流。

git clone https://github.com/elementalsouls/Claude-OSINT ~/.claude/skills/osint

┄┄┄

No.5

iothackbot

BrownFineSecurity / iothackbot

819 ★

榜单里唯一一个 IoT 专项。

**固件分析 + 硬件接口（UART/JTAG/SWD）+ 无线协议（ZigBee/BLE/NFC）**。你挖路由器、摄像头、智能家居网关，别的 skill 用不上，这个能直接用。

Star 不到 1k，但垂直领域里没有对手。

git clone https://github.com/BrownFineSecurity/iothackbot ~/.claude/skills/iothackbot

┄┄┄

⭐ No.6 · SRC 挖洞首选

src-hunter-skill

MyuriKanao / src-hunter-skill

605 ★

这一条我必须单独拎出来说。

它和前面五个不是一类东西——前面是综合性的，这是**专门为国内 SRC 挖洞场景写的**。作者 MyuriKanao 把它做成了一条流水线：

**intake → recon → enum → hunt → report**

给它一个目标域名，它会按这五步自己跑完。

数字很炸裂——19 个攻击 playbook，每个都嵌了真实 HackerOne 案例（IDOR 465 例、RCE 385 例、XSS 335 例、信息泄露 319 例），305 个结构化 payload，263 个 WAF/EDR 绕过步骤，2887 份 HackerOne High/Critical 报告做底层数据。

还集成了一个 MCP（jshookmcp 0.3.0），134 个工具精选，浏览器自动化、JS hook、Frida、WASM 逆向全打通。

最让我服气的是它的**红线规则**——每个 playbook 末尾都写了边界：

SQLi 拿到库名/版本就停，IDOR 拉 1-3 条样本就够，RCE 只跑 id/whoami，Redis 未授权只 info 一下……

这种东西，是真的懂 SRC 规则的人才会写。

/plugin marketplace add MyuriKanao/src-hunter-skill

┄┄┄

No.7

communitytools

transilienceai / communitytools

498 ★

transilienceai 出的开源社区集合，包含 skills、agents、slash commands 三件套。

社区驱动，适合作为自建技能库的底座——你想搭一套团队专属的渗透工具集，先把这个 fork 下来再删减，比从零开始快得多。

git clone https://github.com/transilienceai/communitytools ~/.claude/skills/community

┄┄┄

No.8

bountyforge

Gabson0x / bountyforge

406 ★

如果你做 Web3 漏洞赏金（Immunefi、Code4rena），这个是榜单里唯一一个同时支持 Web2 和智能合约的。

并行 agent 架构，**EVM / Move / Solana / TRON 全覆盖**，生成可直接提交到 HackerOne / Bugcrowd / Intigriti / Immunefi 的报告。

省事省心。

git clone https://github.com/Gabson0x/bountyforge ~/.claude/skills/bountyforge

┄┄┄

No.9

Black-cat

0rangec3t / Black-cat

304 ★

设计理念和其他所有 skill 都不一样。

普通 skill 是流水线（RECON → ENUM → VALIDATE 一条路走到底），**Black-cat 是状态机**：

**RECON ⇄ ENUMERATE ⇄ VALIDATE**

失败和新发现可以**回溯重启早期阶段**，每次发现都形成可验证的「假设」。

适合那种打到一半发现线索断了、需要跳回前一步换个角度继续挖的复杂目标。

git clone https://github.com/0rangec3t/Black-cat ~/.claude/skills/black-cat

┄┄┄

No.10

public-skills-builder

Awarexone / public-skills-builder

225 ★

榜单里唯一一个「造 skill 的 skill」。

从 500+ 份公开 HackerOne 报告和 GitHub writeup 中**自动生成** Claude skill 文件，覆盖 18 个漏洞类别。

你团队有自己专属的攻击方法论？扔 100 份内部报告进去，跑一遍，就能产出一套定制 skill。

git clone https://github.com/Awarexone/public-skills-builder ~/.claude/skills/skill-builder

— ★ —

04

一张表，按场景挑

看完还是不知道怎么选？我帮你按场景整理了一下：

|你的场景|首选|
|---|---|
|挖国内 SRC、做众测|src-hunter-skill|
|通用 Bug Bounty 全流程|Claude-BugHunter|
|全自动攻击链编排|raptor|
|侦察阶段专项|Claude-OSINT|
|多攻击面覆盖|Claude-Red|
|Web3 智能合约审计|bountyforge|
|IoT / 嵌入式渗透|iothackbot|
|复杂目标深度回溯|Black-cat|
|造团队专属 skill|public-skills-builder|

收藏这一张表，下次挖洞直接按场景对照。

  

AI推荐：https://coding101.site

  

最后提醒一句：

**所有这些 skill 只能在已授权的目标上使用**——SRC 公告的资产、众测平台授权范围、自己公司有渗透测试合同的目标。乱扫是要踩缝纫机的，这条不展开，懂的自然懂。

如果觉得有用，点个在看，转发给身边做安全的朋友。
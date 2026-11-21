# makefun-beginner-guide

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/SUNPROAM/makefun-beginner-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/SUNPROAM/makefun-beginner-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

![新手教程截图](screenshot.png)

一份给新手的 make.fun 入门教程：不用自己写代码，让 AI agent 帮你写，赢了赏金直接拿 USDC。

**先注册，再往下看 —— 用这个链接注册：https://make.fun/r/08kqq9fr**

## Run it

```sh
git clone https://github.com/SUNPROAM/makefun-beginner-guide.git
```

这份教程就是一个 Markdown 文件，克隆下来用任何编辑器打开就能读。

## 1. make.fun 是什么

make.fun 是一个“AI agent 编代码赢赏金”的平台。流程很简单：

1. 平台挂出一个赏金任务（bounty），比如“写一个 4KB 象棋引擎”“做一个浏览器小游戏”“克隆一个 Git 服务”。
2. 你（或者你的 AI agent）写出代码，提交到一个公开的 GitHub 仓库。
3. 平台在沙箱里跑你的代码、打分、排名。
4. 进了付费名次，奖金以 USDC 发到你的 Solana 钱包。

奖金是真的钱，不是积分。每个赏金的奖金池、付费名次、截止时间都在它的赏金页面上写得清清楚楚，提交之前先看一眼。

## 2. 注册：三分钟

1. 打开我的推荐链接注册：**https://make.fun/r/08kqq9fr**（走推荐链接注册，你的奖金一分不少；平台另外给我推荐奖励）。
2. 注册就是建一个 Solana 钱包（keypair）。钱包既是你的账号，也是你的领奖地址。
3. 记好两样东西：keypair 文件（一般是 `makefun-keypair.json`）和 API key。
   - keypair 文件只有你能看（权限 600），**永远不要发给任何人**，不要贴到聊天记录、截图、issue 里。
   - API key 30 天过期，到期用同一个 keypair 重新注册一次就能续。

就这么多，不用手机号，不用身份证，不用绑卡。

## 3. 选第一个赏金：别贪大

新手第一次，别冲着奖金最高的去。按这四个条件挑：

- **免费参加。** 大多数赏金免费，个别有报名费。第一次只做免费的。
- **截止时间够。** 至少留出一天，别卡着截止前一小时才动手。
- **有本地可测的分数。** 赏金包里带 `grade-local` 的最好，先在自己电脑上跑出分数再提交，心里有底。
- **任务看得懂。** 读一遍赏金页的规则（rules）和要求（requirements），知道要交什么、怎么算分，再动手。

常见的第一单：小游戏、象棋引擎、数据榜单这类“做出来就能跑”的任务，比要接真实 API、要跑长期策略的任务友好得多。

## 4. 让 AI agent 写代码：你是指挥，不是码农

make.fun 是给 AI agent 办的比赛，你不需要自己一行行写代码。做法是：

1. 把赏金包（kit）下载下来，里面有任务说明、测试数据和提交用的命令行工具。
2. 开一个新的 agent 会话（Claude Code、Cursor、Codex，或者你自己的 agent），把任务交代清楚，让它在会话里写代码。
3. **关键的一步：先录制，再开工。** 平台要检查“代码真是你的 agent 写的”，所以提交时要附上 agent 会话的 transcripts（记录）。有的赏金要求开录制（`makefun record`），有的只要求打包会话记录（`makefun bundle`）。不管哪种，都是先开始记录，再让 agent 写代码——顺序反了，记录作废。
4. 让 agent 自己跑测试、修 bug，跑通了再提交。提交之前，先在本地用 `grade-local` 跑一遍，和平台打分的方式一样。

几条铁律：

- **不要复制别人的代码。** 抄别人的参赛作品、抄公开题解，检查会直接判不合格。
- **不要把 API key、钱包私钥写进代码或仓库。** 提交前检查一遍仓库里有没有密钥。
- **不要让 agent 替你花钱。** 报名费、领奖、下注，凡是动钱的步骤，先自己确认再动手。

## 5. 提交：仓库 + 记录，缺一不可

一次提交通常包括：

- **公开 GitHub 仓库**：代码放在里面，根目录要有 OSI 开源协议文件（比如 MIT 的 `LICENSE`）。
- **一个提交记录（commit）**：提交时要填这个 commit 的完整 SHA。
- **transcripts**：agent 写代码的会话记录，用 kit 的命令行工具打包（`bundle`）或者用录制（`record`）生成。
- **签名**：用你的钱包给提交信息签名，证明这个提交是你的。

提交成功会返回一个提交 ID（submission id），用它可以查状态：是通过了检查、正在打分，还是被哪个检查打回来了。被打回来不用慌，看清楚是哪一项检查没过，修好再交——只要在截止时间前、每天的提交次数没用完，就可以重新提交。

## 6. 领奖：进了名次才有，流程别急

- 结果公布后，进了付费名次才能领奖。奖金锁在链上托管（escrow）里，领奖就是从托管里把 USDC 提到你的钱包。
- 领奖时平台会问税务问题：**非美国人不用填 W-9**；如果一年累计奖金达到申报线，再按平台提示填表。
- 领奖没有截止时间压力，但也别拖太久，按页面提示操作就行。

没进付费名次也别灰心：很多赏金有参与奖（participation reward），进了打分、没赢钱也能拿一小笔；而且每次参赛的仓库和经验，下次都能复用。

## 7. 推荐奖励：不参赛也能赚

除了自己参赛赢奖金，推荐别人注册也能赚钱：

- 把你的推荐链接发给朋友：`https://make.fun/r/<你的推荐码>`。
- 别人通过你的链接注册、参赛、赢了钱，平台按他奖金的 10% 另外给你发奖励，连发 90 天——这笔钱是平台出的，不从朋友的奖金里扣。
- 推荐奖励要审核一天以上才到账，能领的时候平台会提示。

## 8. 新手常见问题

**Q：我不会写代码，能参加吗？**
A：能。这就是这个平台存在的原因：你指挥 AI agent 写代码，你负责选题、验收和提交。

**Q：要花钱吗？**
A：参赛本身大多数免费。唯一可能花钱的地方是：个别赏金有报名费（提交前会明说）；agent 跑模型要花你自己的模型额度。钱包里不用预存 USDC 参赛。

**Q：赢了奖，多久到账？**
A：结果公布、挑战期过后才能领，领奖是链上操作，几分钟到账。别信任何“提前领奖”的链接，只在 make.fun 官方页面操作。

**Q：一个人能交几个作品？**
A：每个赏金每天最多交 5 次（不同国家档位可能更低），整个赏金最多 20 次。别浪费次数在没跑通的代码上。

**Q：提交被拒了怎么办？**
A：看拒绝原因，一个一个修。最常见的是：仓库不是公开的、缺 LICENSE、transcripts 对不上代码、仓库建得太早（必须在赏金开始后新建）。修好重新提交就行。

**Q：我的 agent 会话记录会被公开吗？**
A：不会。transcripts 只给平台检查用，不公开展示。

## 9. 十分钟上手清单

- [ ] 用推荐链接注册：https://make.fun/r/08kqq9fr
- [ ] 保存好 keypair 文件和 API key
- [ ] 打开赏金榜，挑一个免费、截止时间够、有本地评分的任务
- [ ] 下载赏金包，读一遍 rules 和 requirements
- [ ] 先开始记录（record / bundle），再让 agent 写代码
- [ ] 本地跑通 `grade-local`，提交，查状态
- [ ] 进了名次就领奖；没进就看看参与奖，再战下一个

---

<sub>Entered on [make.fun](https://make.fun/?ref=08kqq9fr&utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02) · AI agents build software for cash rewards</sub>

# zys-study-skills

一套自己天天在用、也踩过坑的学习方法，做成了 AI 能直接调用的 skill。

> 名字里的「20 倍速」是噱头。真东西是下面这 12 步——**前面 10 步负责学得懂，第 11 步负责忘不掉，第 12 步负责用得上。**

**EN** — A 12-step learning loop packaged as an AI skill. Steps 1–10 build real understanding: five-perspective STORM, a contradiction map, an active-recall exam, a Feynman loop, and a one-page cheatsheet. Step 11 keeps it from fading (spaced review at 24h / 7d / 30d). Step 12 turns it into something you can actually deliver. Most study methods stop at step 10 — which is exactly why everything you learned is gone three weeks later. Drop `skills/ai-20x-learning/` into your agent's skills folder and say "I want to learn X".

## 这是什么

一个 AI skill 仓库。clone 下来放进 skills 目录，跟 AI 说一句"我想学 XX"，它就会按 12 步闭环带你走，一次只走一步，不会一口气吐完。

跟市面上那些"三招学会任何东西"的区别：

- 不让 AI 单方面给你讲故事，让它演 5 个**互相打架**的专家，然后指认谁在胡说
- 不给你 50 个资源让你收藏吃灰，**只给 5 个**，按最近发展区排好顺序
- 不靠"看懂了"糊弄你，**先考试考到崩，再用费曼磨平**
- 学完不算完，**三个复习节点**把它钉进长期记忆，**一个真实产出**证明你没白学

## 包含的 skill

| Skill | 干什么 | 适合什么场景 |
|---|---|---|
| [`ai-20x-learning`](skills/ai-20x-learning/SKILL.md) | 12 步闭环学任何陌生领域 | 想快速入门一个领域、学完就忘、学了一堆用不上 |

## 12 步长什么样

```
第 0 步  30 分钟摸底（可选）  三问建地图，先决定值不值得学
   ↓
第 1 步  五视角 STORM        实践者 / 学者 / 怀疑者 / 经济学家 / 历史学家，各说各的
第 2 步  矛盾图谱            拉到一张桌互撕，看谁证据最硬
第 3 步  综合简报            CEO 总结 + 5 个发现 + 1 个隐藏关联
第 4 步  同行评审自检        自己给自己打分，找最没把握的地方
   ↓
第 5 步  资源筛选            只给 5 个，排成一周路径
第 6 步  学习阶梯            L1→L5，随时知道自己在哪一级
第 7 步  核心 20%            10 次课，2 小时拿下能干活的部分
   ↓
第 8 步  考到我崩溃          一次一题，主动回忆，答错就重讲
第 9 步  费曼循环            讲到 12 岁小孩能听懂为止
第 10 步 一页速查表          压成 5 分钟能过完的一页
   ↓
第 11 步 间隔复习            24 小时 / 7 天 / 30 天，三个节点
第 12 步 落地实战            做出一个外行能看懂、内行挑不出错的东西
```

**前四段（0–4）是开图，中段（5–10）是真正学，后两段（11–12）是留住和兑现。**
大多数人只做到第 10 步就收工，所以三周后归零。

## 怎么装

### WorkBuddy

```bash
git clone https://github.com/zhang123-666/zys-study-skills.git
cp -r zys-study-skills/skills/ai-20x-learning ~/.workbuddy/skills/
```

放项目里也行，只在这个项目生效：

```bash
cp -r zys-study-skills/skills/ai-20x-learning .workbuddy/skills/
```

### Claude Code / 其他支持 SKILL.md 的 agent

```bash
cp -r zys-study-skills/skills/ai-20x-learning ~/.claude/skills/
```

`SKILL.md` 用的是标准格式（YAML frontmatter + Markdown 正文），任何认这个格式的 agent 都能读。

## 怎么用

装好之后不用记命令，说人话就行：

```
我想学期权定价
帮我快速搞懂具身智能
XX 的资料太多了，不知道从哪看
学完就忘，有什么办法
```

触发之后它会先问你：**这个领域你手上有什么真材料？** —— 有就喂给它，五视角才不是凭空演。然后从第 1 步开始，一步一停，你说"下一步"才往下走。

想只花 30 分钟摸个底、不走完整流程，直接说"先帮我摸个底"。

## 为什么做这个

背景很实在：**时间被切得很碎**，能拿出来的整块时间不多。这种状态下最奢侈的不是钱，是"学了一个东西结果没用上"。

所以这套方法里的每一条都是在治具体的病：

| 病 | 药 |
|---|---|
| 收藏了 50 个资源，一个没看 | 只给 5 个，按最近发展区排 |
| 看了很多，讲不出来 | 第 8 步考试 + 第 9 步费曼 |
| 学完三周忘光 | 第 11 步三个复习节点 |
| 学完不知道怎么用 | 第 12 步落地实战，还给了验收三问 |
| AI 讲的听着有道理，其实在编 | 第 1 步先喂料 + 五视角互撕 + 第 4 步自检 |

## 目录结构

```
zys-study-skills/
├── README.md
└── skills/
    └── ai-20x-learning/
        ├── SKILL.md                        # 方法主体，12 步完整流程
        └── references/
            └── 具身智能-示例.md              # 一次完整跑通的实例，看它比看说明快
```

想看实际跑起来什么样，直接读 `references/具身智能-示例.md`。

## 说明

- 这套方法的前 10 步脱胎于我自己的「10 倍速学习法」，第 11、12 步是这次补的。原版留在本地知识库，这个仓库发的是升级版。
- 第 0 步的三个问题参考了李尚龙讲的一套 AI 学习法，已在文件里标注来源。
- 方法可以随便用、随便改。改完如果更好用，欢迎告诉我。

## License

MIT

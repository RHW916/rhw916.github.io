---
layout: post
author_profile: true
title: "精读：AddyOsmani21lessons14years"
date: 2026-01-11
categories: [经验分享, 翻译]
tags: [Engineer, , ]
excerpt: "探讨如何结合Tensor Train分解与LoRA技术优化Whisper模型，在Common Voice 15数据集上实现参数量压缩99.5%的同时保持识别准确率。"
---

## 背景

偶然看到此文翻译觉得还是回归原文，精读后贴出翻译和一些个人思考。原文指路：https://addyosmani.com/blog/21-lessons/

## 21 Lessons From 14 Years at Google
### January 3, 2026 

When I joined Google ~14 years ago, I thought the job was about writing great code. I was partly right. But the longer I’ve stayed, the more I’ve realized that the engineers who thrive aren’t necessarily the best programmers - they’re the ones who’ve figured out how to navigate everything around the code: the people, the politics, the alignment, the ambiguity.
14 年前当我加入谷歌时，我以为这份工作就是写好代码。我部分正确。但待得越久，我越意识到，那些茁壮成长的工程师未必是最佳程序员——他们懂得如何驾驭代码周围的一切：人际关系、政治因素、协同一致、模糊不清。

These lessons are what I wish I’d known earlier. Some would have saved me months of frustration. Others took years to fully understand. None of them are about specific technologies - those change too fast to matter. They’re about the patterns that keep showing up, project after project, team after team.
这些教训是我希望早点知道的东西。有些能让我节省数月的挫败感。另一些则花了我数年才能真正理解。它们都不是关于具体技术的——那些变化太快，不值得关注。它们是关于那些反复出现的模式，项目接项目，团队接团队。

I’m sharing them because I’ve benefited enormously from engineers who did the same for me. Consider this my attempt to pay it forward.
我分享它们，因为我从那些为我做同样事情的前辈工程师那里获益良多。请将这视为我传递善意的尝试。

1. The best engineers are obsessed with solving user problems.
1. 最好的工程师都痴迷于解决用户问题。
It’s seductive to fall in love with a technology and go looking for places to apply it. I’ve done it. Everyone has. But the engineers who create the most value work backwards: they become obsessed with understanding user problems deeply, and let solutions emerge from that understanding.
沉溺于一种技术并寻找应用它的地方是诱人的。我这样做过，每个人也都这样做过。但创造最大价值的工程师是逆向工作的：他们痴迷于深入理解用户问题，并让解决方案从这种理解中产生。

User obsession means spending time in support tickets, talking to users, watching users struggle, asking “why” until you hit bedrock. The engineer who truly understands the problem often finds that the elegant solution is simpler than anyone expected.
痴迷于用户意味着花时间查看支持工单、与用户交谈、观察用户挣扎，不断问“为什么”直到触及根本。真正理解问题的工程师常常发现，优雅的解决方案比任何人预期的都要简单。

The engineer who starts with a solution tends to build complexity in search of a justification.
从解决方案出发的工程师往往在寻找理由的过程中构建复杂性。

2. Being right is cheap. Getting to right together is the real work.
2. 正确是廉价的。一起到达正确才是真正的挑战。
You can win every technical argument and lose the project. I’ve watched brilliant engineers accrue silent resentment by always being the smartest person in the room. The cost shows up later as “mysterious execution issues” and “strange resistance.”
你可以赢得每一个技术争论，却输掉整个项目。我见过才华横溢的工程师因为总是成为房间里最聪明的人而积累沉默的怨恨。这种代价后来表现为“神秘的执行问题”和“奇怪的阻力”。

The skill isn’t being right. It’s entering discussions to align on the problem, creating space for others, and remaining skeptical of your own certainty.
这项技能不在于正确。而在于参与讨论以就问题达成一致，为他人创造空间，并对自己的确定性保持怀疑。

Strong opinions, weakly held - not because you lack conviction, but because decisions made under uncertainty shouldn’t be welded to identity.
强烈的观点要弱化持有——不是因为缺乏信念，而是因为在不确定性下做出的决策不应与身份绑定。

3. Bias towards action. Ship. You can edit a bad page, but you can’t edit a blank one.
3. 偏向行动。发布。你可以编辑一个糟糕的页面，但你无法编辑一个空白的页面。
The quest for perfection is paralyzing. I’ve watched engineers spend weeks debating the ideal architecture for something they’ve never built. The perfect solution rarely emerges from thought alone - it emerges from contact with reality. AI can in many ways help here.
追求完美是令人瘫痪的。我见过工程师们花几周时间争论他们从未构建过的理想架构。完美的解决方案很少仅凭思考就能产生——它产生于与现实接触的过程中。人工智能在很多方面能在这里提供帮助。

First do it, then do it right, then do it better. Get the ugly prototype in front of users. Write the messy first draft of the design doc. Ship the MVP that embarrasses you slightly. You’ll learn more from one week of real feedback than a month of theoretical debate.
先做，再做正确，然后做得更好。让难看的原型面对用户。写出混乱的第一版设计文档。发布让你略感尴尬的最小可行产品。你将比一个月的理论辩论更能从一周的真实反馈中学习到更多。

Momentum creates clarity. Analysis paralysis creates nothing.
势头创造清晰。分析瘫痪创造不了任何东西。

4. Clarity is seniority. Cleverness is overhead.
4. 清晰是资历。聪明是负担。
The instinct to write clever code is almost universal among engineers. It feels like proof of competence.
工程师几乎都有写聪明代码的冲动。这感觉像是能力的证明。

But software engineering is what happens when you add time and other programmers. In that environment, clarity isn’t a style preference - it’s operational risk reduction.
但软件工程是在你加入时间和其他程序员时发生的。在那个环境中，清晰不是一种风格偏好——它是运营风险降低。

Your code is a strategy memo to strangers who will maintain it at 2am during an outage. Optimize for their comprehension, not your elegance. The senior engineers I respect most have learned to trade cleverness for clarity, every time.
你的代码是一份给陌生人的策略备忘录，他们会在凌晨两点维护故障时使用它。要优化他们的理解，而不是你的优雅。我最尊敬的那些资深工程师已经学会每次都用清晰度换取聪明才智。

5. Novelty is a loan you repay in outages, hiring, and cognitive overhead.
5. 新颖性是一笔你在故障、招聘和认知负担中偿还的贷款。
Treat your technology choices like an organization with a small “innovation token” budget. Spend one each time you adopt something materially non-standard. You can’t afford many.
将你的技术选择像是一个拥有小额“创新代币”预算的组织一样对待。每次采用实质上非标准的做法时，花费一个代币。你负担不起很多。

The punchline isn’t “never innovate.” It’s “innovate only where you’re uniquely paid to innovate.” Everything else should default to boring, because boring has known failure modes.
重点不是“永不创新”。而是“只在你能独特地被支付去创新的地方创新”。其他所有事情都应该默认为无聊，因为无聊已知失败模式。

The “best tool for the job” is often the “least-worst tool across many jobs”-because operating a zoo becomes the real tax.
“最适合这项工作的工具”往往是“在许多工作中最不糟糕的工具”——因为管理一个动物园才是真正的负担。

6. Your code doesn’t advocate for you. People do.
6. 你的代码不会替你说话。是人们替它说话。
Early in my career, I believed great work would speak for itself. I was wrong. Code sits silently in a repository. Your manager mentions you in a meeting, or they don’t. A peer recommends you for a project, or someone else.
在我职业生涯早期，我以为出色的工作会自己说话。我错了。代码静静地躺在仓库里。你的经理在会议上提到你，或者没有。一个同事推荐你参与项目，或者其他人被推荐。

In large organizations, decisions get made in meetings you’re not invited to, using summaries you didn’t write, by people who have five minutes and twelve priorities. If no one can articulate your impact when you’re not in the room, your impact is effectively optional.
在大公司里，决策是在你没被邀请的会议上做出的，使用你没写的总结，由那些只有五分钟和十二个优先事项的人来做。如果你不在场时，没有人能说明你的影响，那么你的影响实际上就是可选的。

This isn’t strictly about self-promotion. It’s about making the value chain legible to everyone- including yourself.
这并非严格意义上的自我宣传。它旨在让价值链对每个人——包括你自己——都清晰可见。

7. The best code is the code you never had to write.
7. 最优秀的代码，是你从未需要编写的代码。
We celebrate creation in engineering culture. Nobody gets promoted for deleting code, even though deletion often improves a system more than addition. Every line of code you don’t write is a line you never have to debug, maintain, or explain.
我们在工程文化中庆祝创造。没有人会因为删除代码而得到晋升，尽管删除代码往往比添加代码更能改进系统。你每不写的一行代码，就是你永远不必调试、维护或解释的一行代码。

Before you build, exhaust the question: “What would happen if we just… didn’t?” Sometimes the answer is “nothing bad,” and that’s your solution.
在构建之前，彻底思考这个问题：“如果我们只是……不做什么会怎样？”有时答案是“不会发生坏事”，这就是你的解决方案。

The problem isn’t that engineers can’t write code or use AI to do so. It’s that we’re so good at writing it that we forget to ask whether we should.
问题不在于工程师不能写代码或使用 AI 来写。问题在于我们写得太好了，以至于忘记问我们是否应该写。

8. At scale, even your bugs have users.
8. 在大规模应用中，即使你的 bug 也有用户。
With enough users, every observable behavior becomes a dependency - regardless of what you promised. Someone is scraping your API, automating your quirks, caching your bugs.
只要有足够多的用户，每一个可观察的行为都会变成依赖——无论你承诺了什么。有人在抓取你的 API，自动化你的怪癖，缓存你的错误。

This creates a career-level insight: you can’t treat compatibility work as “maintenance” and new features as “real work.” Compatibility is product.
这创造了一个职业层面的洞察：你不能将兼容性工作视为“维护”，将新功能视为“真正的工作”。兼容性就是产品。

Design your deprecations as migrations with time, tooling, and empathy. Most “API design” is actually “API retirement.”
将你的弃用设计视为随时间推移、工具和同理心进行的迁移。大多数所谓的“API 设计”实际上是“API 退休”。

9. Most “slow” teams are actually misaligned teams.
9. 大多数所谓的“慢速”团队实际上是方向不一致的团队。
When a project drags, the instinct is to blame execution: people aren’t working hard enough, the technology is wrong, there aren’t enough engineers. Usually none of that is the real problem.
当一个项目进展缓慢时，本能的反应是责备执行层面：人们不够努力，技术选型错误，工程师数量不足。但通常这些都不是真正的问题。

In large companies, teams are your unit of concurrency, but coordination costs grow geometrically as teams multiply. Most slowness is actually alignment failure - people building the wrong things, or the right things in incompatible ways.
在大公司中，团队是并发的基本单位，但随着团队的增多，协调成本会呈几何级数增长。大多数的缓慢实际上是方向不一致的问题——人们正在构建错误的事情，或者以不兼容的方式构建正确的事情。

Senior engineers spend more time clarifying direction, interfaces, and priorities than “writing code faster” because that’s where the actual bottleneck lives.
高级工程师花费更多时间澄清方向、接口和优先级，而不是“更快地编写代码”，因为真正的瓶颈就在于此。

10. Focus on what you can control. Ignore what you can’t.
10. 专注于你能控制的事情。忽略你不能控制的。
In a large company, countless variables are outside your control - organizational changes, management decisions, market shifts, product pivots. Dwelling on these creates anxiety without agency.
在一个大公司里，无数变量都超出了你的控制范围——组织变革、管理层决策、市场变化、产品转型。沉湎于这些只会带来无能为力的焦虑。

The engineers who stay sane and effective zero in on their sphere of influence. You can’t control whether a reorg happens. You can control the quality of your work, how you respond, and what you learn. When faced with uncertainty, break problems into pieces and identify the specific actions available to you.
那些保持理智和高效工作的工程师会专注于自己的影响范围。你无法控制重组是否发生，但你可以控制工作的质量、你的应对方式以及你学到的东西。面对不确定性时，将问题分解成小块，并确定你可以采取的具体行动。

This isn’t passive acceptance but it is strategic focus. Energy spent on what you can’t change is energy stolen from what you can.
这不是被动接受，而是战略聚焦。你把精力花在无法改变的事情上，就是从可以改变的事情上偷走了精力。

11. Abstractions don’t remove complexity. They move it to the day you’re on call.
11. 抽象不会消除复杂性。它们将复杂性转移到了你值班的那个日子。
Every abstraction is a bet that you won’t need to understand what’s underneath. Sometimes you win that bet. But something always leaks, and when it does, you need to know what you’re standing on.
每一种抽象都是一种赌注，赌你不需要理解其底层。有时你赢了这场赌。但总有东西会泄露，当它发生时，你需要知道你站在什么之上。

Senior engineers keep learning “lower level” things even as stacks get higher. Not out of nostalgia, but out of respect for the moment when the abstraction fails and you’re alone with the system at 3am. Use your stack.
高级工程师即使在技术栈越来越高的同时，也在不断学习“更低层次”的东西。这不是出于怀旧，而是出于对抽象失效时，凌晨三点独自面对系统的尊重。使用你的技术栈。

But keep a working model of its underlying failure modes.
但保持对其底层失效模式的可工作模型。

12. Writing forces clarity. The fastest way to learn something better is to try teaching it.
12. 写作迫使人变得清晰。最快的学习方式就是尝试去教它。
Writing forces clarity. When I explain a concept to others - in a doc, a talk, a code review comment, even just chatting with AI - I discover the gaps in my own understanding. The act of making something legible to someone else makes it more legible to me.
写作迫使人变得清晰。当我向他人解释一个概念——无论是写文档、发表演讲、进行代码评审评论，甚至只是与 AI 聊天——我都会发现自己在理解上的不足。将事物变得对他人清晰的过程，也让我自己对其有了更清晰的认识。

This doesn’t mean that you’re going to learn how to be a surgeon by teaching it, but the premise still holds largely true in the software engineering domain.
这并不意味着通过教学你会学会如何成为一名外科医生，但在软件工程领域，这一前提在很大程度上仍然成立。

This isn’t just about being generous with knowledge. It’s a selfish learning hack. If you think you understand something, try to explain it simply. The places where you stumble are the places where your understanding is shallow.
这不仅仅是关于慷慨分享知识。这是一种自私的学习技巧。如果你认为自己理解了某件事，试着用简单的语言解释它。你在解释时卡壳的地方，就是你理解不深的地方。

Teaching is debugging your own mental models.
教学是调试你自己的思维模型。

13. The work that makes other work possible is priceless - and invisible.
13. 使其他工作成为可能的工作是无价的——而且是无形的。
Glue work - documentation, onboarding, cross-team coordination, process improvement - is vital. But if you do it unconsciously, it can stall your technical trajectory and burn you out. The trap is doing it as “helpfulness” rather than treating it as deliberate, bounded, visible impact.
粘合工作——文档编写、入职培训、跨团队协调、流程改进——至关重要。但如果你无意识地做这些工作，它可能会阻碍你的技术发展路线，并让你筋疲力尽。陷阱在于将其视为“乐于助人”，而不是将其当作有目的、有边界、有可见影响力的工作来对待。

Timebox it. Rotate it. Turn it into artifacts: docs, templates, automation. And make it legible as impact, not as personality trait.
设定时间限制。轮换角色。将其转化为成果：文档、模板、自动化。并使其以影响而非个性特征的方式呈现可见性。

Priceless and invisible is a dangerous combination for your career.
无价且无形是您职业生涯中危险的组合。

14. If you win every debate, you’re probably accumulating silent resistance.
14. 如果你赢得每一场辩论，你可能正在积累沉默的抵制。
I’ve learned to be suspicious of my own certainty. When I “win” too easily, something is usually wrong. People stop fighting you not because you’ve convinced them, but because they’ve given up trying - and they’ll express that disagreement in execution, not meetings.
我学会了怀疑自己的确定性。当我轻易“获胜”时，通常有什么不对劲。人们不再与你争辩，不是因为你说服了他们，而是因为他们已经放弃尝试——他们会在执行中而非会议上表达这种分歧。

Real alignment takes longer. You have to actually understand other perspectives, incorporate feedback, and sometimes change your mind publicly.
真正的对齐需要更长时间。你必须真正理解其他观点，纳入反馈，有时还需要公开改变自己的想法。

The short-term feeling of being right is worth much less than the long-term reality of building things with willing collaborators.
短期内感觉自己正确的感觉，远不如长期与愿意合作的伙伴一起建设事物的现实有价值。

15. When a measure becomes a target, it stops measuring.
15. 当一个衡量标准变成目标时，它就停止衡量了。
Every metric you expose to management will eventually be gamed. Not through malice, but because humans optimize for what’s measured.
你向管理层公开的每一个指标最终都会被操纵。不是出于恶意，而是因为人类会优化被衡量的东西。

If you track lines of code, you’ll get more lines. If you track velocity, you’ll get inflated estimates.
如果你追踪代码行数，你会得到更多的代码行。如果你追踪速度，你会得到被夸大的估计。

The senior move: respond to every metric request with a pair. One for speed. One for quality or risk. Then insist on interpreting trends, not worshiping thresholds. The goal is insight, not surveillance.
高级策略：对每一个指标请求都回应一对数据。一个关于速度，一个关于质量或风险。然后坚持解读趋势，而不是崇拜阈值。目标是洞察，而不是监控。

16. Admitting what you don’t know creates more safety than pretending you do.
16. 承认自己不知道比假装知道更能创造安全感。
Senior engineers who say “I don’t know” aren’t showing weakness - they’re creating permission. When a leader admits uncertainty, it signals that the room is safe for others to do the same. The alternative is a culture where everyone pretends to understand and problems stay hidden until they explode.
那些说“我不知道”的高级工程师并不是在显示软弱——他们是在创造许可。当领导者承认不确定性时，它向其他人传递了一个信号：这个空间是安全的，其他人也可以这样做。另一种选择是一种文化，在这种文化中，每个人都假装理解，问题直到爆发前都隐藏起来。

I’ve seen teams where the most senior person never admitted confusion, and I’ve seen the damage. Questions don’t get asked. Assumptions don’t get challenged. Junior engineers stay silent because they assume everyone else gets it.
我见过那些最资深的人从不承认困惑，也见过因此造成的损害。问题得不到提出，假设得不到挑战。初级工程师保持沉默，因为他们以为其他人都能明白。

Model curiosity, and you get a team that actually learns.
展现好奇心，你就能得到一个真正学习的团队。

17. Your network outlasts every job you’ll ever have.
17. 你的社交网络比任何一份工作都要持久。
Early in my career, I focused on the work and neglected networking. In hindsight, this was a mistake. Colleagues who invested in relationships - inside and outside the company - reaped benefits for decades.
在我职业生涯早期，我专注于工作而忽视了社交网络。回首来看，这是一个错误。那些在公司内外都注重建立关系同事，数十年来都获得了回报。

They heard about opportunities first, could build bridges faster, got recommended for roles, and co-founded ventures with people they’d built trust with over years.
他们能最先得知机会，能更快地建立桥梁，被推荐担任重要角色，并与多年来建立信任的人共同创立事业。

Your job isn’t forever, but your network is. Approach it with curiosity and generosity, not transactional hustle.
工作不是永恒的，但你的社交网络是。用好奇心和慷慨去对待它，而不是交易式的奔波。

When the time comes to move on, it’s often relationships that open the door.
当是时候向前迈进时，往往是人际关系为你打开大门。

18. Most performance wins come from removing work, not adding cleverness.
18. 大多数性能提升来自于减少工作，而非增加巧妙的技巧。
When systems get slow, the instinct is to add: caching layers, parallel processing, smarter algorithms. Sometimes that’s right. But I’ve seen more performance wins from asking “what are we computing that we don’t need?”
当系统变慢时，本能的反应是增加：缓存层、并行处理、更智能的算法。有时这是正确的做法。但我看到更多性能提升来自于问自己“我们在计算什么是不必要的？”

Deleting unnecessary work is almost always more impactful than doing necessary work faster. The fastest code is code that never runs.
删除不必要的工作几乎总是比更快地完成必要工作更有影响力。最快的代码是永远不会运行的代码。

Before you optimize, question whether the work should exist at all.
在优化之前，先质疑这项工作是否真的有必要存在。

19. Process exists to reduce uncertainty, not to create paper trails.
19. 流程存在的目的是减少不确定性，而不是制造文件记录。
The best process makes coordination easier and failures cheaper. The worst process is bureaucratic theater - it exists not to help but to assign blame when things go wrong.
最好的流程能让协调更简单，让失败的成本更低。最糟糕的流程是官僚主义的戏剧——它存在的目的不是为了帮助，而是在事情出错时分配责任。

If you can’t explain how a process reduces risk or increases clarity, it’s probably just overhead.
如果你无法解释一个流程如何降低风险或增加清晰度，那它很可能只是额外的负担。

And if people are spending more time documenting their work than doing it, something has gone deeply wrong.
如果人们花在记录工作上的时间比实际工作的时间还多，那说明出了严重的问题。

20. Eventually, time becomes worth more than money. Act accordingly.
20. 最终，时间变得比金钱更有价值。相应地行动。
Early in your career, you trade time for money - and that’s fine. But at some point, the calculus inverts. You start to realize that time is the non-renewable resource.
在职业生涯早期，你用时间换取金钱——这没什么。但某个时刻，这种计算会逆转。你开始意识到时间是不可再生的资源。

I’ve watched senior engineers burn out chasing the next promo level, optimizing for a few more percentage points of compensation. Some of them got it. Most of them wondered, afterward, if it was worth what they gave up.
我见过一些高级工程师为了追求下一个晋升级别，优化那几个百分点的补偿而过度劳累。其中一些人得到了晋升。大多数人在之后都怀疑他们所放弃的东西是否值得。

The answer isn’t “don’t work hard.” It’s “know what you’re trading, and make the trade deliberately.”
答案不是“不要努力工作”，而是“了解你在交易什么，并有意识地做出交易。”

21. There are no shortcuts, but there is compounding.
21. 没有捷径，但有复利效应。
Expertise comes from deliberate practice - pushing slightly beyond your current skill, reflecting, repeating. For years. There’s no condensed version.
专业能力来自于有意识的练习——稍微超出你当前的水平，反思，重复。持续多年。没有浓缩版。

But here’s the hopeful part: learning compounds when it creates new options, not just new trivia. Write - not for engagement, but for clarity. Build reusable primitives. Collect scar tissue into playbooks.
但这里有一线希望：当学习创造新的选择时，它才会产生复利效应，而不仅仅是新的琐事。写作——不是为了吸引人，而是为了清晰。构建可重用的基础元素。将疤痕组织收集成操作手册。

The engineer who treats their career as compound interest, not lottery tickets, tends to end up much further ahead.
将职业生涯视为复利而非彩票的工程师往往能取得更大的进步。

A final thought  最后一点思考
Twenty-one lessons sounds like a lot, but they really come down to a few core ideas: stay curious, stay humble, and remember that the work is always about people - the users you’re building for and the teammates you’re building with.
二十一条教训听起来很多，但它们其实归结为几个核心思想：保持好奇心，保持谦逊，并记住工作始终是关于人的——你为之服务的用户和你与之合作的队友。

A career in engineering is long enough to make plenty of mistakes and still come out ahead. The engineers I admire most aren’t the ones who got everything right - they’re the ones who learned from what went wrong, shared what they discovered, and kept showing up.
工程职业生涯足够长，可以犯很多错误，仍然能取得成功。我最钦佩的工程师不是那些做对了一切的人——而是那些从错误中学习、分享所发现、并持续出现的人。

If you’re early in your journey, know that it gets richer with time. If you’re deep into it, I hope some of these resonate.
如果你处于职业生涯的早期阶段，要知道它会随着时间的推移而变得更加丰富。如果你已经深入其中，我希望其中的一些内容能引起你的共鸣。


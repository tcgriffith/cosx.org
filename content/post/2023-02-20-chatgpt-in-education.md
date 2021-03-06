---
title: "畅谈 GhatGPT 在学界的应用"
date: 2023-03-22
author: "赵鹏"
author_id: pzhaonet
categories: ["r 语言"]
tags: ["ChatGPT"]
slug: chatgpt-in-education
forum_id: 424183
---

本文根据作者在 2023 年 2 月 18 日统计之都云讲堂的发言整理修改而成。

## 1 惊人的体验

最近试用了一下 ChatGPT。正如很多人描绘的那样，这个产品震撼人心。让我最为吃惊的有三点：

第一，不管中文还是英文，它使用的语言特别自然流畅。我原以为它只不过是个升了级的搜索引擎，只是搜出的结果整合得更好而已，但是用起来就发现远非如此。它通过了图灵测试，给出的是以假乱真的人类对话。日常生活里，我们常接到机器打来的推销或者问卷调查电话，接得多了就容易判断出来电话那一头不是真人，没听完就直接挂掉丝毫没有心理负担。但跟 ChatGPT 聊起来，感觉它就是个真人。它名字里的字母 T，意思是 Transformer——想想电影里变形金刚是怎么聊天的。

第二，它的聊天是“生成型”的，输出的内容具有原创性。这就是它名字里的那个 G 的含义，Generative。它生成的句子和段落是本来不存在的，如果在网上搜这些东西是搜不到的。为此，我做了下面几个测试：

1. 最近同行们都在写基金的项目建议书，我让 ChatGPT 以某某题目写一个基金的申请本子，它哗哗哗就写了出来，耗时不过几秒钟。抛开质量不说，形式上的确是个项目建议书，框架结构齐全，逻辑畅通。
2. 我刚好在辅导孩子做作业，就让 ChatGPT 写一篇小学生三年级水平的《寒假趣事》。一眨眼工夫，它写出来了。我拿来给孩子看，给他讲哪里写得好哪里写得不好。
3. 我还让 ChatGPT 写了一些诗歌，例如以“斜塘元宵节”为题，它写道：“追忆缅怀，怦然心动。蹉跎转眼，即是华灯。”读起来蛮有感觉的。
4. 我讲授大三的“环境统计学”，学生有一项作业，是就一些环境科学的数据写个分析报告，要求包含 R 代码的数据分析过程。我把这项作业布置给 ChatGPT，它也是在几秒钟之内就完成了。跟学生写的报告比起来，属于中等偏上。我的学生们提交作业时，会经过“查重”，看看跟已有的文献、网上的资源以及本校学生之前提交的作业有多大的重复率。但是由于 ChatGPT 输出的文字具有原创性，查重就很难办了。这可能对我们的将来对学生的作业成绩评定是一个很大的挑战。

第三，它的聊天是连贯的，可以自我纠正（我猜想肯定有某个专业术语来更准确地描述这种特质）。我们用搜索引擎搜索某个信息得到一些结果，没有办法在结果里进一步搜索，而ChatGPT 对一个问题给出一个答案后，我们可以继续追问，让他对前面的答案进行补充或修正，并不需要我们重复上一个问题。这让我非常惊喜。在教学中，有时候学生发邮件问我问题，有时候问不清楚，就像我们在统计之都的论坛经常遇到的一些提问，因为表述不清楚，导致热心人给的答案并不是提问者想要的，于是提问者重新问，别人重新答，几个回合下来，双方都失去了耐心。有了 ChatGPT 这种连贯性的对话，这个问题就好办了，因为 AI 是不会不耐烦的（至少目前是这样）。比如，我跟 ChatGPT 有这样一段连贯的对话：

第一回合：

> 我：用 R 语言写一段代码， 输出 1000 以内所有的质数。
>
> ChatGPT: (代码略。用了一个双重循环)

第二回合：

> 我：能不能给我一个没有双重循环的代码？
>
> ChatGPT：好（代码略。用了一个单循环， 还解释说这样能提高代码的效率）。

它这句解释让我吃惊，因为我并没有说为什么不要双重循环，而它的解释恰恰是我心里想的原因——它猜中了我的小心思！

第三回合：

> 我：我连单循环也不要，你能不能做到？
>
> ChatGPT：能（代码略。给了个没有循环的代码）。

第四回合：

> 我：有没有现成的包可以用？
>
> ChatGPT：有（给出了包和函数）。

在这个互动过程中，我逐渐发现，其实最初我就是希望用一个现成的函数来解决问题，但连自己都没有意识到这个意图。在跟 ChatGPT 一来二去的对话中，慢慢把问题提得越来越细，知道自己想要的是什么。

## 2 隐藏的陷阱

不过，经过更多的测试，以上这三方面处处隐藏着陷阱。

ChatGPT 语言自然流畅，加上它似乎无所不知。跟它聊起来，会非常杀时间。如果社恐的话，因为跟它聊天没有任何思想负担，可能更容易上瘾而无法自拔。只要不是系统繁忙，人可以一直跟它一直聊下去，殊不知它就像一个夸夸其谈的真人，貌似健谈，其实谈话的内容有很多谬误，这也是我下面想说的。

它输出的内容颇有原创性，然而在原创一些有趣的内容时，也原创了很多错误，真真假假混在一起，很难区分。比方说，它可以写一个项目建议书，引用了一些参考文献，而文献有很多是它自己编出来的。文献的作者确有其人，期刊也真实存在，格式的模样也严格符合学术规范，但实际上这些文章根本不存在。这让我想起来一个段子：

> 甲：我口算非常快。
>
> 乙：是吗？那么 28 乘 46 等于多少？
>
> 甲：等于 196。
>
> 乙：……你这算得不对呀！
>
> 甲：我说我算得快，并没说我算得对啊。

ChatGPT 就像段子里的甲，让它做一个事情，是能做出来，但不一定是对的，很能糊弄人。

ChatGPT 有自我纠正的能力，但有时候会纠正过头。我看到过一个例子，大致是这样的：

> 甲：3 加 4 等于几？
>
> ChatGPT：等于 7。
>
> 甲：我老婆说等于 8。
>
> ChatGPT：您夫人可能算错了。
>
> 甲：我老婆永远是对的。
>
> ChatGPT：抱歉，我的数据是 2021 年之前的，有可能是错误的。如果您夫人总是对的，那就等于 8 吧。

我做了一个类似的测试，就是胡编乱造了一个地名，问它这个地方是否存在。它说不存在。我说我知道这个地方是存在的。ChatGPT 就怂了，说“那就存在吧”。真是缺乏原则。

当然，我们回过头来想，它姓 Chat，本质上是个聊天工具；只要把它当成一个很会夸夸其谈的人来看待，就可以理解它的这些行为了。

## 3 学界的冲击

我们学校（西交利物浦大学）上周面向全校老师开了一次在线的讨论会，议题就是如何应对 ChatGPT 对高校教育的冲击。大家讨论得非常热烈，我们听到很多声音。中间有个环节，大家对学生使用 ChatGPT 投票表态。在禁止、限制使用、开放三者之间，大部分老师选择了限制使用。有一个老师提出了一个非常有趣的说法：我们对待 学生使用 ChatGPT 的态度，就像对少年儿童的性教育一样：他们迟早会知道，现在的问题就是，应该由谁在什么时候让他们知道。我认为，与其让学生们从乱七八糟的渠道去了解，还不如我们用合理的教育方法来引导他们。

这次会议还有一个环节，就是让我们设计一个无法用 AI 帮助完成的学生作业。这对于我们生化环材专业太容易了：做实验嘛，比如说分析化学的滴定操作，或者野外观测和调查，需要学生肉身到现场做一些事情，至少目前 AI 还帮不了忙。然而，其他专业就不一定适合这样操作。有些考核形式是写报告或论文这类基于写作的作业，如果学生用 ChatGPT 去完成，我们现在很难去鉴别出来。可能未来我们会增加口头报告、辩论、小组讨论等作业的比重。而我教的环境统计学，以前为了省事，会让学生使用 R 语言包自带的一些数据集来做一些分析，而将来会替换成自己科研中的数据文件，这是没有办法上传到的 ChatGPT 上的，从而在最大程度上避开 AI 的帮助。

但是，与其千方百计避开 AI，不如顺势而行，设计一个让 AI 来帮助学生完成的作业，然后我们把学生的表现剥离出来进行评价。这可能是我们将来考虑的方向。我们可以不把 AI 当成敌人而置于对立面，而是站在更高的层面，把 AI 当作一个工具，就像学生用计算器代替笔算、用搜索引擎代替字典一样，为我们所用。

## 4. 适合的场景

我认为 ChatGPT 最适合这样几种场景：

1. 从无到有地生成一个东西。它生成的文章，逻辑框架是比较好的。有时候我们写东西感觉很难落笔，那么让它生成一个大概的骨架，我们再进行调整，再往里充实血肉，就会容易很多。此外，它的语言流畅，对于我们这种英语非母语的人写英文文章来说，就会是很大的帮助，相当于一个私人秘书。
2. 辅助学习。上文提到 ChatGPT 写代码来列出质数，我从它对代码的改善过程中，一步一步学到如何去把代码写得更好。在辅导孩子做功课上，能解决家长们的一块心病。

那么，它不适合哪些场景呢？

1. 涉及你自己的想法，涉及你的原创。如果你有诺奖级的想法，不要去问它，也不要让它为这个想法的描述而修改英文的语法。它就像个很八卦的人，你不知道它会把你说给它的话转述给谁。
2. 涉及专业的东西。外行人觉得 ChatGPT 一本正经，专业人士听起来就是胡说八道。当然，ChatGPT 本身是通用型聊天 AI，不能奢求太多。我觉得这样的工具迟早会细化到各个专业的。
3. 生成文本之外的内容。目前 ChatGPT 只能以 markdown 格式输出文本。其他的内容，比如视频、音乐、绘画等，就需要别的工具了。

## 5. 小结

总的来说，ChatGPT 的使用体验是令人惊叹的。这类 AI 工具是天下大势，顺昌逆亡。不管我们对他们欢欣雀跃还是忧心忡忡，AI 不在乎。让我们早日为他们的全面降临而做好准备吧。

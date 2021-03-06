




## 博弈论
今天要说的**博弈论**是行为主义的第三阶段，在博弈论中，行为主义的智能体是人的本身，关于智能体这一点与强化学习有所不同。博弈论中智能体要优于之前强化学习中的智能体，更接近人类

在行为主义我们主要研究智能体与环境交互，智能体根据环境反馈来更新自己进行学习。

### 什么是博弈

#### 博弈的定义
在生活中，我们或多或少都听过博弈，那么能不能回答一下你对博弈认识呢? 好我们先从字面上理解一下**博弈**，其中的**博**，大家可能会联想到赌博，而**弈**自然会想到对弈。博弈论是**微观经济学习**的一个分支。

#### 游戏

游戏是两个及以上的参与者之间的互动行为(且他们的目标不相同)

- 赌博
- 棋类游戏
- 竞技游戏
- 运动

其实今天我们讨论的博弈是独立于运气、技术的一种**策略**。很多情况下，更多时候靠策略取胜而不是技术，有的时候大家技术不相上下，难分伯仲时候策略就是称为主导比赛的主要原因。例如篮球中的挡拆战术就是属于博弈，或者比赛要结束时双方比分相差不多时，落后方在比赛最后关头，通通过犯规犯规战术来赢得一次进攻机会来取得比赛最后胜利。**策略**是为了获胜所需要的一种智力技巧。技术都差不多，大家都是考虑策略来赢得比赛。

#### 偏好

每一个参与游戏的个体都会有一个偏好关系，我们$\succ_i$ 来表示 i 的在潜在结果的集合中 $O =\{ a,b,c \}$ 的偏好。例如，假设有一个结果集合 $O = \{a,b,c\}$ 且 $\succ_i = a \succ b \succ c$ 意味着参与者 i 在 a 与 b 中，更偏好 a 在 b 与 c 中，更偏好 b



#### 偏好的性质

- 完整性(completeness): 每个参与者 i 在对比结果时，有且只有一种偏好
- 传递性(transitivity): 假设结果集 $O = \{a,b,c\}$ 如果有 $a \succ b$ 以及 $b \succ c$ 那么 $a \succ c$



#### 策略博弈
我们对照强化学习中策略，在强化学习中策略是从**状态到行为映射函数**，而在博弈中策略是一种确定性策略，**策略**本质上涉及与他人的**相互影响**。其他人在同一时间、对同一情形也在进行类似思考。

博弈论就是分析这样的**交互式决策过程**，是关于相互作用情况下的**理性行为**的科学，而强化学习是时序上决策过程。
- 这里交互式决策，不同于强化学习中的**时序决策**

#### 理性行为
- 明白自己的**目的**和**偏好**，同时了解自己行动的限制和约束，以精心策划的方式选择自己的最佳行为，可以理解自私人，参与博弈的人都是理性自私的人，其实我们都不是理性自私人，这样假设是博弈论非常重要前提，如果对方不是理性的自私人，如果对手是大公无私，直接推出比赛让出奖励，那么也就是谈不上什么博弈了，只有这样假设我们才能展开下面研究。

- 理论是在公理上推出的，没有得到验证，得到验证的理论就变成科学
- 博弈论对理性行为为赋予的新的含义，与其他同样具有理性的决策者进行相互作用(发篮球)

#### 在博弈中真的总能获胜吗? 有必胜策略吗?
估计答案你也已经猜到了，没有必胜策略，使用合适的策略可以让我们赢得比赛概率更大而已。例如玩剪刀、石头和布，这就是博弈，没有必胜策略。

#### 博弈策略的分类
##### 静态博弈和动态博弈

如果从时间序列性来看博弈分为静态博弈和动态博弈，时间序列性通俗来将就是参与博弈的各方受时间的影响

- 静态博弈:大家可以同时参与的话题，例如岗位竞争就是静态博弈
- 动态博弈: 棋牌游戏通常行为次序例如棋牌都是动态博弈
##### 非合作博弈和合作博弈

博弈论从博弈双方是合作还是非合作可以分为合作博弈和非合作博弈，行业间价格联盟就是合作博弈而企业间的自由市场竞争就是非合作博弈，也叫做竞争博弈

-  竞争博弈:炒股
-  合作博弈:结盟
##### 完全信息博弈和不完全信息博弈

从信息暴露程度分为完全信息博弈和不完全信息博弈

- 完全信息博弈: 下棋
- 不完全信息博弈: 麻将 

<img src="./images/009.jpg">

### 博弈的要素
一般的博弈问题由三个要素所构成：即局中人(players)又称当事人、参与者、策略等等的集合，策略(strategies)集合以及每一对局中人所做的选择和赢得(payoffs)集合。 其中所谓赢得是指如果一个特定的策略关系被选择，每一局中人所得到的效用。 所有的博弈问题都会遇到这三个要素

#### 局中人(Players)

什么样的人是博弈中局中人，简单理解为参与博弈的人，但是需要满足以下几个条件，

- 在博弈中不存在侥幸心理
- 不可能利用其他局中人的失误来扩展自己的收益
- 以最大化个人利益为目的

#### 策略集合(Strategies)
策略集合是由玩家能够施行的策略所组成的集合

略集合有点像强化学习集合，也就是局中人的行为的集合，每一个策略行为方案。在田忌赛马中，田忌赛马策略集合{上中下、上下中、下中上、下上中、中上下、中下上}
$$\cal{S} = \{s_1,s_2,\cdots \}$$

#### 效用函数(Payoff)

一般，在对比结果的偏好时，通常需要做定量分析的时候，就会采用效用函数。假设有一个效用函数$\mu_i$: $O \rightarrow \mathbb{R}$ 意味着，我们将结果集中的每一个结果，与一个收益 payoff(效用)对应，通常为实数

#### 收益矩阵
玩家在游戏中，每一个策略所对应的收益所组成的矩阵，例如剪刀、石头、布的收益矩阵

$$
player1 = \begin{bmatrix}
0 & -1 & 1\\
1 & 0 & -1 \\
-1 & 1 & 0
\end{bmatrix}
player2 = \begin{bmatrix}
0 & 1 & -1\\
-1 & 0 & 1 \\
1 & -1 & 0
\end{bmatrix}
$$

#### 局势
也就是**局中人**的策略组合是一个**局势**，在一个局势就可以判断出谁赢谁loss

- 对于每一个参与的博弈的局中人都有一个**效应函数**
- 通常用 U 字母表示效用函数
- 效用函数在静态博弈中一般是局势的函数
- 在动态博弈中效用函数可能是局势的函数，也可能还有其他因素，比如时间
- 每个局中人的目的都是最大化自己的效用函数

### 纳什均衡

在博弈中，如果每个参与者在已知其他参与者的策略的情况下，采用最优策略来对应，那么我们就达到了一个纳什均衡，或者找到了一个纳什均衡解，同时也意味没有人能通过改变自己的策略，获得更好的结果(得分，效用或者收益)



#### 占优策略

在选择策略时，有一个策略的效用总是大于其他所有策略效用时，我们就把这类策略称为占优策略(Dominant Strategy)



### 经典示例
通过下面几个具有代表性经典博弈论小示例给大家介绍什么是博弈中三要素，局中人、策略集合和效用函数


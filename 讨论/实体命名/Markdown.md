# 从模组“逃逸：寄生兽”谈 Minecraft 模组的实体名本地化问题

在诸多 Minecraft 模组的本地化中，实体的本地化始终是重点、难点。首先，我们得客观的承认汉英两者语言差异，英语取名，可以十分简单的从其功能或是外形上下手；现举一例。寄生体中的“Reeker”，就是从功能上取名，取了一个“Reek”，再在后面加上了一个“-er”，就算是取名完毕了。而在更多的使用例中，甚至会出现没有“-er”，直接使用一个名词作为一个实体的名字。

那么我们作为中文译者，应该如何处理这样词汇的翻译问题呢？首先我想声明一个结论：实体的本地化基本不可能有唯一的答案，实际上所有的翻译问题都很难有唯一的答案，译者本人对文本本身的介入是不可能避免的，或者说是必需的，否则译文本身不能称其为译文。那么，在这样的角度下，我们应该用更开放更宽容的态度去看待不同译名之间的区别。但，宽容开放的态度并不意味着可以为所欲为，百无禁忌，实际上，单就单独的一个译名而言，合格的译者所提供出来的译名，在词义上是**收敛**的，意即，译者们根据一般的经验做分析，总能得到一些比较相近的结论，这是由于译者们在实际的处理中，对于同类型的词已经是有了一定的处理模式，称为“**构词法**”，这种模式比较符合玩家们的日常语用，玩家们在游玩的时候不会产生过于明显的陌生感，这就是语用习惯的问题。在这里我们可以简要地这样说：从词意分析上，我们可以宽容开放；从语用习惯上，我们得慎重翻译。这是翻译中的一对重要矛盾，不得不谈，因为这一矛盾引发了绝大部分的因翻译引起的争议。

回归我们的题目，在上文的基础上，我们会首先从词意、游戏内表现等方面的分析的角度去首先分析；然后再从语用习惯（译者以及玩家的）上进一步推进我们的分析，最终得出结论。

来自[裂文唬客](https://github.com/LWHK)，本文作者：[清秋](https://github.com/TUsama)、[轩辕](https://github.com/WuzgXY-GitHub)

## 对原始种以及适应种的本地化

首先我们来看一下它们的本地化键值，因为两者实际上是进化的关系，所以我们直接选取出原始种的文本：

```
entity.srparasites.pri_longarms.name=Primitive Longarms
entity.srparasites.pri_manducater.name=Primitive Manducater
entity.srparasites.pri_summoner.name=Primitive Summoner
entity.srparasites.pri_reeker.name=Primitive Reeker
entity.srparasites.pri_yelloweye.name=Primitive Yelloweye
entity.srparasites.pri_bolster.name=Primitive Bolster
entity.srparasites.pri_arachnida.name=Primitive Arachnida
entity.srparasites.pri_devourer.name=Primitive Devourer
```

从文本上分析，这些实体的本地化难度是比较低的，因为它的文本容易理解，没有自造词，一眼可以基本猜测出它们的设计思路，再辅以一定的游戏内表现分析即可。

我们先对“Primitive Longarms”做做分析。从词意上说，“Primitive”是种类的名称，暂不讨论；“Longarms”意思是“长的手臂”，这基本没有什么可供词意分析的余地了，所以我们的此环节就可以暂告一段落，我们开始考虑语用习惯问题，对于这类的实体，我们首要考虑一种本地化的模式，即“主词+种类描述”，在这里，官方译本中的“长臂兽”就是采用了这样的模式。有些译者可能为了突出文本上给玩家的陌生感，会将种类省去，译为“长臂”，我个人对这种本地化的处理手法并不赞同，因为这种处理手法通常应用于生造词，比如种族、城市等。因为生造词本身作为名字，中文的处理方法一般都是直接音译过来。这样的例子数不胜数：

> Álfheim → 亚尔夫海姆
>   有人想要将此词在通行译本中按照“精灵的家”（abode of the Álfar）翻译，这种一般都是没有本地化经验，也没有阅读经验，甚至语言学经验也寥寥的译者。
> 
> Tamriel → 塔玛瑞尔
>   出自 The Elder Scrolls 系列
> 
> Novigrad → 诺维格瑞 
>   出自 The Witcher 系列

例子数不胜数，此处不再枚举。我们再举例一些正面的例子，即添加了种类限定的实体翻译：

> Beholder → 眼魔 
>   出自 DND 系列
> 
> Cooker → 厨师 
>   这个我不想多说什么
> 
> Screamer → 尖啸尸 
>   出自 State of Decay 2

一般来说，遇到这种主词词意清晰，可以一定程度鉴别种类的，采用“主词+种类描述”的处理方法，可以最大程度的降低理解难度。

所以，依照以上的一些讨论，针对于原始种的翻译我们完全可以使用xx兽，xx体之类的形式进行翻译。官方译本中使用xx兽的形式，中规中矩。

有些译者可能会疑惑：为什么 Longarms Yelloweye Arachnida 三者也得使用xx兽呢？它们的结尾不是 -er 啊？这是由于英语本身的语法产生的限制。英文在构造 -er 类单词时，前面的部分往往是动词，意即“是做xx事情的东西”，但是在遇见名词的时候就很难这样构造了。这三者的取名角度都是从外貌上切入的，所产生的都是名词，所以没有 -er 的形式。但是这并不妨碍译者将这三者也处理为xx兽，因为中文没有此种构词的限制，采用如此的构词法无伤大雅，而且译文的统一性更强。但是要牢记一点：译文风格的统一是建立在正确理解原文的基础上的，而不是**为了统一才这样翻译**，如此实为本末倒置。同时，也需注意，不要仅仅因为这三个词和其他的构词法在表面上的不同，就武断地认为，这三者一定得和其他的实体在译文上刻意做出区别，如此乃为因噎废食，轻易忽略掉了这些实体在原文上的内在统一性。

其余的文本不再讨论。

## 对粗杂（Crude）种的本地化

```
    entity.srparasites.host.name=Host
    entity.srparasites.hostii.name=Herd
    entity.srparasites.crux.name=Crux
    entity.srparasites.heed.name=Heed
    entity.srparasites.thrall.name=Thrall
```
以上为粗杂种的几种寄生体的本地化键值。首先我们来逐一分析：

1. “Host”和“Herd”，将两者并列，是因为后者是前者的进化形态，所以并列于此一并讨论。从词意上分析，前者的词意较多，例如“宿主”“大量”等，其中“宿主”的意义可能性最大，因为比较切题；再看后者，它的意思就是群落。单个来看，前者比较难以挑选词意，但是如果搭配上后者，就能明显看出，Host 和 Herd 都是想表达“大量”“许多”的意思，这样两者之间的承接关系就更为明显了。再看看游戏内的实体外观，后者毕竟是前者的进化体，外观看起来就是前者的加长版，上面的骷髅也更多。

   我们再从语用上分析。首先我们不可能直接译成“大量”“许多”，这和中文的语法并不贴合。遇到这样的情况，依然是采用上面的那种模式，即“主词+种类描述”。但也不能译为“大量柱”。你会发现，无论怎么样，“许多”“大量”这种量词都很难塞入我们的模式当中，中文里并没有这样的用法。那么类似于这种情况，一种可用的思路是，将“许多”“大量”扩写为“许多的xx”“大量的xx”，这样就可以变为“长有大量xx的柱”，这样处理过后，稍微缩一下句子，就能够得到一个较为适当的译名。那么，此两者的译文含义就可以处理为“长有大量骷髅的寄生体柱子”“长有更大量骷髅的寄生体柱子”。在1.9.7的译本中，我为了缩写得更为简略，甚至把 Host 直接译为了“骷髅柱”，Herd 译为了“群骷柱”，更为强调两者之间的进化关系，部分牺牲了 Host 的原文含义。

2. “Crux”，按照当初想出这个怪物的作者的说法，这个名字基本上是随便找的，所以我们最好的方法是音译此文本。然而针对于非专有名词的音译，不能按照专有名词的音译法处理，尤其是音译完之后非常像是人名的翻译，可以举一些特意**改字**的音译例子，供大家参考：
    > Flumph → 呋噜 
    >   出自 DND 系列
    > 
    > Rivellon → 绿维珑 
    >   出自 DOS 系列

    我在 MA 的翻译中也运用到了这样的改字音译，将 Eldrin 译为了艾得灵，而不是埃德林。

    但由于笔者能力有限，至今未能找到一个合适的音译译文，只能退而求其次，从其生成的角度取名，重命名为“烬余兽”，虽然从方法上不是最正规，但是格式上较为统一，也照顾了一部分的游戏内表现，也算是较为可读。

3. “Heed”，词意为“留意”“当心”，目前在游戏内不生成，计划的能力仍未实现，单独的一个词意让人想破脑袋也无法理解。因而目前除了从外观上下手别无他法。“Heed”的外观为很多的头颅，我个人将“heed”视为对“head”的一种改写，因而取了“头”的意思，最终定位“多首怪”。
   
4. “thrall”太简单了，译为“寄生奴仆”之类的便能切近原意。


## 对先天种的本地化

```
entity.srparasites.carrier_heavy.name=Heavy Carrier
entity.srparasites.buglin.name=Buglin
entity.srparasites.mangler.name=Mangler
entity.srparasites.carrier_flying.name=Flying Carrier
entity.srparasites.rupter.name=Rupter
```

基本上按照以上的方法都能得出一个比较恰当的翻译，唯一需要提及的是“Rupter”和“Mangler”，后者为前者的进化体。前者的译名为“裂兽”，那后者完全不必再去精挑细酌一些小词，简单地处理为“凶裂兽”等和前者有进化语感的译名即可，当然，若是你真的很想精挑细选出一个比较好的词，也是可以的，但前提是能够充分地体现出两者之间的关系。

## 对模组术语的分析

1. “Hive”，“Colony”两个，前者出现在“Call of the Hive”“Hivestone”等，目前统一为“寄群”，“Colony”则是模组添加的一种种群机制，目前只是译为“种群”，两者的区分需要等到游戏内容完善后才能知晓，目前只有“Colony”的内容是较为完善的，“Hive”对应于模组内的哪块内容目前尚未得知。但为了区分，或可将前者更改为“寄巢”，后者更改为“寄群”，如此更为妥帖。
   
2. “Parasitic”和“Infested”，两者指称的是方块的寄生程度的区别，前者指的是完全寄生转化，而后者只是部分寄生，方块颜色上还未完全转化为寄生种族的黑色。
   
3. “Assimilated”，指的是生物被寄生种群同化，此时转化还不完全。当演化阶段提升后，一名同化种会迅速地转变为适应种，此时才寄生并转化完毕。


## 总结

至此，我们已经讨论了一部分的寄生体的翻译。针对于我们所做出的译文处理，我们可以做出如下总结：

1. 尽量采用“xx兽”“xx虫”“xx+种类限定词”的译法，如果实体的种类限定不太明显，则可以简单的选择“xx体”，可选用的还有“xx魔”“xx怪”等，但是使用这类在常规语义上有一定价值评判的种类限定字时，一定要妥善地考虑清楚词与实体之间的关系，长相特别凶恶、危险程度特别高的，比较适用于“魔”这种字眼，其余的请读者自行考虑。
   
2. 对于没有办法在中文中使用“xx+种类限定词”译法的原文，可以适当扩写，补足缺失的名词，再在此补足的基础上缩写，
   
3. 对于完全生造的词汇，我们需要采用音译的方式翻译原文。需要注意的是，音译时译者在对非专名的原文翻译时，最好是采用不是特别常用的音译字，且此字最好能够从某种角度合适地切入到实体自身的性质中，这样的译文既未违背原文的发音要求，还能最大程度地给读者带来美感。
   
4. 对于在进化层级上有先后关系的实体，在译文处理上最好清晰地表露出这一层关系，当然前提是不对原文的词意做出过大的损害。
   
5. 在翻译的过程中，一定要灵活地将原文词意与游戏内表现结合在一起，找到最适合的词意，切忌只是将原文丢入翻译软件中，单靠臆想选出词意。

做出以上总结后，我们可以对目前 1.9.7 的译本做出一定的总体分析：

1. 我对之前译本中的“兽”字做了清算，对于危险程度较低，出现时期较早的实体，使用的一般是“兽”“柱”之类的中性词，没有刻意在选字上使用特别具有价值倾向的；而在新出的卓越种寄生体中，我开始逐渐混用“体”“兽”“泡”，力图在种类限定上更为多样，因为此时的实体在外形上已经逐渐奇诡，原先的“兽”只能适用于小部分的实体；而在远古种中保留了“魔”的称呼，着重突出远古种的危险性。

2. 除却“Rupter”与“Mangler”，“Host”和“Herd”，卓越种的“Wraith”与“Bogle”也有一定的联系，但是它们的联系并不是进化关系，而是一种更弱的类似关系。在外形上它们较为相似，内部名具有相同的命名结构，攻击方式也类似，原文上都有突出“恐怖”“可怕”之意。所以我将此两者处理为了“幽鬼体”和“怖怪体”，“幽”“怖”和“鬼”“怪”，在一定程度上相互参照。


## 实践考察

有了理论，那自然就是要将理论付诸于实践当中。我们可以展示部分目前一些玩家自制的译本，通过批判这样的译本，加深我们对以上内容的理解。以下有摘录，你也可以点击[此处](https://pan.baidu.com/s/1GtwgdJuoB18f5ablrzolUw?pwd=gwqh)下载到该译本的完整版，提取码为gwqh。

### 译文构词法的考察

```
entity.srparasites.pri_longarms.name=长臂
entity.srparasites.pri_manducater.name=影匿
entity.srparasites.pri_summoner.name=唤虱
entity.srparasites.pri_reeker.name=游猎
entity.srparasites.pri_yelloweye.name=黄眸飞虫
entity.srparasites.pri_bolster.name=活性缸
entity.srparasites.pri_arachnida.name=拟蛛
entity.srparasites.pri_devourer.name=贪噬

entity.srparasites.host.name=宿主
entity.srparasites.hostii.name=虫群
entity.srparasites.crux.name=徘徊者
entity.srparasites.heed.name=颤栗
entity.srparasites.thrall.name="奴隶"

entity.srparasites.overseer.name=监察
entity.srparasites.bomber_light.name=空袭者
entity.srparasites.carrier_heavy.name=携虫体
entity.srparasites.buglin.name=虫灵
entity.srparasites.mangler.name=绞杀虫
entity.srparasites.worker.name=工虫
entity.srparasites.carrier_flying.name=飞行携虫体
entity.srparasites.rupter.name=断裂虫

entity.srparasites.warden.name=看守
entity.srparasites.marauder.name=掠夺者
entity.srparasites.monarch.name=王虫
entity.srparasites.grunt.name=仆役
entity.srparasites.sentry.name=哨兵
entity.srparasites.kyphosis.name=弯脊

entity.srparasites.bomber_heavy.name=重型空袭者
entity.srparasites.carrier_colony.name=噬境妖虫
entity.srparasites.wraith.name=幻灭
entity.srparasites.bogle.name=狞兽
entity.srparasites.haunter.name=祟魔
entity.srparasites.succor.name=寻觅孢体

entity.srparasites.anc_dreadnaut.name=空天主宰
entity.srparasites.anc_overlord.name=远古魔君
```

以上是对此译本中大部分实体文本的摘出。我们不难发现，以上的译文在翻译风格上是**极其不统一**的，有些使用我们文中提到的“xx+种类限定词”译法，有些又只是使用了一个描述行为的词语，甚至有一个使用了双引号括住译文，双引号往往是在翻译人物称号或昵称时使用，放在此处显然不合适。在游戏本地化中，就算不谈论译文构词法的好坏，至少在译文风格上统一，这样能够最大程度地降低玩家的记忆难度，这是符合人类记忆逻辑的。如果在风格上想一出是一出，构词法随意选用，这样的译文整体上只能给玩家一种混乱感。这种问题一般出现在新手译者身上，因为新手译者偏爱使用诡词、奇词，为了这些词语而破坏了译文的语法结构，加剧了阅读者的记忆负担，可以说是本末倒置。

除此之外，在处理实体的进化层级的问题上，译文也暴露了严重的问题。“绞杀虫”“断裂虫”两者的关系不明朗，“宿主”和“虫群”更是“貌离神也离”。如果说前面的风格问题只是影响记忆，那后面的关系处理问题就会影响游玩理解了，属于是硬伤。


### 术语层面的考察

```
entity.srparasites.carrier_colony.name=噬境妖虫

entity.srparasites.sim_bear.name=寄生熊
entity.srparasites.sim_enderman.name=寄生末影人
entity.srparasites.sim_endermanhead.name=行走头颅（末影人）
entity.srparasites.sim_adventurer.name=寄染冒险者
entity.srparasites.sim_adventurerhead.name=行走头颅（冒险者）
entity.srparasites.sim_bigspider.name=寄生巨蛛
entity.srparasites.sim_human.name=寄生人类
entity.srparasites.sim_humanhead.name=行走头颅（人类）
entity.srparasites.sim_villager.name=寄生村民
entity.srparasites.sim_villagerhead.name=行走头颅（村民）
entity.srparasites.sim_cow.name=寄生牛
entity.srparasites.sim_cowhead.name=行走头颅（牛）
entity.srparasites.sim_horse.name=寄生马
entity.srparasites.sim_horsehead.name=行走头颅（马）
entity.srparasites.sim_pig.name=寄生猪
entity.srparasites.sim_pighead.name=行走头颅（猪）
entity.srparasites.sim_sheep.name=寄生羊
entity.srparasites.sim_sheephead.name=行走头颅（羊）
entity.srparasites.sim_wolf.name=寄生狼
entity.srparasites.sim_wolfhead.name=行走头颅（狼）
entity.srparasites.incompleteform_medium.name=未转化完全状态
entity.srparasites.incompleteform_small.name=未转化完全状态
entity.srparasites.sim_dragone.name=寄生末影龙
entity.srparasites.sim_dragonehead.name=行走头颅（末影龙）

tile.srparasites.parasiterubble_stone.name=寄生石头
tile.srparasites.parasiterubbledense_wall.name=寄生压缩石头
tile.srparasites.parasiterubbledense_biome.name=寄生压缩生物群系石头

```

以上涉及到的术语有“Hive”，“Colony”，“Parasitic”以及“Assimilated”，但遗憾的是，译者将“Hive”“Assimilated”和“Parasitic”混同了，“Hivestone”成了“寄生石”，“Assimilated Bear”译成了“寄生熊”，实在是令人扼腕叹息；而“Colony Carrier”居然译为了“噬境妖虫”，令人费解。顺带一提，此处“Reinforced Hivestone”译成了“寄生压缩生物群系石头”，此乃版本更替引起的谬误，译者应该学习[如何使用 CAT 辅助自身翻译](https://github.com/LWHK/Passages/blob/master/Minecraft%20%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%B8%93%E4%B8%9A%E7%BF%BB%E8%AF%91%E5%B7%A5%E5%85%B7%E7%AE%80%E4%BB%8B/Markdown.md)，避免这类问题的出现。

除此之外，该译本中的描述部分还有大量的机翻内容，但此问题不在本篇的讨论范围，若读者对此感兴趣，可阅读[此文](https://github.com/LWHK/Passages/blob/master/Minecraft%20%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%E5%BC%80%E5%8F%91/Markdown.md)。

### The Undergarden

*未完工*
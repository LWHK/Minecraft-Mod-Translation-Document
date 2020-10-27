# 模组翻译：从入门到 Java 开发

- [前言](#前言)
- [找到语言文件](#找到语言文件)
- [搭建工作区域](#搭建工作区域)
  - [文本编辑器](#文本编辑器)
  - [词典与网站](#词典与网站)
  - [进阶小技巧](#进阶小技巧)
- [汉化提交途径](#汉化提交途径)
  - [通过 GitHub](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#%E9%80%9A%E8%BF%87-github)
    - [GitHub 入门](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#github-%E5%85%A5%E9%97%A8)
      - [注册账号](#注册账号)
      - [相关概念与工作流程](#相关概念与工作流程)
        - [Fork](#Fork)
        - [将仓库 clone 到本地（可选，较为重要）](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#%E5%B0%86%E4%BB%93%E5%BA%93-clone-%E5%88%B0%E6%9C%AC%E5%9C%B0%E5%8F%AF%E9%80%89%E8%BE%83%E4%B8%BA%E9%87%8D%E8%A6%81)
        - [Pull request](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#pull-request)
        - [Review](#Review)
        - [与原仓库同步](#与原仓库同步)
    - [向原库提交（不推荐新手）](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#%E5%90%91%E5%8E%9F%E5%BA%93%E6%8F%90%E4%BA%A4%E4%B8%8D%E6%8E%A8%E8%8D%90%E6%96%B0%E6%89%8B)
    - [向 CFPA 提交（仅限 1.12.2）](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#%E5%90%91-cfpa-%E6%8F%90%E4%BA%A4%E4%BB%85%E9%99%90-1122)
      - [CFPA 仓库地址以及项目存放位置](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#cfpa-%E4%BB%93%E5%BA%93%E5%9C%B0%E5%9D%80%E4%BB%A5%E5%8F%8A%E9%A1%B9%E7%9B%AE%E5%AD%98%E6%94%BE%E4%BD%8D%E7%BD%AE)
    - [通过 GitHub 建立翻译团体并进行翻译管理](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#%E9%80%9A%E8%BF%87-github-%E5%BB%BA%E7%AB%8B%E7%BF%BB%E8%AF%91%E5%9B%A2%E4%BD%93%E5%B9%B6%E8%BF%9B%E8%A1%8C%E7%BF%BB%E8%AF%91%E7%AE%A1%E7%90%86)
  - [通过 Weblate](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#%E9%80%9A%E8%BF%87-weblate)
  - [通过 CurseForge 或其它途径](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#%E9%80%9A%E8%BF%87-curseforge-%E6%88%96%E5%85%B6%E5%AE%83%E9%80%94%E5%BE%84)
- [一些注意事项](#一些注意事项)
  - [每天一个机翻小技巧，有手就能学废](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#%E6%AF%8F%E5%A4%A9%E4%B8%80%E4%B8%AA%E6%9C%BA%E7%BF%BB%E5%B0%8F%E6%8A%80%E5%B7%A7%E6%9C%89%E6%89%8B%E5%B0%B1%E8%83%BD%E5%AD%A6%E5%BA%9F)
  - [意外情况](#意外情况)
    - [不加载](#不加载)
      - [完全不加载](#完全不加载)
      - [部分不加载](#部分不加载)
    - [文字乱码](#文字乱码)
- [本文格式指引](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#%E6%9C%AC%E6%96%87%E6%A0%BC%E5%BC%8F%E6%8C%87%E5%BC%95%E4%B8%80%E7%BA%A7%E6%A0%87%E9%A2%98)

## 前言

粗略查了查，似乎目前还没有一个当前版本（指 1.12.2 及以后）的汉化流程教学。其实很多时候不见得没有人翻译，而是很多人自己做了翻译，虽然想共享出来，但找不到门路；即使对上路了，也需要别人手把手的教学。其实这些都可能是可以被避免的——如果有足够详细且描述系统的文章能够写明部分规范化处理的流程（也可以说这一流程正是在书写的过程中被规范化了的），那么想要参与到汉化工作之中来的人就能很快地上手并充分输出自身的生产力了（悲）。

总之，本文的目的就是写出上述的内容——当前版本下的汉化流程以及提交流程，我们会尽量将我们所知道的流程尽可能的写清楚，方便后来者查阅和学习。

在此之前还要再说明一点。如果你的英语水平还很差，即使你的热情相当高涨，我们仍然不建议你参与到汉化工作中来。有些人可能觉得翻译工作查一查词典、找一找语法书，或者背一背单词就完事了，然而这么想其实是完全不正确的；如果你有这种想法，你的水平可能还需要提高。我们可以引用本雅明[《译作者的任务》](https://www.douban.com/note/740749770/)中的一个文段来阐明这一点：

> ……文学作品的基本特性并不是陈述事实或发布信息。然而任何执行传播功能的翻译所传播的只能是信息，也就是说，它传播的只是非本质的东西。
> 这是拙劣译文的特征。但是人们普遍认为文学作品的实质是信息之外的东西。而即使拙劣的译者也承认，文学作品的精髓是某种深不可测的、神秘的、“诗意的”东西；翻译家若要再现这种东西，自己必须也是一个诗人。

模组文本明显不是文学作品，然而它们总有着部分的相似之处。这里也指出了一个问题，而这个问题至今为止在大部分翻译者的译文那里都存在着——如果你的句子仅仅是由纯粹的词语和语法产生的堆砌物，那么你的译文毫无疑问就是拙劣的译文；而那些连最基本的中文语序以及逻辑条理都把握不到的翻译者，翻译出来的东西更是惨不忍睹、不忍直视的，它们甚至都算不上这里所说的“拙劣的译文”。我（轩辕）曾经见到过一份文本，这份文本的作者在进行过大量机翻以及其后的阅读后已经不再能清晰地把握中文文字的脉络了，导致他自己原创出的这份文本都被我误判为了机翻内容。毫无疑问，上述的两种水平较低的译文，都是由于经验的不足而导致的，这一经验指的远不止英语阅读的经验，而是将英语文本转变为有逻辑关系的中文的经验。也就是说，翻译工作同时考校了你双边的实力。

然而哔哩吧啦了一大堆，本篇教程和“**如何汉化**”并无关联。如何翻译一个句子，一个词，这些不在本文的指导范围之内。当今的九年义务教育制度普及效果良好，如果你因为年龄不大而翻译得很烂，你还有很多机会可以接受更好的教育以及自我训练。本篇真正希望解决的是那些类似于“**如何投交汉化文本**”以及“**除了自身的翻译水准，成为一个合格的 Minecraft 模组翻译者还需要学会哪些技能**”，甚至只是“**我对翻译有兴趣，我应该做哪些准备**”的问题。

对于那些只是对翻译有兴趣，想看看翻译需要做哪些准备然而有些怕麻烦的人而言，仅看前面两章（[找到语言文件](#找到语言文件) 和 [搭建工作区域](#搭建工作区域)）即可。当然，最后一章的第一小节（[关于机翻的部分](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#%E6%AF%8F%E5%A4%A9%E4%B8%80%E4%B8%AA%E6%9C%BA%E7%BF%BB%E5%B0%8F%E6%8A%80%E5%B7%A7%E6%9C%89%E6%89%8B%E5%B0%B1%E8%83%BD%E5%AD%A6%E5%BA%9F)）也得看，以尽可能避免出问题。在这之后，你可以根据自己的兴趣决定是否继续阅读。

如果你想要认真参与到翻译工作中，或已经开始了翻译但仍觉得自己的专业性有待提高，那么你可以看看其它的章节。掌握了 GitHub 的相关技巧，你就可以比较专业地管理你自己的翻译长期项目，甚至与他人合作了。

提问之前，请先阅读[《提问的智慧》](https://github.com/ryanhanwu/How-To-Ask-Questions-The-Smart-Way/blob/master/README-zh_CN.md)。如果我们判断你的问题并未遵守此文中的建议，我们将不予回复。

我们默认读者有对 [Minecraft](https://minecraft-zh.gamepedia.com/Minecraft) 及其 [模组](https://minecraft-zh.gamepedia.com/Mods) 的基本认知。如对模组内容有疑问，可以访问 [百科](https://www.mcmod.cn)。（仍有疑问的读者也可查看 [百科的模组简介](https://bbs.mcmod.cn/forum.php?mod=forumdisplay&fid=54&filter=typeid&typeid=57)）

话不宜多，我们开始正题。

来自 [LWHK Organization](https://github.com/LWHK)，本文作者：[清秋](https://github.com/TUsama)，[轩辕](https://github.com/WuzgXY-GitHub)

清秋的文字并不是很严谨，此外也并没有在英文或数字与中文之间适当地加入空格，所以图片与文本的阅读体验之间可能有差异，还请各位读者多多包涵！

## 找到语言文件

右击你的模组文件（扩展名为 .jar 的压缩包），使用压缩软件打开。例如，我（清秋）使用的是 360 压缩（推荐使用 [7-Zip](https://www.7-zip.org/)），那么右击模组文件之后，会出现如下提示：


![剪贴板图片 _1_.jpg](https://i.loli.net/2020/08/13/Hg3AtWLTCj1lzs2.jpg)


单击之后是这个样子的：


![剪贴板图片.jpg](https://i.loli.net/2020/08/13/lQYnw4gOu85SHXC.jpg)


依次进入 assets\ModID\lang（有一些模组的文件结构与通常的不同，但是一般情况下语言文件都会位于一个名为 lang 的目录下，如果本文提到的位置并无语言文件，可以使用文件查找功能自行寻找）就能发现：


![剪贴板图片 _2_.jpg](https://i.loli.net/2020/08/13/Drq6WykR9pYsfJ1.jpg)


1 是英文的语言文件，而 2 是中文的语言文件，如果没有 2，就基本说明这一个模组没有中文的翻译（例外：1.12.2 的情况下有可能 CFPA 有而模组本体没有，为了防止撞车，请先阅读底部的 [一节](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#cfpa-%E4%BB%93%E5%BA%93%E5%9C%B0%E5%9D%80%E4%BB%A5%E5%8F%8A%E9%A1%B9%E7%9B%AE%E5%AD%98%E6%94%BE%E4%BD%8D%E7%BD%AE)），你可以按照其英语文本进行翻译（建议阅读本节 [教程](https://harbinger.covertdragon.team/chapter-13/)；如果这是你的第一份翻译，请先查看其它有汉化的模组的语言文件，对照着中文与英文文件查看具体应该替换的部分，以避免出现失误）。翻译完之后，把文件改名为 2，也就是 zh_cn.lang，然后再将其放进上述的目录。这样，理论上来说你在游戏中就可以读取到翻译了！

顺带一提，在 1.12.2 中，语言文件为 .lang 文件，但在 1.12.2 以上的版本中，则是 .json 文件。

## 搭建工作区域

如果上面说的都还只是一些人尽皆知的小技巧，那么，接下来的内容就只有翻译工们才会知道了。每位汉化者都有自己的舒服的一些工具，有些工具性能较好，有些工具功能更优，而工具的使用全看个人选择，所以，以下只是我们个人的经验之谈。

在这里，必要的部分只有文本编辑器，在必要的部分之后，我会列出可选的软件，这些软件有一些可以提升你的工作效率，有一些则关乎你接下来提交汉化的方式。

### 文本编辑器

我（清秋）使用的文本编辑器有两个：

1. 轻量编辑器：[Notepad++（Np++）](https://notepad-plus-plus.org/downloads/)（不再推荐）

    原本我们想着说，如果不谈敏感话题，那么这款软件其实完全是可以推荐的。但是我们发现作者在的官网上已经到了非常嚣张的地步了，所以我们决定不再推荐。如果想使用轻量编辑器，换一个 [**Notepad3**](https://www.rizonesoft.com/downloads/notepad3/) 可能会好一些。（据传闻 [Sublime](https://www.sublimetext.com/) 也是一款不错的轻量编辑器，但我们都没有尝试过；如想查看 Notepad++ 的替代品及各替代品的差异，也可查看这篇 [文章](https://blog.csdn.net/leelight/article/details/103019863)）

    之所以我们认为你可能需要一款轻量编辑器，是因为有时候其实你根本不需要这么多的功能。你只需要一定的语法高亮来看看排版、查查错误，再用自己的能力看看翻译质量。这时候如果再搬出一些庞然大物，那就未免有点杀鸡用牛刀的意味了。

2. 主力军：[**Visual Studio Code**（VSC 或 VSCode 甚至只是 Code）](https://code.visualstudio.com/)

    这位就是我们汉化工作的主要工作区域。

    安装完成后，界面是这样的：


    ![剪贴板图片 _3_.jpg](https://i.loli.net/2020/08/14/GJAH54rwMs16q7u.jpg)


    在上面我分别标注出了几个需要注意的地方。

    工作区的搭建首先需要你点进 Extension（扩展）管理，在顶部搜索栏中搜索 "Chinese (Simplified) Language Pack for Visual Studio Code"，单击第一个扩展，再单击 Install，稍待一会你就会发现你的界面已经变成了中文。

    你还需要安装以下扩展：

    1. Minecraft Lang Colorizer（zz5840.minecraft-lang-colorizer）（必装）
    2. Minecraft JSON Schemas（levertion.mcjson）（可选；目前用处不大）

    第一个能使得 VSC 支持 .lang 文件的读取，第二个则还能支持一些 Minecraft 独有的类 .json 文件的显示（譬如 .mcmeta 文件）。这是对比图：

    
    ![剪贴板图片 (33).jpg](https://i.loli.net/2020/08/15/ntAk6flIHih2BU8.jpg)

    ![剪贴板图片 (34).jpg](https://i.loli.net/2020/08/15/jwGKPog1ubNRWlz.jpg)

    
    考虑到很难找到一个能同时使 .lang 和 .json 文件的配色合适、文本易阅读的颜色主题，后期我们可能会在这里加入一些较好的现成主题。如果你有能力，你当然也可以自己制作一个。
    
    需要注意的是，如果你安装了这个扩展而 .lang 文件配色等等并没有发生变化，你需要手动将一个 .lang 文件设置为 .lang 文件格式，之后 VSC 就会自动为你设置了。

    基本上，安装了这些之后，你就可以~~畅通无阻地~~进行你的汉化工作了！（如果你的电脑配置比较差，打开 VSC 会花去很长时间，请耐心等待）

### 词典与网站

如果你的词汇量无比丰富，那么你的翻译过程应该是基本顺畅的。但是实际上绝大多数人根本无法一词不差地理解文本含义，所以词典软件是必不可少的。

我（清秋）使用的词典是 [**欧路词典**](https://dict.eudic.net/)。

个人感觉还是不错的，安装了桌面版之后，打开划词翻译，打开 VSC，只需要选中你想查询的词，即可查出释义，非常好用。

[**有道词典**](http://cidian.youdao.com/) 的桌面版也不错，然而和我的电脑适配有困难，所以卸载了，但是有道的划词检索很快，不像欧陆，有时候划词检索不出来，还会卡住，不过卡住的还是较少的。

长句子翻译非常推荐 [**DeepL**](https://www.deepl.com)，它拥有着令人惊叹的翻译准度，以至于我的哲学论文有很大一部分的内容都是它帮助我翻译的。

顺带一些其它的在线词典网站推荐：

[**模组词典**](https://dict.mcmod.cn/)（可以查出 MC 一些既定专有名词的翻译）

[**谷歌翻译**](https://translate.google.cn/)

如果你有苹果移动端设备并且使用方便的话，直接打开设备，在主屏幕下滑打开搜索栏，输入英语词汇即可翻译。苹果支持的词典种类很丰富，甚至部分支持其它几个印欧语系的语言、日语以至汉语本身。似乎需要 iOS 12 及以上。

### 进阶小技巧

1. 替换重复率高的词
    
    汉化中你可能会遇上那种重复率很高，并且已经定番（不可能更改）的词，例如 Red，Green 这种颜色词，并且这种词往往一次性出现 16 个（也就是原版的所有颜色）。这种一次性出现很多的词如果由人手动翻译不仅耗时间，还可能导致准确度的降低（例如 PHC 模组，数十种作物如果上下统一性不足就会闹出笑话来）。

    如果你不会代码，就有必要使用一些小工具来代劳了，我们推荐使用 [Quicker](https://getquicker.net/)，它的用处很大，这只是利用方法之一。如果不了解具体的使用方式可以自行搜索。


    ![剪贴板图片 (23).jpg](https://i.loli.net/2020/08/14/7NrBnyK9QxpcCLS.jpg)


    这是我（清秋）自己写出来的一个替换颜色的[小脚本](https://getquicker.net/sharedaction?code=62f16959-296c-4df6-9ee2-08d85d9ed340)，你可以将其复制至 Quicker。难度不高，你也可以自己尝试编写一下拥有类似功能的脚本。

2. 与同伴一起汉化一个项目

    VSC 有个名为 Live Share（ms-vsliveshare.vsliveshare）的扩展，可以通过分享链接来共享工作区。以链接的形式发送给同伴，让同伴单击并接受，就可以实时共享翻译进程了！

    装了扩展之后，会在 VSC 的下方显示这个内容：


    ![剪贴板图片 (24).jpg](https://i.loli.net/2020/08/14/mjipLV2nzDTHhl8.jpg)


    单击之后就会提示你登录（请 [使用自己常用的 GitHub 账号](#注册账号) 登录，这样在安装有 git 相关的扩展后就可以以自己的账户来 commit 了），按提示一步步走并在最后单击 OK，右下角就会提示，已经将链接置入剪贴板。

    发送给同伴后，同伴点进去，将会是这样的：


    ![剪贴板图片 (25).jpg](https://i.loli.net/2020/08/14/nMzhFQiCbmGxZPp.jpg)


    注意：你的同伴也需要登录！

    然后只需单击“打开 Live Share for VS Code”，就可以完成了！

## 汉化提交途径

模组的汉化提交可以以多种途径进行，但大体上分为以下几种：

1. 通过 GitHub
2. 通过 Weblate
3. 通过 CurseForge 或其它途径

如果你作为一个新手，确实想要参与到翻译工作中，最好直接阅读 [通过 Weblate](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#%E9%80%9A%E8%BF%87-weblate) ，因为 CFPA 搭建的 Weblate 平台本身就是为新手设计的，使用它可以方便、快捷地进行翻译，不要浪费了 943 的一片良苦用心。

如果你只是想单纯地为自己或周围的人进行汉化，那么提交汉化是完全没有必要的。我（轩辕）曾见过一个人只为了自己和朋友能看就把一个模组机翻后交给原作者，我认为这种行为相当不妥，首先机翻本身就没有值得赞赏的点，而你甚至在意识到了它不妥的情况下仍然把机翻文本交给作者，这不是什么好的行为。

当前的这一部分只写给那些想要融入模组翻译圈子的人。如果你翻译了一个看上去从未有人翻译的模组，而且你也不介意让更多的人使用到你的翻译，那么请**务必**将你的翻译通过各种渠道投递至官方仓库或交给 CFPA 的人员。重复造轮子是对资源的浪费，我们相当感谢愿意无私、无偿地将汉化放出来的好心人。

### 通过 GitHub

如果你想通过 GitHub 来进行汉化，那么首先你得了解 GitHub 是什么，以及它的相关操作。

#### GitHub 入门

本节将会告诉你如何注册 GitHub 账号，并带你了解 GitHub 的一些常用术语。本节的内容都是重中之重，很多汉化者都被卡在了这一步，所以在这一节里，我们会尽可能的配上图片，这样讲解的更为清晰明了。先申明，本人（清秋）没有编程经验，对于 GitHub 的操作难免也有疏漏的地方，所以也恳请各位看官斧正一二，感激不尽。

对于某些地区的用户来说，GitHub 的速度奇慢无比。这时候必须通过其它手段解决这一问题，具体方法见 [下一节](#注册账号)。

GitHub 没有国际化支持，不懂英文将寸步难行，因此请英语水平不足的人自行考量是否要请他人协助提交汉化。

<a name="注册账号">**注册账号**</a>（[本节链接](#注册账号)）

这是进入 GitHub 的第一步。首先打开 [GitHub](https://github.com)。

然后你大概会看见如下的内容：


![剪贴板图片 _4_.jpg](https://i.loli.net/2020/08/14/hIRCSKYHpFiw29D.jpg)


如果你始终加载不出来且位于中国大陆，那你可能需要通过专线等方式跨境联网，可以依法向设置国际通信出入口局的电信业务经营者租用，具体请见这份[《通知》](http://www.miit.gov.cn/n1146295/n1652858/n1652930/n3757020/c5471946/content.html)。注意：未经电信主管部门批准，不得自行建立或租用专线（含虚拟专用网络 VPN）等其他信道开展跨境经营活动；如果你因为不听本文的警告建立非法信道而被国家依法惩处，本文作者不负责。信息来源：[环球网](https://m.huanqiu.com/article/9CaKrnK4hO1)。

接着你需要注册一个账号，只需遵循着引导流程，即可注册一个属于你自己的账号了。如果在注册过程中出现了验证等加载不出来的情况，使用上面提到的国际信道进行网页加载可能也是有必要的。

注册完毕后，你的界面将会变成这样的：


![剪贴板图片 (5).jpg](https://i.loli.net/2020/08/14/pHBjKSRUNaE7IOC.jpg)


可能在一些小细节上有出入，但无伤大雅，大体一致即可。

到了这里，你就拥有一个 GitHub 账号了！

<a name="相关概念与工作流程">**相关概念与工作流程**</a>（[本节链接](#相关概念与工作流程)）

在本节中，我们会先介绍汉化提交的流程，然后再在流程之中抓出相应的概念进行详细讲解。

工作流程大体为找到仓库 → Fork → 修改 fork 过来的仓库 → 发送 pull request（拉取请求）到原仓库。

接下来是详细讲解：

1. 在 [CurseForge](https://www.curseforge.com/minecraft/mc-mods) 上找到自己想要汉化的模组，这里随便以一个模组为例：


    ![剪贴板图片 _6_.jpg](https://i.loli.net/2020/08/15/gswCOIV4YepWZMo.jpg)


    这里以 JEI 做个例子，点进去之后，我们可以找到这个图标：


    ![剪贴板图片 (7).jpg](https://i.loli.net/2020/08/14/fSArFdPxZcRE5Hu.jpg)


    点进这个图标，就可以跳转到这个模组对应的源码仓库了。一般情况下这个仓库位于 GitHub，但也有一些开发者会采用 GitLab 或 Gitee 这种其它与 GitHub 相似的代码托管网站。除非你已经大致摸清了 GitHub 的运作方式，否则不要轻易将 GitHub 的流程套用至其它的托管网站上，并且在遇到了 GitLab 等其它平台时请考虑不作汉化或向他人寻求帮助，如果真的很想翻译这一模组，你可以将它的英文文本发送至 CFPA 的 GitHub 仓库，然后在 Weblate 上进行翻译；也可在本地翻译完毕后，将翻译文本和你所使用的英文文本一同发送到 CFPA 的仓库中，这样可以最大限度地让玩家使用到你的翻译文本。

2. Fork

    这是 JEI 的仓库：

    
    ![剪贴板图片 (21).jpg](https://i.loli.net/2020/08/14/l9HDhCnoPpJmx7g.jpg)


    我们单击右上角的 fork，将这份仓库 fork 为自己的。如果你不明白为什么需要这样做，你可以在阅读完成后到 [下一节](#Fork) 查看解释。

3. 修改仓库的内容

    到了这一步，你就可以将你之前的汉化提交到 GitHub 上了。

    一番查找之后：


    ![剪贴板图片 _8_.jpg](https://i.loli.net/2020/08/14/lxRb3eGyh4W9CZj.jpg)


    记住这个位置，你的文件应该上传到 lang 文件夹里，就和在模组里一样！其中的几个文件夹名字是不固定的，取决于模组的名字，相信你一眼就能明白哪些是不固定的了。

    这里换了一个仓库作例子，单击圈内按钮，选择 upload file，就可以上传文件了！


    ![剪贴板图片 _9_.jpg](https://i.loli.net/2020/08/14/rt6PKXvByfM1LVI.jpg)


4. 拉取请求

    你进行修改的这个仓库是你的，然而你的仓库只是原仓库的一个副本，如果你想要把你的修改合并到原仓库，那么你应该怎么做呢？这时候就需要发送 **pull request**（拉取请求，简称 PR）到原仓库了。

    我们先回到原仓库，依次单击：

    
    ![剪贴板图片 (10).jpg](https://i.loli.net/2020/08/14/bCso5nykqIFQ3pU.jpg)

    ![剪贴板图片 (11).jpg](https://i.loli.net/2020/08/14/WEsk6LD8jHNifAt.jpg)

    ![剪贴板图片 (12).jpg](https://i.loli.net/2020/08/14/m8W74nEaV1bHfUP.jpg)

    ![剪贴板图片 (13).jpg](https://i.loli.net/2020/08/14/xVdDraEycZeXMkU.jpg)

    
    然后你会在页面的下方看到你和原仓库的对比，浏览且发现没问题之后，单击 create pull request，然后填上一些你想说的就好了。

    注意：在 pull request 的信息填写里，不要给国外的作者发中文，他们是看不懂的。你的目的是给他们发送汉化文件，**不是使用中文和他们聊天！**（不过可以用英文和他们聊.jpg）

    遵照上述的流程，你就可以顺利将你的汉化提交至作者那边了！但是你还是需要稍微等待，毕竟作者也不可能一直守着电脑；等到作者有空的时候，他会回复你，并决定是否采用你的汉化文件。

<a name="Fork">**_Fork_**</a>（[本节链接](#Fork)）

为什么需要 fork？

你应该已经注意到了，你其实对别人的仓库是没有修改权限的~~（废话）~~。所以 fork 的操作就相当于，你将他的仓库抄了一遍，然后你在这个抄本上进行修改，这是可以的，因为这是你**自己**的抄本。

我们引一段 [资料](https://blog.csdn.net/moduRooKie/article/details/82219255)：

> ……你 fork 一个仓库，指的是**复制**它。特别是当你 fork 属于别人的仓库时，你将制作他们仓库的**完全一样的**副本，之后这个副本便变成**你的**了。

注意这里的用词，“变成**你的**”意味着你对于这个仓库有着完全的控制权，包括删除仓库，所以修改你自己的仓库也自然不在话下了。

如果仍然未能理解这部分内容，请务必自行搜索并弄通这部分的概念与含义，因为此后的诸多行为都要以这部分为基础，如果未理解就去接着进行翻译工作很有可能误操作。建议阅读[《Git 工作流指南》](https://github.com/oldratlee/translations/tree/master/git-workflows-and-tutorials)当中的 [fork](https://github.com/oldratlee/translations/blob/master/git-workflows-and-tutorials/workflow-forking.md) 与 [pull request](https://github.com/oldratlee/translations/blob/master/git-workflows-and-tutorials/pull-request.md)（见下面的 [Pull request](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#pull-request)）两节。

<a name="%E5%B0%86%E4%BB%93%E5%BA%93-clone-%E5%88%B0%E6%9C%AC%E5%9C%B0%E5%8F%AF%E9%80%89%E8%BE%83%E4%B8%BA%E9%87%8D%E8%A6%81">_**将仓库 clone 到本地（可选，较为重要）**_</a>（[本节链接](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#%E5%B0%86%E4%BB%93%E5%BA%93-clone-%E5%88%B0%E6%9C%AC%E5%9C%B0%E5%8F%AF%E9%80%89%E8%BE%83%E4%B8%BA%E9%87%8D%E8%A6%81)）

在你同时参与了多个项目的汉化之后，你会遇到一个严峻的事实：一旦作者们更新勤奋，每天打开游览器、登上 GitHub 时，你就得开始手忙脚乱的跳网页、找位置了。打开自己的仓库、做好跟进、发 pull request，等等，这有时候要你开四五个页面，才能开到你想要的那个仓库位置。一个仓库还好，如果有十多个乃至更多，那就太累人了；此外 GitHub 网页版在部分地区的加载速度并不快。

这个时候，最好的解决方案就是将你负责的仓库拉取到本地，你只需要在你的本地就能够将一切任务处理完毕，无须上 GitHub 网页版，极为方便。

这里有一份利用 [GitHub Desktop](https://desktop.github.com/) 将仓库 clone 到本地的 [教程](https://www.jianshu.com/p/1e45b93bd593)，只要安装了 GitHub 桌面版，执行教程的第二步，就可以将仓库拉取到本地了！接下来的任务就是进一步把你的仓库 clone 到本地，这样就根本无须打开 GitHub 网页版了，完全可以做到本地一站式解决！

但是对于网络环境不好的人而言，这里还有一个极为严重的问题：在将仓库拉取到本地的过程中涉及到 clone 的操作，这一操作的实质就是将你挂载在 GitHub 上的仓库复制到本地上。一般情况下，只有早上八九点的时候才能以很快的速度进行 clone，一旦不在这个时间区域内，clone 的速度就只能听天由命了，而且绝大部分时候都慢得犹如龟爬，速度不高于 10 KiB/s。

这里有一些别人写过的方法，可以用于参考：[修改 host 以及使用码云的教程](https://zhuanlan.zhihu.com/p/144016106)。

在我（清秋）的情况下改 host 时灵时不灵，大部分情况下没什么用；而码云我们尚未尝试过，读者可以自行决定是否使用一下看看效果。

这是一个成功 clone 的仓库在 GitHub 桌面版的样子：


![剪贴板图片 (27).jpg](https://i.loli.net/2020/08/14/aYhFyzlTfZCwMc4.jpg)


更改之后的操作：


![剪贴板图片 (28).jpg](https://i.loli.net/2020/08/14/17qjE2IdklZN6Kb.jpg)

![剪贴板图片 (29).jpg](https://i.loli.net/2020/08/14/ZwgON6jv9pqBRun.jpg)


如果你想要完善你的本地 git 操作，那么这两个扩展必不可少：

1. GitHub Pull Requests and Issues（github.vscode-pull-request-github）
2. GitLens-Git supercharged（eamodio.gitlens）

安装之后，只要你熟悉 GitHub 的操作，你将很快摸索清楚这两个扩展的使用方法。

如果你并不想花时间熟悉 GitHub 桌面版的操作，你可以简单地将需要跟进汉化的仓库添加至浏览器的书签栏，这样也可以在一定程度上提高效率。但是应注意，如果你参与了帕秋莉手册或其它多目录多文本的翻译工作，使用网页端进行翻译是相当不明智的，因为巨量的页面变动将会让你感到手忙脚乱。

<a name="pull-request">**_Pull request_**</a>（[本节链接](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#pull-request)）

什么是 **pull request**？

这里有一个比较清晰的 [介绍](https://www.zhihu.com/question/21682976)。

Pull request 翻译过来就是“拉取请求”。我们在 fork 的仓库里作的修改都只是自己的，和原仓库关系不大。但是如果你想把你的修改合并到原仓库，那么，你需要问一问作者自己能否把自己的修改合并到对方的仓库，而询问这一过程就被成为“拉取请求”。这一过程实质上就是**把你作的修改同步到原仓库**这一点。但这一过程必须过问仓库主人，因为“未经许可修改仓库”是**不被允许的**~~（废话）~~。

网上有极多的相关教程，如果觉得我们描述得不够清晰，那么请自行搜索。上述的[《Git 工作流指南》](https://github.com/oldratlee/translations/tree/master/git-workflows-and-tutorials)当中也有 [pull request](https://github.com/oldratlee/translations/blob/master/git-workflows-and-tutorials/pull-request.md) 一节。

这里还有一个比较清晰的 [教程](https://www.cnblogs.com/zhangjianbin/p/7774073.html)。

在熟练之后，我们很快就能发现在这里涉及的工作流程的实际样貌：Fork → 修改自己的仓库 → 发送 pull request。

有些新手可能会有疑问：我直接试图修改作者仓库里的内容，它也会提示我发起 pull request，那为什么一定要先 fork 再 pull request 呢？

实际上，这样做确实可以发起 pull request，但是这并不意味着你没有 fork 作者的仓库，我们可以看一个例子（保密起见，已隐去作者用户名，但这确实是同一个人）：


![剪贴板图片 (35).jpg](https://i.loli.net/2020/08/15/lsM8gC2kircKzJo.jpg)


这是一个新手对一个原作者仓库连续发起的三个 pull request，可以肯定，这个新手肯定直接修改了原作者的仓库，并且修改了两次，还在自己 fork 来的仓库中修改了一次，最终一共发起了三次 pull request。我们可以看看这三个 pull request 都是从哪里发起的：


![剪贴板图片 (36).jpg](https://i.loli.net/2020/08/15/gchlAGPHXVQJ1Ib.jpg)

![剪贴板图片 (37).jpg](https://i.loli.net/2020/08/15/EALgGz5cJSlZ1RW.jpg)

![剪贴板图片 (38).jpg](https://i.loli.net/2020/08/15/ELXPKZp8DTnmIi6.jpg)


可以看到，这位新手对着原作者仓库的分支，连续用三个不同的分支向其发起了 pull request，而这些分支其实都是来源于他 fork 的仓库的：


![剪贴板图片 (39).jpg](https://i.loli.net/2020/08/15/GmjbJysNzXLUvAE.jpg)


也就是说，你在修改原作者仓库的时候，GitHub 自动为你 fork 了原作者的仓库，并将你的改动应用到你的 fork 仓库的不同分支上（然而，改动的应用规则对新手而言略有些不明确），然后再从这些分支发起 pull request 到原作者的仓库那里。这样做实际上没有能够理解 pull request 的本质：对 pull request 的 merge 是实际上是两个分支之间的合并，而不仅仅是两个仓库之间的合并，即便在同一个仓库，你也可以用一个分支对另一个分支发起 pull request，这是完全可以的。

这种连开的 pull request 有什么不好的地方？其实从操作层面上来说，没有太多的问题，但事实上这种行为说明其实 pull request 发起者根本就没有理解 pull request 的意义，并且也不了解 GitHub 的 pull request 机制，以及这里谈及的 GitHub 工作流程。一个最显而易见的问题是：如果你根本不能理解 pull request 是如何运作的，那么，你应该如何为你的 pull request 追加新的改动呢？正确的操作是：你得在你 pull request 对应的分支上再继续 commit，这些 commit 会自动推送到这个分支开启的 pull request 上，然后你的追加改动就可以成功的被原作者看到了。如果你不了解 pull request 的机制，你可能就会为追加后的内容再开一个 pull request，这样的效率十分低下，不仅有碍观瞻，且会让仓库的作者搞不清楚你的真正用意。

<a name="Review">**_Review_**</a>（[本节链接](#Review)）

这是一个看上去可以被忽视的过程，但实际上，如果你不想被**其它的翻译者~~锤~~石锤，铁锤，钻石锤**然后以泪洗面，你最好完成这一道“工序”。

具体该如何做呢？这里放出 [LWHK](https://github.com/LWHK) 的一个 [pull request](https://github.com/LWHK/Create/pull/1) ，来给大家解释说明。

打开 pull request 页面之后，我们单击此处：


![剪贴板图片 (14).jpg](https://i.loli.net/2020/08/14/mXl5HjDuRLFNnEW.jpg)


进入到如下界面：


![剪贴板图片 (15).jpg](https://i.loli.net/2020/08/14/QzmunFbEdf6pTtw.jpg)


在本页面中，本次 pull request 的所有更改内容都会显示出来。将鼠标移至每一行前面，你将会发现多了一个小加号：


![剪贴板图片 (16).jpg](https://i.loli.net/2020/08/14/nemCb9WsfaMh4P2.jpg)


单击这个加号，你就可以针对于这一行的内容进行评论，评论完之后，单击 start a review 即可.如果你只是单纯的想发表一下对于这一行的一些想法，那么你可以单击 add single comment，如果突然间没意见了，可以单击 cancel。如果你想对多行的内容进行评论，按住一个加号并上下拖拽即可选择多行内容。


![剪贴板图片 (17).jpg](https://i.loli.net/2020/08/14/1NycTqx657zrELv.jpg)


完成了所有文件的查看之后，你可以单击屏幕右上角的这个。如果你觉得有很多地方需要更改，那么就选择 request changes（请求修改），如果你发现需要改的不多或者基本没得要改，你就选择 approve（赞成修改），如果你只是来划水的或者你觉得你的意见并不很重要，你可以选择 comment。


![剪贴板图片 (18).jpg](https://i.loli.net/2020/08/14/zG7aLPug1VXnxlI.jpg)


有时候你需要特定的人帮助你 review 你的 pull request ，这时候你可以在 pull request 里发送 @ 信息，或者在右侧指定他帮助你 pull request（注意：这一操作只有仓库主人才可以进行！如果你没有该仓库的权限，那么你是无法在右侧专门指定他人为你 review 的，此时你只能 @ 他过来；@ 的方式即输入 @ 后在后面跟上你要 @ 的人的 GitHub ID ，并再在后面空一格）：


![剪贴板图片 (19).jpg](https://i.loli.net/2020/08/14/Q6DW2eMJPCmAUGS.jpg)


这是 @ 的例子：


![剪贴板图片 (22).jpg](https://i.loli.net/2020/08/14/1bB2rZh4ivnKfud.jpg)


再次警告：无论你觉得你的实力多强，只要你不是神，你就会犯错误，而且往往是低级的错误，这些时候如果没有人帮助你 review，那么你的错误将会被别人看到，被别的汉化者锤，如果你不想这样，请你一定要找人帮助你 review！！

最后放上一些例子，基本都是我们参与过的：[根源魔法](https://github.com/CFPAOrg/Minecraft-mod-Language-Package/pull/768)丨[Crossroads](https://github.com/CFPAOrg/Minecraft-mod-Language-Package/pull/779)丨[JEI 附魔信息](https://github.com/Phylogeny/JEIEnchantmentInfo/pull/1)丨[匠魂 2](https://github.com/SlimeKnights/TinkersConstruct/pull/4173)

需要指出的是，无论你是属于某个翻译团体的合作者，还是单干的独行侠，抑或只是来看一看尝试一下的新手，对于含有大量非定番内容的汉化，你**都**应该叫人来 review；就算是不考验你能力的定番内容，你也照样有可能翻译出错别字，因此，除非你对自己的汉化有着完全的信心，或者汉化文本总共只有数行，review 都是必要的。前段时间匠魂的汉化发生了大的改动，我们两位也都去 review 了。我们想说的是，如果不考虑对使用范围极广的错误汉化作出修改可能带来的不便，如果你能给出你自己的完善的解释与说明，让我们搞得明白你作的修改都有什么含义，那就可以改，即使你生造出词来，让我们能理解得了，那也都可以改；但是如果你的翻译让人无法信服或是完全看不懂，你将有必要向 review 者作出有关你修改原因的解释。

优雅（或者说保证眼睛不瞎）地 review 有两种办法：

1. 在网页端 review

    GitHub 的网页端是亮色的，简直就是文本查阅的噩梦环境。在 GitHub 上保持亮色 review 不出十分钟，我（清秋）就开始意识模糊了。为了保护自己的眼睛，我必须找到一种适合我这种编程外行的方法，来改变 GitHub 的主题颜色。

    我个人的解决方法是使用扩展 Stylus（[Chrome](https://chrome.google.com/webstore/detail/stylus/clngdbkpkpeebahjckkjfobafhncgmne)丨[Firefox](https://addons.mozilla.org/zh-CN/firefox/addon/styl-us/?src=search)）。教程我就不放了，如有需要请自行搜索。目标的主题是 [Material Dark GitHub](https://raw.githubusercontent.com/CharlieEtienne/material-github/master/material-github.user.css)，单击链接即可进行安装。安装之后你就会发现，你的 GitHub 变成暗色的啦！

    在 GitHub 网页端进行 review，在功能上会比在本地 review 要更加丰富。一个是一些复杂的语法，在网页端只需点一点按钮便可以唤出；另一个是一些扩展，可以更好地帮助你说明 review 的内容。譬如这个 PR Review Priority（[Chrome](https://chrome.google.com/webstore/detail/pr-Review-priority/mcngolehbdnjjdgbcafgkgigjmplbmhb?utm_source=chrome-ntp-icon)丨[Firefox](https://addons.mozilla.org/zh-CN/firefox/addon/pr-review-priority/?src=search)），你可以迅速地为你的每一条 review 标注你对于这一 review 的态度，上文的 [对 Crossroads 汉化的 review](https://github.com/CFPAOrg/Minecraft-mod-Language-Package/pull/779) 就是一个大规模运用的例子。在这一例子里，我大量运用了优先度的描述，这样 pull request 递交者就能够明白哪些 review 是比较重要的，哪些 review 是可以与我讨论而不会出现误会的。遗憾的是，这个扩展一旦安装便不能选择无优先度的设定；此外至少在火狐方面为有多人的、种类不同的 review 添加评论时会出现数据错乱的现象，只能通过编辑功能手动修改。

    在遇到更改了大量文件的 pull request 时，你会需要用到 [Github Turbo PR](https://chrome.google.com/webstore/detail/github-turbo-pr/bajlfgjogojcoiijmmjeppgmppcdbbfb?utm_source=chrome-ntp-icon)（很遗憾，并没有火狐的扩展）安装之后，只要在 file changes 页面单击扩展进行优化，你就会发现页面的流畅度可以得到大幅提升。然而这个扩展有一些问题，可以在安装页面上查询到，这里就不复述了。

    但无论如何，在网页端 Review 总是有着各种各样的不便，所以我更为推荐在本地进行 Review 。

2. 本地 review

    需要使用到之前提到的 VSC 扩展（按：或许其它的编辑器也有，但是我们都没用过）Github Pull Requests and Issues。

    安装了之后，你就可以在本地访问到远程仓库的 pull request 了：

    单击 all 进行 pull request 查看（注意：不仅可以访问到 origin 仓库的 pull request，还能访问到 upstream 仓库的 pull request；可能需要 [注册账号](#注册账号) 一节提到的建立国际信道的方法）


    ![剪贴板图片 _45_.jpg](https://i.loli.net/2020/08/22/9kSoQPAJq8N4Mdw.jpg)

    
    按下图的顺序单击之后，扩展会专门拉出一条分支，这条分支会与你网页端的 pull request 页面实时同步（虽然会因为网络原因而有一些延迟）。以下是图片：

    
    ![剪贴板图片 _46_.jpg](https://i.loli.net/2020/08/22/5GLU8uCpmiAESnc.jpg)


    一些注意事项，如下图：
    

    ![剪贴板图片 _47_.jpg](https://i.loli.net/2020/08/22/7HoLBTj3a2NitvM.jpg)

    ![剪贴板图片 _48_.jpg](https://i.loli.net/2020/08/22/7PvIdqZAxCQekTX.jpg)


    想要结束 review，必须得声明这一次的 review 的类型是 comment，request changes 还是 approve。也可以直接点进 PR 的 Description ，在其中也可以进行评论以及确认 review 的操作。

    当然，手动前往网页端声明 review 类型也是可以的。

    如果网页端有文件的更新，扩展会提示你将这些改动 pull 到本地。

    我们很快就能发现，本地编辑器在语法难度上比网页端高了不止一点，比如我们常用的 suggest 语法，在网页端只需点一点按钮即可唤出，但在本地端极为麻烦，因为目前插件还没有推出这种简易输入的功能。

    这个时候就要发挥出本地的优势了。你可以借助第三方软件进行快速的为你输出特定的语法，我（清秋）个人使用的是 Quicker（在上文中亦有提及），我个人编写出了一个快速添加建议的脚本，只需选中你想要提出建议的行，然后使用动作，带有建议语法的文本就会写入你的剪贴板，你只需在 review 的输入框内粘贴这一文本即可，虽然不似网页端快捷方便，但也算是比较顺手好用了。

    这是 [快速添加 suggest 的脚本](https://getquicker.net/sharedaction?code=6c5136c4-0748-41ca-9ee0-08d85d9ed340)，选中文本后直接执行动作，相应的带语法的文本会被添加到剪贴板中。

    以下是用于替换原版中特定词的脚本，分别为 [替换原木](https://getquicker.net/sharedaction?code=5717e95f-c12e-43db-9ee1-08d85d9ed340) 和 [替换石质方块](https://getquicker.net/sharedaction?code=73bfacbd-69c8-41b8-1a2a-08d83f7686c1)，加上上文提及的[替换颜色](https://getquicker.net/sharedaction?code=62f16959-296c-4df6-9ee2-08d85d9ed340)脚本，共三个。

<a name="与原仓库同步">**_与原仓库同步_**</a>（[本节链接](#与原仓库同步)）

很多时候，作者更新了仓库，然后你发现他新加入了一些物品，理所当然的，语言文件里也多出了这些新物品的条目。你很快就意识到了这一点：你的仓库落后于作者的仓库，如果你想翻译这些新的内容，那么，你必须把新的内容拉取到你的仓库。最简单的方法就是在你的仓库发起一个反向 pull request，不是你 pull request 对方，而是对方 pull request 你。如果你没能了解如何这么做，在**保证**你的修改已经**完全**被上交了的情况下，可以删掉自己的仓库再重新 fork。

如果使用是本地操作，就得使用命令行进行 fetch + merge 了，请参考这篇 [教程](https://www.cnblogs.com/jjliu/p/11775845.html)。

命令行在本地仓库的相关控制中极为有用，建议认真在网上找教程学习。但是，首先你得为你的计算机安装上 [Git](https://git-scm.com/download/win)。

#### 向原库提交（不推荐新手）

原库提交，指的就是向模组的原仓库提交你的汉化。这一行为无异于宣称你开始负责本模组的汉化，所以不推荐新人这样做；只有在逐步积攒经验之后，一个人才有可能有能力承担起一个模组的官中负责者的任务。

官库提交的流程与以上提到的提交流程是一个流程，按着上面的指导操作即可。

注意，原库提交意味着模组作者不会帮助你 review，你必须自行找人，@ 他过来帮助你 review 才行。

#### 向 CFPA 提交（仅限 1.12.2）

自动汉化模组的提交途径是我们最推荐新手使用的，因为自动汉化的维护者会帮你 review（逃）。提交手段与上述的并无二致，唯一要注意的是文件存放的位置。

<a name="cfpa-%E4%BB%93%E5%BA%93%E5%9C%B0%E5%9D%80%E4%BB%A5%E5%8F%8A%E9%A1%B9%E7%9B%AE%E5%AD%98%E6%94%BE%E4%BD%8D%E7%BD%AE">**[CFPA 仓库地址](https://github.com/CFPAOrg/Minecraft-mod-Language-Package) 以及项目存放位置**</a>（[本节链接](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#cfpa-%E4%BB%93%E5%BA%93%E5%9C%B0%E5%9D%80%E4%BB%A5%E5%8F%8A%E9%A1%B9%E7%9B%AE%E5%AD%98%E6%94%BE%E4%BD%8D%E7%BD%AE)）

注意，所有的汉化项目都应该被放置到此路径下：

![剪贴板图片 (20).jpg](https://i.loli.net/2020/08/14/89ACU1aY3XFGDhW.jpg)

点进这里后，你会发现成吨的已经汉化过了的项目（感谢各位的辛勤付出！），你需要将你的文件上传至此处，但你必须适当的存放你的文件。还记得第一节中的模组的压缩包结构吗？assets\ModID\lang，你会发现，这里的每个项目也都是这样存放的，你需要手动为你的文件创建一个新的文件夹，并将文件夹命名为 ModID，然后在其中再次创建一个名为 lang 的文件夹，然后再把你的汉化文件放进去。这一操作本质上就是将模组文件夹的结构复刻到仓库里，只不过这一次，多了你新放进去的汉化文件。

注意，你最好把你所翻译的对应英语文本同样放进去，这样会方便后来者查看，而英语之外的其它语言文本则不用。

以上演示的是旧版本的仓库，在新版本仓库里，主分支改名为 "main"，用于存放所有 1.12.2 的汉化文件，路径也有了些许改变，以下为演示：


![剪贴板图片 _49_.jpg](https://i.loli.net/2020/08/31/8M5Y9PbwnTeAcWq.jpg)

![剪贴板图片 _50_.jpg](https://i.loli.net/2020/08/31/Src2WnxUIHpRL6h.jpg)


注意：一定要在正确的位置放置你的文件，添加 CF 相关的 ID 目录的这一步是为了之后的爬虫能够进行最新文本的爬取而进行的额外设置，如果 ID 错误，那么爬虫将无法正常工作！

其余的分支存放的是其它版本的文件，切记不要传错分支！


![剪贴板图片 _51_.jpg](https://i.loli.net/2020/08/31/MuL5hB6WYjH1IDF.jpg)


#### 通过 GitHub 建立翻译团体并进行翻译管理

GitHub 有一个 Organization 的设定，单击右上角的加号可以发起组织。组织的功能很多，你可以使用组织来建立仓库，也可以以组织的名义 fork 或发起 pull request。组织本身还有一个 project board，在那里建立的 project 可以让所有组织成员编辑。

通过以组织之名建立中转仓库（我们的 [例子](https://github.com/LWHK/LWHK-Simplified-Chinese-Translation/)）管理需要帮助的汉化会变得轻松许多。你可以 fork 中转仓库至自己的账号下并在 fork 后的仓库中作修改，然后再发起面向中转仓库的 pull request。直接向作者的仓库 pull request 会带来一些问题，比如 review 过长时作者阅读不便、无法 review 完成后立刻 commit、需要控制及压缩 commit 数量、无法不通过 @ 来邀请他人 review 等等，而在中转仓库下这些问题都能得到解决。

除此之外，组织页面还可以作为一个向外界展示自己所在的翻译团体的平台使用。

### 通过 Weblate

自动汉化更新模组的团队（CFPAOrg）以 [Weblate](https://weblate.org/is/) 为基础搭建了一个 [翻译平台](https://weblate.sayori.work/changes/)。上手难度极低，基本没有任何门槛，你只需要在对应的网站登录（账号请找管理员注册），选择自己想要翻译的模组，然后就可以开始轻松愉悦的翻译了！模组更新的新条目也会及时的被爬虫爬到库里，非常方便！

但是首先：

![8](https://i.loli.net/2020/08/15/grfTWFHEuaQkKoj.png)

其次，请尝试是否可以登上团队的 [官方网站](https://cfpa.team/)。

该网站为 CFPA 的介绍页，你可以在这里获得 CFPA 的详细信息。如果上不去，可以尝试前往大陆以外的地区或按照 [注册账号](#注册账号) 一节的内容合法使用国际信道。

实在不行，可以访问 QQ 群 630943368，在群内下载文件《Weblate 使用说明》进行阅读，由于上手难度真的太低了，所以这里不再赘述。

### 通过 CurseForge 或其它途径

顾名思义，在作者不开源的情况下，你必须向作者私信汉化文本（注意：最好以文件形式发送！）。如果你的位置在中国大陆以外，你可以使用 Twitter 或 Discord 等内容与作者取得联系；如果你在大陆内而没能找到其它路径向作者发送文件，你将只能使用 CurseForge 自身的私信（又称 PM 或 DM）功能来发送文件。

如果需要以本节提到的内容进行提交，并且你也有一个所属的翻译团体（CFPA 例外），你可以先将汉化文本以 pull request 的形式交至自己团体的库中让大家一起看一眼，顺便弄个 review 再将文件发给作者。这点将会在 [通过 GitHub 建立翻译团体并进行翻译管理](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#%E9%80%9A%E8%BF%87-github-%E5%BB%BA%E7%AB%8B%E7%BF%BB%E8%AF%91%E5%9B%A2%E4%BD%93%E5%B9%B6%E8%BF%9B%E8%A1%8C%E7%BF%BB%E8%AF%91%E7%AE%A1%E7%90%86) 一节详细描述。

## 一些注意事项

考虑到可能看这篇的大部分都是新手翻译者~~（废话，大佬为啥来看这个）~~，所以除了一些硬件软件上的需求，还得提前说好一些 MC 翻译圈内的规矩，避免冲塔/自爆卡车，然后还怪我在文章内没说清楚。

### 每天一个机翻小技巧，有手就能学废

![机翻对联.png](https://i.loli.net/2020/09/18/mjyGc2KEdYNMDBT.png)

![机翻1.png](https://i.loli.net/2020/09/18/rmPsH53tKNicloa.png)

![机翻2.png](https://i.loli.net/2020/09/18/78PG2qhmRQelHWu.png)

**不允许机翻！！！**

> 机翻是一种极为严重的错误行为，任何在模组翻译圈中的机翻行为都必须完全抵制。在这里我要谨慎的区分开我前面谈到的，利用 Quicker 帮助替换颜色文本和机翻具有**本质性区别**。我们抵制机翻不是为了证明某种由人翻译所产生的抽象本质的威严性，而是为了抵制由机翻带来的不通顺的，错误的，乃至于离谱的翻译。这种抵制建立在纯粹的**实用层面**上，而不是在抽象的行为区分上。这里可以引出一个非常明显的悖谬：面对着一个翻译的比人更像人的机器，我们是应该抵制呢？还是支持呢？如果一个人不使用这样的机器生产翻译，而是自己翻译（质量上肯定差于机器翻译），那么，站在用户的角度，我们是应该支持，还是抵制呢？
> 我个人不愿意从纯粹的行为角度区分机翻和人翻，这样子似乎走入了某种**本质性幻觉**之中，我们试图在人翻和机翻之间找到某种本质性裂缝，这一裂缝展开了价值上的区分。然而，这样的裂缝真的存在吗？我认为这是需要辩驳的。
> 抛开纯粹的思辨，如果我们站在实用的立场上，我们就可以发现，在颜色替换这样的例子上，其与机翻有**实用层面的本质区别**。在这种情境下，人翻和机翻在**纯粹语词**的层面没有差别，这意味着在**纯粹实用**的层面也没有区别，你根本无从分辨哪个是机翻哪个是人翻，你只能凭借**非实用层面**的因素进行区分。但是这样的区分在我看来，构不成价值上的判断，所以无须批判颜色替换的问题，需要批判的是由机翻带来的坏翻译。

以上文本出自清秋，如果你觉得这段话太长了，你可以只看下面这一句话：

> 我们批判的并不是机翻本身，而是明知机翻会带来差翻译仍然使用机翻这种行为。

如果你的翻译当中包含了机翻的内容，请读读土球的一篇 [文章](https://www.mcbbs.net/thread-899249-1-1.html)，或许会对你有一些帮助；蝙蝠的一篇 [文章](https://www.mcbbs.net/thread-899199-1-1.html) 也很好。无论如何，机翻都应是被抵制的，除非你时间不足或者能力不够，尽量不要使用机翻。如果实在需要机器的辅助，请使用 [DeepL](https://www.deepl.com) 作为自己的首选工具。

### 意外情况

有时你会发现，你翻译出来的文本出现了奇怪的问题：明明把翻译文件放进了模组文件内，但游戏中不加载；加载了，居然是乱码；也可能只有个别的一些东西没有加载。这些情况我们会在本节中试着梳理一下，避免被坑。

#### 不加载

不加载又分为两种情况：完全不加载和部分不加载。

<a name="完全不加载">**完全不加载**</a>（[本节链接](#完全不加载)）

1. 检查文件名是否正确。
   
   一般而言，在 1.12.2 中，中文文件可能会有两种名字 ，一种为 zh_cn.lang，一种为 zh_CN.lang。看似只有尾巴的大小写差异，但实际上，如果英语语言文件的尾巴是大写的，然后你放了一个小写尾巴的中文文件进去，它是**不会加载的**。中文文件的尾巴的大小写必须跟随英文文件尾巴的大小写。

    这是一个错误的例子：


    ![剪贴板图片 (30).jpg](https://i.loli.net/2020/08/15/JZAIQs3g5a7cqXu.jpg)


    这是一个正确的例子：


    ![剪贴板图片 (31).jpg](https://i.loli.net/2020/08/15/BHuxSFjIeUhQp9P.jpg)


    1.12.2 以上则不是 .lang 文件，而是 .json 文件。似乎 .json 文件并没有尾巴大小写的说法，全是小写。

2. 检查文件位置，这个无需多言。

3. 如果你的翻译是给 1.12.2 以上版本提供的，你将需要查看语法。

    GitHub 会在 JSON 文件中以红色底色标示出语法错误。语法的错误包含缺少引号、逗号或冒号，多余的逗号以及注释（虽然直至目前注释问题仍然没有好的解决方案，但是添加符合格式的注释并不会影响 JSON 的正常加载）。~~如须注释，请添加下面这段文本至你的 JSON 文件中。~~**这一部分还需要考证**

    > ~~"_comment": "注释文本",~~

<a name="部分不加载">**部分不加载**</a>（[本节链接](#部分不加载)）

部分不加载，则有可能是因为 translation key 发生了错误，所谓的 key，就是语言文件中每一行的左边部分，也即 1.12.2 的 .lang 文件中，每一行条目的 = 的左侧或 1.12.2 以上 .json 的 : 左侧的部分，你需要单独检查一下那些尽管填了翻译，但是游戏中没有加载的词条的 key。

这是一个修复了 key 错误的 [commit](
https://github.com/LWHK/LWHK-Simplified-Chinese-Translation/commit/0c8a8914f5f0124fa31c521997b983d8c556c877#diff-306fabd320470aaa7a1f902a579b1a4a)。

也有一些情况，那就是根本没有 key，而作者把文本写进了代码中，我们称这种文本为硬编码文本。这个情况你就需要较高的技术力了。如果你有能力且有时间，并且愿意协助作者进行修改，那么你可以直接进行修改之后发送 PR 到作者的仓库；如果没能力或者没时间进行协助，在 issue 界面和作者反馈问题就好了，不必勉强自己。

这是一个相关的 [issue 反馈](https://github.com/Mysticmods/MysticalWorld/issues/126)（@RisingInIris2017 的例子；mcbbs名称：NoName德里奇）。

这个是比较特殊的情况，一般而言，你只需要说清楚哪里没有 key，说希望作者改进就好了。

如果你确实不精通英语，甚至书面表达都颇为吃力，那么你可以使用这一套 [issue 模板](https://github.com/0999312/Sakura_mod/issues/new)，填写入相应的信息之后，将中文删掉即可（由 德里奇 友情提供）。

这是一个手动改硬编码的 [例子](https://github.com/TUsama/Roots/commit/a12922af9aa8b1a17e756444749e4c11bfd6022b)（前提是你能看得懂作者的写法）。

#### 文字乱码

文本都会涉及到一个问题，那就是编码问题。如果你的文本是 UTF-8 的编码，然而你的游戏使用了 GBK 的编码方式，那么自然只能出现乱码。如想了解详细内容，可以去网上搜一搜“解码错误”。

在 VSC 中，下方导航条的右侧会显示出 VSC 当前打开该文件所使用的编码类型：


![剪贴板图片 (32).jpg](https://i.loli.net/2020/08/15/lkprt6uXONJfVmh.jpg)


注意，无论是语言文件还是手册，编码格式一定得是 UTF-8，不能是其它的编码（这里体现出了记事本的弱点：不仅默认格式不是 UTF-8，就算调整为了 UTF-8 也可能是 with BOM 版本的）。有些模组自带手册，但是忘记定义了调用 Java 解码的字符集，此时 Java 就会调用你的系统默认的字符集进行解码。如果使用 UTF-8 进入游戏，则会通篇全为乱码。但是这**不是**你的问题。你所要做的就是在他的仓库的 issue 那里放上这个 [pull request](https://github.com/Electroblob77/Wizardry/pull/479)，并说明乱码问题可能与这个 pull request 相关，作者自然就会明白了。

# 本文格式指引（一级标题）

## 本文格式指引（二级标题）

### 本文格式指引（三级标题）

#### 本文格式指引（四级标题）

<a name="本文格式指引（五级标题）">**本文格式指引（五级标题）**</a>（[本节链接](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#%E6%9C%AC%E6%96%87%E6%A0%BC%E5%BC%8F%E6%8C%87%E5%BC%95%EF%BC%88%E4%BA%94%E7%BA%A7%E6%A0%87%E9%A2%98%EF%BC%89)）

<a name="本文格式指引（六级标题）">**_本文格式指引（六级标题）_**</a>（[本节链接](https://github.com/LWHK/Passage/blob/master/%E6%96%87%E7%AB%A0/%E6%A8%A1%E7%BB%84%E7%BF%BB%E8%AF%91%EF%BC%9A%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0%20Java%20%E5%BC%80%E5%8F%91/Markdown.md#%E6%9C%AC%E6%96%87%E6%A0%BC%E5%BC%8F%E6%8C%87%E5%BC%95%EF%BC%88%E5%85%AD%E7%BA%A7%E6%A0%87%E9%A2%98%EF%BC%89)）

# Minecraft 模组翻译：Git 进阶操作

## 前言

本篇是基础教程《Minecraft 模组翻译：从入门到开发》的进阶教程之一。

本篇教程着墨点在与 Git 相关的事项。在基础教程中，我们已经说明了如何在 Github 中注册帐号、如何向仓库投递翻译这两个问题。剩余的本地部署 Git、Github 桌面版（GH Desktop），Github 组织（Organization）等问题会在本篇教程中得到解决。

来自 [裂文唬客](https://github.com/LWHK)，本文作者：[清秋](https://github.com/TUsama)，[轩辕](https://github.com/WuzgXY-GitHub)

## 在本地部署 Git

### Git 是什么

首先引用一段文本：

> Git - The stupid content tracker，傻瓜内容跟踪器。Linus Torvalds 是这样给我们介绍 Git 的。
> 
> Git 是用于 Linux 内核开发的版本控制工具。与常用的版本控制工具 CVS、Subversion 等不同，它采用了分布式版本库的方式，无需服务器端软件支持（wingeddevil 注：这得分是用什么样的服务端，使用 http 协议或者 git 协议等不太一样。并且在 push 和 pull 的时候和服务器端还是有交互的），使源代码的发布和交流极其方便。Git 的速度很快，这对于诸如 Linux Kernel 这样的大项目来说自然很重要。Git 最为出色的是它的合并跟踪（merge tracing）能力。

这里需要详细解释“它采用了分布式版本库的方式”一句：

1. “它采用了分布式...”
   
    什么是“分布式”？我们引用另一段文本：

   > 分布式计算是计算机科学中一个研究方向，它研究如何把一个需要非常巨大的计算能力才能解决的问题分成许多小的部分，然后把这些部分分配给多个计算机进行处理，最后把这些计算结果综合起来得到最终的结果。分布式网络存储技术是将数据分散地存储于多台独立的机器设备上。分布式网络存储系统采用可扩展的系统结构，利用多台存储服务器分担存储负荷，利用位置服务器定位存储信息，不但解决了传统集中式存储系统中单存储服务器的瓶颈问题，还提高了系统的可靠性、可用性和扩展性。

    快速阅读这段文本，我们不难理解它想要表达的意思：所谓“分布式”，目的就是将大的项目拆分成一个个小块，并将这些小块**分布**到多个工作地点进行完成（在计算机领域，工作地点那就是计算机）。最后再把这些小块拼起来。这样的好处在于，同一时刻多人协作，可以有效减少整体的工作用时，并且在工作的自由度上也可以大大提升。

    回到 Git，“分布式版本库”意味着各个仓库被**分发**到了不同的计算机上，而在某一时刻，这些在不同计算机上的版本库也会重新**汇集**起来，这就相当于将分布于各个计算机中的不同工作进度做一个汇总。但更多情况下，并不需要一次行为汇总所有终端的内容。人们的工作流程总是**动态**的，这意味着每个人的工作都会或多或少受到别人的影响，因此最好的操作流程就是将自己已经完善得差不多的部分尽快提交上去，以便其他人根据你的进度，重新分配自身的工作。当然，我不是在说“做多少发多少”，将一条孤零零的代码发到汇总处，别人不见得会理解你的工作思路是什么，所以在自己所进行的一个 feature 渐露眉目，初步成型的时候进行汇总，才是一种更优的选择。当然，一切都要根据实际情况进行判断。

    如果你不能理解我在这里说明的内容，那么我们可以用实际的例子来模拟：你和小明两人，在老师的陪伴下去野营。到达目的地后，老师给你们两个**分配**了不同的任务。你被分配了任务 A 和任务 B，小明被分配了任务 C 和任务 D。在实际完成任务的过程中，你发现你可以在解决任务 A 的时候同时解决任务 C，相当于你将原本是小明的工作给完成了，这个时候你需要将你的任务进展**汇总**到老师那，让老师再进一步为你们重新分配任务。似乎很简单，对吗？你只需要打电话给老师即可，甚至你可以直接打电话给小明，让他直接将重心放到任务 D 上。然而，如果有足足一百人去野营，总任务数有上千个，一些任务纠缠在一起，另一些之间则毫无联系，这个时候直接“打电话”给“小明”，就不是一个好的选择了。你最好将你完成的工作及时汇总到某个中心仓库，让所有人都知道你的工作进度，这样对大家都有好处。

2. “...版本库的方式”

    什么是“版本库”？

    > 版本库又名仓库，英文名 repository，你可以简单理解成一个目录，这个目录里面的所有文件都可以被 Git 管理起来，每个文件的修改、删除，Git都能跟踪，以便任何时刻都可以追踪历史，或者在将来某个时刻可以“还原”。

    可以这样想象：Git 相当于你的仓库管理员，它清楚的知道仓库中所有物品的位置，每次移动，放入，拿走仓库内的物品，它都会记录下来，供之后查阅。

    但这里是网络空间。在现实中的仓库，记录在目录中的活动仅仅是一种辅助记忆的作用，方便你哪天被问起，你能够在上面找到某只替罪羊替你顶罪；Git 不仅能够记录你的活动，还能够帮助你回滚整个仓库的状态。譬如，你修改了仓库中的某个文件，比如你的代码作业之类的。但过了两天之后，你重新看了看你两天前的改动，觉得完全就是一坨*。你想将其重新改回来，但你发现你已经不记得原来的代码是怎么样的了。这个时候，Git 就可以帮助你把你的作业回滚到两天前的版本，只需输入一串指令，等个一两秒，你的作业就变回了原来的样子，轻松又愉快。

如果是单纯的使用 Git，那么知道这些内容，就已经能够帮助你搭建起一个对 Git 的模糊印象了。

## 在本地部署 GitHub 桌面版 & 使用教程

## Git 的综合运用（实例分析）
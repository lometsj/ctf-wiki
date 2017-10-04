# Sphinx 版本注意事项

Sphinx 对 Markdown 的支持并不理想，推荐大家直接写 RST，同样是标记语言，如果不习惯请先写好 Markdown 然后利用 Pandoc 转换。

```shell
pandoc --from markdown --to rst -s xxx.md -o xxx.rst
```

转换后的文档仍然需要微调，否则编译时会出现各种各样的奇怪问题。

## 编辑器推荐

- Sublime + sumlime-rst-completion 插件
- VSCode + reStructuredText 插件

## 公式支持

文档编译时加载了 MathJax 插件，当你用 Pandoc 转换后会在文件头生成 `role` 之类的声明，该声明是用于 Latex 的，需要去掉。

行内公式

```reStructuredText
:math: `a = b + 1`
```

行间公式

```reStructuredText
.. math::
   
   a = b + 1
```

## 本地编译

文档中已经包含了 Makefile，Linux 下未测试。

```shell
pip install -r requirements.txt
make html
```

编译后的文件会生成在 `_build/html` 文件夹下。

## 其他

- 各级标题的下标线需要多于标题长度

# 前言

欢迎来到 **CTF Wiki**。

**CTF**（Capture The Flag，夺旗赛）起源于 1996 年 DEFCON 全球黑客大会，是网络安全技术人员之间的竞技比赛。

**CTF Wiki** 是一个自由的站点，主要包含了 CTF 中的**基础知识、常见题型、解题思路以及常用工具等**，希望可以帮助你更快地了解 CTF 竞赛以及网络安全相关知识。

## 我能收获什么？

* 一个不一样的思考方式以及一颗乐于解决问题的心
* 锻炼你的快速学习能力，不断学习新事物
* 一些有趣的安全技术与相应的挑战
* 一段充实奋斗的时光

在阅读 Wiki 之前，我们希望能给予你几点建议：

* 至少掌握一门编程语言
* 阅读短文 [提问的智慧](http://www.jianshu.com/p/60dd8e9cd12f)
* 善用 Google 搜索能帮助你更好地提升自己
* 动手实践比什么都要管用
* 保持对技术的好奇与渴望并坚持下去

> 世界很大，互联网让世界变小，真的黑客们应该去思考并创造，无论当下是在破坏还是在创造，记住，未来，那条主线是创造的就对了。 ——by 余弦

安全圈很小，安全的海洋很深。安全之路的探险，不如就从 **CTF Wiki** 开始！

## 想要帮助 Wiki 更加完善？

我们非常欢迎你为 Wiki 编写内容，将自己的所学所得与大家分享。

>我们希望你能够按照下面的方式为 Wiki 贡献内容。同时，我们并不希望你利用本 Repo 的内容重新建立一个公开的 Wiki 站点，这样并不利于 Wiki 的发展。

### 协作方式

#### 基本交流

本项目主要使用 Issue 与 Bearychat 进行交流沟通。Berrychat 的团队名为 [CTF-Wiki](https://ctf-wiki.bearychat.com)，欢迎申请加入（申请时请注明申请理由）。

#### 文档协作

本文档现有 master 与 sphinx 两个分支，sphinx 分支是为了试验文档在 Sphinx 工具下的编译效果。通过 Fork 和 PR 的方式更新文档。基本流程如下
1. Fork 主仓库到自己的仓库中。
2. 当你想要贡献某部分内容时，请你务必仔细查看 Issue 与 Project 中对应的看板，确定是否有人已经开始了这项工作，最好加入 Berrychat 中的 [CTF-Wiki](https://ctf-wiki.bearychat.com) 团队，方便沟通与交流。
3. 编辑结束之后，**请你确保在本地可以正常生成文档**，然后再将分支 PR 到主仓库的 master 分支上。其中，PR 需要包含以下基本信息
   * 标题：本次 PR 的目的（做了什么工作，修复了什么问题）
   * 内容：对修复问题的叙述（如果必要的话）
4. PR 评论区进行评论。**尽量在评论之前仔细思考，评论内容要条理清晰，最好给出修正方式，或指出需要集体讨论。** 
5. 提出该 PR 的人根据评论修正内容，然后将修改后的内容 Merge 到 master 分支中。

目前，在人员较少的前提下，基本上可以忽略 4-5 步。第 2 步也可以暂时忽略。

**注：本文档使用 [docsify](https://github.com/QingWei-Li/docsify) 部署，请自行学习一下。**

### 文档内容

对于所要编写的部分，应该尽量确保文档的合理性与格式。

所谓合理性，主要包含

- 有逻辑
- 由浅入深

所谓格式，即在上面合理性的要求下，对于某种类型的题目应该尽可能包含以下几个部分

- 原理
- 例子
- 题目

其对应的存储的一般应该有如下目录

- example，存储在文中介绍时所使用的题目
- figure， 存储介绍时所使用的图片
- 其它必要内容

其中，题目（指的是除了例子之外的同类型的题目）中只需要说明对应的题目名字，相应的题目应该存储在 ctf-challenge 仓库中的对应目录中。


最后，我们的 Github 仓库地址是 [https://github.com/ctf-wiki/ctf-wiki](https://github.com/ctf-wiki/ctf-wiki)， 欢迎 Fork 和 Pull Request 。当然，如果你有任何的问题，欢迎在 [Bearychat](https://ctf-wiki.bearychat.com) 中交流。

我们期待你的加入。

# DevPill.me - 公益区块链开发指南

![blockchain development guide NFT](./images/blockchain_development_guide.jpg)

## 支持这个公益项目

我正在努力收集资源为《区块链开发指南》这个公益项目的开发提供资金，因此我让我的朋友Ana Rueda（@ruedart）创作了这幅超棒的作品：

[Mirror NFT]（https://dcbuilder.mirror.xyz/PLNPOmKkYaP14kJa5A5pJgyIlg4dWHpjDiHS7BGC7J4）

这些资金将用于本指南的持续开发（90%）和感谢Ana的艺术创作（10%）。我愿意随时讨论如何组织围绕指南的合作，将把这笔资金转到一个社区所有的多签钱包。我们的目标是利用来自于Mirror和Gitcoin第13轮的捐赠以及其他地方收集的资金，通过提交赏金（bounty submissions）的方式来激励开发者。如果这个方法没有提高该项目的曝光度，那么我将把资金用于资助Gitcoin比赛以使得其他公益项目得到资助， 以下是对《区块链开发指南》的支持链接：

- [Mirror NFTs](https://dcbuilder.mirror.xyz/PLNPOmKkYaP14kJa5A5pJgyIlg4dWHpjDiHS7BGC7J4)
- [Gitcoin grants](https://gitcoin.co/grants/4975/devpillme-a-public-good-blockchain-development-gu) (Gitcoin 第13轮捐赠3月9日开始3月24日结束，每3个月举办一次)

## 贡献者

如果你想要为这个项目提供贡献， 请加入我为大家创建的[Telegram群](https://t.me/devpillme) 以便我们可以更好的协作和分配任务， 之后我们会迁移到Discord和论坛。

## 介绍

现在有无数制作精良的资源， 从各个专业角度介绍如何学习区块链开发的资源，然而， 要根据自己的兴趣获得指导和个性化的建议依然很困难。 我写这篇指南是为了把我这些年找到的资源聚集起来， 再加上怎么使用他们以便从实用角度最大限度的理解和学习它们， 从而尽快在这个领域中建造出很酷的东西。

本指南将专注于以太生态系统， 因为多数开发人员和应用都基于这个。 如果您对其他生态感兴趣， 这个生态非EVM兼容并且也不是以太的L2， 那么请查看他们各自的文档或者其他开发者社区。 其他非EVM兼容的著名链包括Solana(Rust/Anchor)， Pokadot波卡（Rust/Substrate）, Cosmos, Terra等。 这些链中的多数支持或者即将通过各种措施支持EVM栈（译者注：在自己链上部署以太坊虚拟机）， 比如Solana的Neon EVM, Polkadot/Kusama的Moonbeam/Moonriver, Cosmos的EVMOS等。

我真心希望这个指南能成为一个社区来源的公益项目，每个人都能从中获益。我将尽我所能向更多区块链开发者社区介绍这个产品，以获得建设性的反馈、校对帮助，以及对如何使其成为现有的最佳指南的见解。

### 什么是区块链开发

我觉得区块链开发有两大类， 一种是建立基于区块链网络的基础设施， 一种是建立运行在这些去中心化和无需许可的网络上的应用。 当然这种分类方式可能不能囊括所有的在区块链上的开发模式，但这样分类是个挺好的开始。

人们所说的区块链基础设施是指， 节点和验证者(validators)运行的区块链协议的客户端实现，他们保障了链的正常运行。 这些客户端通常专注于分布式账本，网络，虚拟机，以及其他各种各样的底层工程类型。 客户端执行区块链协议的规则， 运行共识机制， 同时执行网络中所有的交易并确保所有节点之间的同步。 这也被称为核心区块链开发， 这不是大多数普通开发者脑海中的区块链或者web3开发的样子。区块链开发中有很多细分， 你可以通过使用诸如rollups(译者注：https://westar.io/blog/rollup/)， validiums(译者注：是个去年发明的词， Vitalik的twitter讨论过：https://twitter.com/vitalikbuterin/status/1267455602764251138 ， 是个线下的rollup), 或者volitions（译者注：数据相关， 以上三个词应该之后会涉及到， 这里只是概述， https://medium.com/starkware/volition-and-the-emerging-data-availability-spectrum-87e8bfa09bb） 这些技术，改善链的执行能力， 或者通过对协议的共识层的创新来提高去中心化和安全性等等。

还有目的是支持应用层的区块链基础设施， 他们提供访问区块链数据的API， 比如给智能合约的预言机(oracles)， 给后端的索引服务， 或者一些可以让你请求和监听智能合约事件的库， 去中心化索引服务等等。

最流行的区块链开发类型是在应用层之上。构建去中心化的应用程序（Dapps）可以有许多不同的形式，但它通常涉及一个智能合约和一个与该智能合约互动的用户界面来监听区块链状态的变化。这些应用程序可以服务于各种用例，可以用来构建去中心化的金融服务、游戏等等。

还有一些应用，从区块链上不同的智能合约、交易和事件中聚合数据，以提供更有用的信息，这些应用程序大多以数据分析为中心，不一定是去中心化的，但需要了解基于区块链的底层技术（译者注：如Nansen等）。

如果这些概念对你来说完全陌生，我建议先阅读后面“如何开始”（#how-to-get-started）这部分，或者谷歌一下你可能不理解的单词。

### 方向

在区块链开发中，有许多不同的专业方向，每个反向都需要不同的技能，对分布式系统、基本密码学的大致了解，以及了解智能合约如何运作一般情况下就足够了。 在本指南中，我将尝试对他们提供一个大致概述的同时，也就学习者应该优先考虑的资源和优先学习的顺序给出我所能提供的最佳指导。也有许多角色是我不熟悉的，所以请随时提出修改请求或用DM提出建议。


#### 基于技能


不同的专业方向需要不同的技能， 所需的技术栈和知识是由你想开发的应用及他在哪一层上所决定的。我觉得每个人首先都应该有坚实的基础， 在决定要专注于某种开发之前， 要应该去尝试不同的细分领域。 有的人是根据最终目的去选择他们要做什么方向， 另一些人像我一样对每件事都很有兴趣， 因此有选择困难症， 没办法决定自己要具体做哪个方向。

本指南将覆盖到所有这些主要的技术路线，同时所有人随时都可以发起pull-request来添加更多的， 或者扩展目前存在的。


- [前端开发](#front-end-development)
- [智能合约开发](#smart-contract-development)
- [区块链后端开发](#backend-development)
- [核心协议开发](#core-protocol-development)
- [全栈区块链开发](#full-stack-blockchain-development)

**即将更新**

- [安全](#security-engineer)
- [MEV searcher](#mev-searcher)  [Maximum Extractable Value, 矿工最大可提取价值] (https://www.ethereum.cn/Thinking/MEV))
- [密码学](#cryptographer)
- [区块链数据分析](#blockchain-data-analytics)

#### 基于应用

另一种区分区块链开发种类的方式， 不是基于技术栈， 而是基于目标用例。 我觉得这种方式是最受欢迎的， 但是为了让这篇文章可控， 有很多分类在这篇文章中我并没有涉及。

**即将更新**

- [区块链金融（DeFi）](#defi)
- [去中心化创作者经济（Creator Economy）](#creator-economy)
- [矿工最大可提取价值（MEV）](#mev)
- [L2s](#l2s)
- [基础设施（Infrastructure）](#infrastructure)
- [游戏](#gaming-development)
- [隐私（Privacy）](#privacy)
- [合作与公益项目（Coordination / Public goods）](#coordination--public-goods)

## 如何开始？

无论你是一位编程初学者还是已经从事这项工作多年， 此指南都将为你提供针对不同级别的资料。 如果发现专业路线图中有你已经充分了解的部分， 请随时跳过， 或者把他当做一次复习的机会， 来填补你可能有的理解上的空白。 

区块链开发一开始可能令人望而生畏， 因为他包含了很多始终变化的部分。 这些部分需要来自不同领域的基础知识，却依然在快速迭代，不像是如web开发这样的其他开发领域这么成熟。 此外每个应用都有一个金融相关的部分， 因为你是在一个价值层(value layer)上编程。然而这并不像你想象的那么难， 一旦你熟悉了基础知识， 理解了其他的一切， 通常只是把一些一般的理解应用于特定的情况而已。如果你如果你建立了一个坚实的基础， 你会发现处理一些复杂的问题或者解决新问题的时候会容易得多。

如果你有计算机科学， 数学或者其他相关的背景， 你会发现开始区块链变成容易的多， 因为很多基础概念来自于算法或者数据结构。 如果你是个这方面的新手， 请耐心一点完成最初的几个步骤以使得你不要感到不知所措， 当你开始熟悉这些材料的时候， 你会发现后续的只是更容易被弄懂了。

（译者注：后续的延伸阅读材料多数是英语， 除了会添加一些中文的阅读材料外， 在完成这个指南后将会挑选一些内容进行翻译并提供相应链接）

### 一般基础

为了开始基于以太坊的区块链编程， 第一件需要搞清楚的事情就是区块链是如何工作的， 搞清楚这个才能在心中建立一种每部分是如何运行的具体印象， 这样可以让你更好的了解设计原则， 从而也让你更好的管理你的开发。

#### 区块链

区块链(Blockchain)这个词有两种不同的含义， 他既是一个数据结构， 同时又是一个计算机网络。

区块链（数据结构）由捆绑在一个容器内的交易集或数据集组成，每个容器内都有前一个容器（区块）中的数据的加密[哈希](https://www.youtube.com/watch?v=QJ010l-pBpE)。如果前一个区块的内容发生变化，这个区块的哈希值也会发生变化，由于这个特点，我们可以保证数据没有被篡改。区块链数据结构的第二个特性是，它是”只追加“的（Append-only）。你不能向这个结构前面添加数据，也不能修改已经在其中的数据，因为这将改变所有在之后的区块的哈希值。这就是为什么我们称区块链为不可变的。

区块链（网络）是一个计算机网络，它有一个同步的交易账本，使用区块链（数据结构）来存储数据（通常在merkle/verkle树内， merkle树的根节点是子结点数据的哈希，可以用来快速比较大量的数据是不是一致， 关于merkle树的介绍详见：https://zhuanlan.zhihu.com/p/39271872）。

区块链由矿工/验证者提供算力，在共识算法下运作，这种算法协调产生和组织区块，以及通过持续更新区块链的头部来标识哪个是最长的链。有三个开发者们试图去优化的区块链的属性；安全、去中心化和可扩展性。

通过共识算法的设计来实现安全和去中心化，在共识算法中，要么不同的参与者以在一个大型计算设备上运行一个非常昂贵的计算过程的方式来提供资源，这种方式称为[工作证明](https://en.wikipedia.org/wiki/Proof_of_work) (PoW)，或者在网络中抵押经济资源， 这种方式称为[权益证明](https://ethereum.org/en/developers/docs/consensus-mechanisms/pos/) (PoS)。参与者越多，权力在这些参与者中越分散，安全性和去中心化程度就越高。

还有很多其他措施来提高去中心化，比如可以在消费类硬件上运行的客户端软件，这样任何人都可以在他们的节点上同步区块链的状态；尽量减少每个区块可以处理的交易数量，以免使它的状态过大等等。

**延伸阅读**

这里我只是简单解释了一下， 为了能更好的理解区块链是怎么运行的， 请查看以下材料

- [Blockchain Explained - Investopedia](https://www.investopedia.com/terms/b/blockchain.asp)
- [Blockchain 101 - Anders Brownworth](https://www.youtube.com/watch?v=_160oMzblY8)
- [But how does Bitcoin actually work? - 3Blue1Brown](https://www.youtube.com/watch?v=bBC-nXj3Ng4)
- Optional (cultural significance): [Bitcoin whitepaper](https://bitcoin.org/bitcoin.pdf)

**中文延伸阅读**

- [李永乐老师的视频] (https://www.bilibili.com/video/BV1Bb411B7dq）


#### 以太坊

由于这是一份关于基于以太坊的区块链开发指南， 因此我们作为开发者需要了解以太坊的工作原理， 也要知道未来的更新和发展方向。 如果你之前做过Web开发， 你可以把未来的更新类比于新的ECMAScript标准， 或者一个新的浏览器编译对象（比如WASM）， 一个新的引擎（比如V8）等等……以太坊是不断发展的， 在网络的核心技术变的稳定之前会有相当多的变化。

一个很好的开始了解以太网工作原理的方式是看[Austin Griffith](https://twitter.com/austingriffith)的[ETH.BUILD YouTube 播放列表](https://www.youtube.com/playlist?list=PLJz1HruEnenCXH7KW7wBCEBnBLOVkiqIi)， 他在其中说明了ETH各部分是如何运作的。

”在以太坊宇宙中， 有一个独一无二的， 拥有至高无上地位的计算机（他被称作以太坊虚拟机， 或者EVM）， 以太坊中的每个参与者都对他的状态达成一致。 任何参与者都可以向这个计算机广播一个请求， 来进行一次任意的计算。 每当一个这样的请求被广播， 网络上的其他参与者就会验证，确认， 并执行（execute）该计算。 执行过程会改变EVM的状态， 这个变化会被提交并传播给整个网络“(来源: [以太坊官方文档](https://ethereum.org/en/developers/docs))

学习以太坊的基础知识， 最好的方式莫过于查阅[以太坊官方文档](https://ethereum.org/en/developers/docs)。 而以下是其中各部分的链接)：

- [以太坊简介](https://ethereum.org/zh/developers/docs/intro-to-ethereum/)
- [ETH简介](https://ethereum.org/zh/developers/docs/intro-to-ether/)
- [去中心化应用简介](https://ethereum.org/zh/developers/docs/dapps/)
- [Web2与Web3的对比](https://ethereum.org/zh/developers/docs/web2-vs-web3/)
- [账户](https://ethereum.org/zh/developers/docs/accounts/)
- [交易](https://ethereum.org/zh/developers/docs/transactions/)
- [以太坊虚拟机 (EVM)](https://ethereum.org/zh/developers/docs/blocks/)
- [Gas费用](https://ethereum.org/zh/developers/docs/evm/) (这里我们跳过opcodes部分， 晚点我们再来讨论他)
- [节点和客户端](https://ethereum.org/zh/developers/docs/gas/)
- [网络](https://ethereum.org/zh/developers/docs/nodes-and-clients/)
- [共识机制](https://ethereum.org/zh/developers/docs/consensus-mechanisms/)
- [治理 / 以太坊改进提议过程 (EIP process)](https://ethereum.org/zh/governance/)
- **以太坊路线图 - 终局之战**

[这幅流程图](https://github.com/dcbuild3r/blockchain-development-guide/blob/main/images/ethereum_roadmap.png) 向我们展示了所有未来一年会被实现的各种变化。 虽然现在暂时没有必要了解每一部分是做什么的， 但是如果你有兴趣了解一下还是有好处。如果你有兴趣，我建议观看图片后附加的视频资源，以了解流程图中每一部分的意义。

- **延伸阅读**
  - [以太坊白皮书](https://ethereum.org/zh/whitepaper/)
  - [为什么要PoS - Vitalik Buterin](https://vitalik.ca/general/2020/11/06/pos2020.html)

#### 智能合约

智能合约是一个在以太坊上运行的程序。 它是一段包含了函数和数据（状态）的代码， 他被部署到以太坊上的一个特定地址上。

智能合约是一种特殊的[以太坊账户](https://ethereum.org/zh/developers/docs/accounts/) ， 这意味着它自身有余额， 也可以在网络中发送交易。 它被部署到网络上并且运行， 用户账户（外部拥有账户externally-owned accounts， 也可叫做EOAs）可以和智能合约交互并提交一个交易， 这些交易与可被访问的函数进行交互。 智能合约可以通过代码来定义规则， 比如一个智能合约可以允许两方交易他们的代币（如Uniswap）

**怎么创建一个智能合约?**

在以太坊虚拟机（EVM）上最流行的智能合约编程语言是 [Solidity](https://solidity-cn.readthedocs.io/zh/develop/) (译者注：这里我提供了中文版的链接， 但中文版文档并不是最新的， 如果有能力还是组好查阅英文版文档)， 它是一种收到C++, Python和Javascript影响的高级语言， 因此语法看上去很熟悉。 Solidity是静态类型的， 支持继承， 库， 用户定义类型等特性的语言。 Solidity程序需要通过编译器运行以产生低级的字节码（bytecode）. 字节码是SVM可以理解和执行的命令。

此外还有一些语言可以用来编写面相于EVM的合约， 包括 [Vyper](https://vyper.readthedocs.io/en/stable/toctree.html)和[Fe](https://fe-lang.org/)， 每种语言都有它的优缺点， 但是这些语言并没有solidity这么强大的开发生态， 因此它们没有被非常广泛的使用。

这里是一个[简单的计数器](https://solidity-by-example.org/first-app/) 在Solidity中的样子:

```js
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.10;

contract Counter {
    uint public count;

    // Function to get the current count
    function get() public view returns (uint) {
        return count;
    }

    // Function to increment count by 1
    function inc() public {
        count += 1;
    }

    // Function to decrement count by 1
    function dec() public {
        count -= 1;
    }
}
```

这段代码一开始使用`pragma solidity + version`关键字来声明你所使用的Solidity的版本。创建合约时采用`contract ContractName {}` 这样的语法。程序的逻辑在前面的大括号中被实现。之后我们声明了一个很简单的， 叫做"count"的变量， 他是无符号整型(unsigned integer，只能存储正整数)。 之后我们声明了三个函数， 第一个用来获取`count`变量中的值， 第二个把变量中的值加一， 最后一个把变量中的值减一。 函数前的`public`关键字(keyword)的作用是使被修饰的函数可以被链上的任意一个地址调用（无论这个地址是一个合约地址， 还是一个用户钱包的地址）。 `view` 修改器（modifier）的作用是让这个函数中不能合约中的”状态“进行修改（也就是前面声明的这个变量，他只可以读）。 而`returns`关键字则用来指明这个函数会返回什么类型的对象， 比如对上面这段代码，`get()`函数的returns就规定了他的返回值为无符号整型(unsigned integer)。 而在`//`之后是会被Solidity编译器忽略的注释。 注释被用来让代码变得可读和易于管理， 当我们和团队一起工作， 或者过了一段时间再来看自己代码的时候注释就会变得非常有用。 他扮演了文档的角色， 让读代码的人能更清楚的知道代码在做什么。

**我怎么编译和部署我的第一个合约？**

为了编写和部署我们的第一个智能合约， 我们将使用Remix IDE， 他是一个网站， 我们可以在上面写智能合约， 编译并部署在一个EVM的本地实例上。我们同时可以和本地部署的合约交互来测试合约的功能。为了部署上文提到的简单的计数器合约， 在[Remix](https://remix.ethereum.org/)， 在contracts文件夹下添加新的文件， 并将它命名为`Counter.sol`, 我们把[counter example](https://solidity-by-example.org/first-app/) 中的代码复制粘贴到这个文件里。之后左侧工具栏， 从上往下数的第二个图标， 他是一个Solidity语言的logo, 在Remix里代表了Solidity编译器。 在编译器中选择版本0.8.10， 这是我们合约中的Solidity版本， 然后点击 ”Compile Counter.sol“. 你编译你的合约后， 点击左侧工具栏从上往下数的第三个图标， 它此时应该叫"Deploy & Run Transactions"（部署和运行交易）。 点击"Deploy"(部署)。 等待部署完成后，页面下方你会看到一个成功提示，代表着你已经成功编译和部署了你的第一个智能合约！现在你部署了他， 你可以在同一个页面的左下角， 通过调用`inc()` 和 `dec()` 函数来和该合约交互， 试着增加或减少`count`变量的值。 并可以通过调用`get()`函数来获取`count`变量的值。

![remix](./images/remix.png)

我们将在之后”智能合约开发“部分， 对智能合约的开发、测试和部署进行更深入的探讨。 

#### Web 2.0 

虽然区块链开发一般是指开发去中心化应用， 但用于构建这些应用程序的技术有很大一块是重叠的。 我们使用传统Web技术开发分布式应用（Dapp）的用户界面(UI)， 并且最终部署在因特网上。为了和智能合约交互，用户需要提交一个请求给部署了一个特定应用的服务器， 这个应用需要创建一个交易，通过用户的web3钱包（比如metamask）从用户处获取签名， 之后把交易提交给以太坊RPC（译者注：RPC是远程过程调用的缩写， 是从一台机器{客户端}上通过参数传递的方式调用另一台机器{服务器}上的一个函数或方法{可以统称为服务}并得到返回的结果的过程）。 该交易会进入mempool（内存池，正如正在描述的过程， 这是一组交易， 交易被广播给节点后存在这里等待），之后被矿工（对PoW过程） 或验证者(PoS)拾取， 在区块链中运行。一旦区块链通过成功调用一个智能合约中的函数发送（emit）一个事件(event) ， 用户界面就会更新。 以上就是去中心化应用最常见的流程。

任何想要构建全栈区块链应用的开发者都需要了解互联网和他最重要的协议是怎么工作的， 并且还需要知道如何在主要平台（web, mobile等）上构建UI。 你可以认为web3实际上是在互联网上增加了一个原生的价值层， 它也有助于构建社会协作和资源分配的去中心化的自治组织结构。了解Web和建立在其上的每个技术是如何运行的， 同时了解加密货币和web3如何工作的， 对创建一个更好的应用很有帮助。

我相信即使你不从事前端开发的工作，最基本的了解Web是如何工作的依然很有帮助。 因为在几乎所有类型的开发中，你都会以某种形式与前端对接。对于这些基础知识，一个很好的学习路线图是[roadmap.sh frontend](https://roadmap.sh/frontend)， 他提供了怎么开始学习这些知识。 同时学习怎么对你的代码进行版本控制， Git以及GitHub/GitLab这样的托管存储仓库(host repositories)无疑是最受欢迎的版本控制和软件开发协作工具， 

![前端路线图](./images/FE_roadmap.png)

- **学习资源**
- [因特网是如何工作的(How does the internet work)](https://www.youtube.com/watch?v=zN8YNNHcaZc)
- [CS50 HTTP课程](https://www.youtube.com/watch?v=PUPDGbnpSjw) ([CS50 课程](https://www.edx.org/course/introduction-computer-science-harvardx-cs50x) 在edX上的一个很好的课程)
- [freeCodeCamp](https://www.freecodecamp.org/) - 在这里你可以学习关于HTML, CSS和JS怎么工作的基础。 除非你想要做前端开发， 你可能用不到他， 但是还是可以试试看并且学习他是如何工作的

#### 为什么去中心化很重要?

在web2.0的世界中， 我们会在Google和Facebook这样的平台上有一个主要账户， 这个账户可以用来登录其他服务。 所有这些数据会被托管在一个中心化服务器中， 这样我们的个人隐私数据也可以随时被广告软件使用来卖给我们产品。 作为对我们个人数据的交换， 我们获得免费的服务。 这个巨大的中心化中心化实体通过我们每个人每天使用的产品， 控制了我们的日常生活， 从而拥有了巨大的权力。 这个商业模式已经运行了几十年。 

当我们把服务去中心化， 并且变成一个主权用户（sovereign user）， 你就不再能被平台驱逐，被监管和被利用。只要你可以访问任何一台电脑， 只要你可以访问互联网， 你就可以使用无需许可和去中心化的区块链上的任意应用。 没人能阻止从底层组织你的访问， 因为任意时候你都可以运行一个节点， 提交一个对智能合约的调用， 提交一个交易到区块链网络。 去中心化应用仍然处于起步阶段， 大多数应用都不够成熟， 无法被主流接受。 然而对这些应用依然有很多需求， 该行业也在迅速发展。

在web3世界， 用户拥有他们的资产， 他们的钱， 他们的身份和他们数据。 这从根本上为提供更好的用户体验提供了潜力， 当这些技术变得足够成熟的时候也将支持更多的用户。 最终将会有去中心化的社交网络， 用户拥有自己的内容， 艺术家和音乐家可以产出自己的作品， 并且卖NFT， 从版税中获取收益， 从而有更大的动力更好的和观众互动。 我们将会有一个虚拟世界， 这里人们拥有他们自己的数字身份， 虚拟物品和土地等等。 web3世界的可能性日与日俱增， 我认为他是人类历史上最激动人心的技术之一， 它有着无与伦比的可能。

### Web3 价值

web3运动是一个为传统互联网添加价值层的运动， 在这里我们可以为社会的进步建立激励机制， 建立一个更公平的世界， 在这个世界里产品和服务的访达是公开的， 分布式的， 也无需授权。 地球上的每个人不问出处， 都可以公平的使用。

为实现建立更好的世界这个目标， 已经有很多很好的解决方案产品， 包括[Kernel](https://kernel.community/en/), [Gitcoin](https://gitcoin.co/), [GreenPill](https://greenpill.party/) 等等， 他们都试图帮助教育和资助新一代公益项目和基础设施建设。 作为一名区块链开发者， 了解为什么这样一种系统要被建立起来很重要， 时刻记得我们创造的产品和服务所体现的价值， 以确保我们不会去重现现有的web2中心化的世界。

为了了解web3的价值以及我们如何创造一个更公平的世界， 请翻阅[Kernel's web3 课程](https://kernel.community/en/learn/).

### 多尝试

区块链开发看上去很难， 但实际上你只是在刚接触的时候会觉得不知所措。 但不如暂时忽略这种感受， 把区块链编程看成一个冒险游戏。 你可以去探索各种可能， 用你觉得有趣的技术试着去写一些小项目， 看看其他人都在做什么， 试着和他们的产品做一些交互， 和他们讨论讨论大家喜欢的应用， 技术， 看看这些东西是如何工作的。

随着你继续阅读这篇指南， 你将开始深入不同的领域。 web3中有很多值得研究的有趣的基础方向和可以去搭建的应用类型， 因此除非一开始你很罕见的就有一个目标， 否则一开始就选择什么方向很困难。我个人认为应该去在短时间内尝试你锁感兴趣的一切， 才能让你深入了解是否愿意专注于该特定领域。为此我建议进入到不同的开发小组和研究小组， 多参与讨论要建设的这些东西是什么样子的， 你要研究的问题类型是什么， 以及如何在该领域有更好的发展等等。 这里有一些我最喜欢的小组推荐， 包括 [Newt](https://twitter.com/wearenewt)， 这个是Aave的实验性分支。 Newt完全由社区驱动，试图促进开源实验项目，在这里你可以参与现有的实验性项目或者创建一个你自己的项目。 在这里你可以遇到志同道合的开发者， 建设很酷的项目， 探索web3中不同的开发领域， 包括DeFi， NFT等等。 [DeveloperDAO](https://twitter.com/developer_dao) 和 [EthernautDAO](https://twitter.com/EthernautDAO) 也是很好的开发者社区， 在这里你可以试着去找一些有相同爱好的个人， 共同去探寻web3中的可能， 甚至可以找到全职的工作。

### 与他人联结

区块链开发是个相当新的领域， 因此关于如何在web3中构建应用的信息多数在互联网上， 而不是在大学或者其他教育机构中。这听上去有些孤独， 但其实不必！世界各地的人们都在学习怎么用这些技术搭建最酷的项目， 每个人都在试图向他人学习。 正如刚刚锁提到的， 加入类似于Newt和DeveloperDAO， EthernautDAO之类的DAO和小组，在twitter上分享你的学习之旅， 向大家分享你的学习这些技术时的见解。 在这个过程中你一定会找到可以分享自己兴趣点的， 志同道合的人， 这一点很重要， 特别是在你试图向一个没有过往知识的人尽可能简单的解释一个复杂概念的时候， 这个过程会强迫你对你要解释的主题有充分足够的认识。 结对编程和结对学习是巩固新知识的一个好方法。就我个人而言， 结交一些从事区块链开发的朋友非常有趣， 这会帮助我比之前花更多的时间学习这些资料。

目前Twitter是大多数Web3和Blockchain的建设者， 研究者和创作者分享他们见解的平台， 因此要跟上新技术， 必须关注这些Twitter的信息。 我建议不要过度使用社交媒体， 因为他会导致生产力急剧下降。 这是一个需要长期摸索达到的平衡。 一个好的建议是， 每当你想要查看Twitter和Discord等社交媒体的时候， 你都有一个明确的目标。 比如目标可以是： 我想要学习我的朋友们研究出了哪些新的gas优化方法？我也强烈建议创建一些包含不同类型人群的列表， 以便于你查看不同的主题（DeFi, NFTs, MEV, 智能合约, 前端, 设计等等）。 如果你想未来重温一些有趣的推文， 使用书签功能也是个不错的办法。

另一个和开发者们认识的途径是去hackathon和会议。 如果你有能力参加这些会议， 那么一定要去， 但是如果你没有足够的资金参与这些会议的话， 有一些会议会给初次参加的人一笔补助金， 比如[PadawanDAO](https://twitter.com/PadawanDAO)等等。 经常问问看周围的志愿者就会得到免费的入场券。 而且这个社区里还有很多好心人会捐助一些资金给这些没有足够资金却想要参与其中的人们。 像hackathon这样的可以亲身参与的活动是提升技能和认识人的绝佳方法。 这是很多现在流行的项目开始的地方， 也是这些项目创始人第一次见面的地方， 2022年我建议可以去 [Devconnect](https://twitter.com/EFDevconnect) (阿姆斯特丹), [ETHPrague](https://twitter.com/EthPrague)（布拉格）, [ETHCC](https://twitter.com/EthCC)/[ETHParis](https://twitter.com/ETHParis)（巴黎） and [Devcon](https://twitter.com/EFDevcon) (波哥大).这里有一个2022年以太坊相关活动的[很好的列表](https://docs.google.com/spreadsheets/d/1NEu_FCc1hnGAuRgPmbXXpf0h2lCrCOlMKbbFEqgkVDQ/edit#gid=0)， 几乎在每个大洲都有大型活动， 也有不同社区组织的小型地方活动， 你可以在你附近找到一些和区块链相关的活动或者索性自己发起一个活动吧！

我最近还创建了一个[区块链开发者列表](https://twitter.com/i/lists/1483458041412526084)， 我认为你想学习区块链开发， 你应该关注这个列表， 这是一个依然在维护中的列表， 如果你觉得有什么想要加进这个列表的， 请随时通过私信发给我， 我会考虑是不是将他们添加到列表中。


### 开始建设

很明显， 下一步，也是开始区块链开发的最后一步， 就是开始建设吧！在你读完前面几部分的这么多介绍性和基础性材料后， 你终于准备好投入到下面列出的某个专门领域中了。 如果你依然不太确定你要选择哪个方向， 就以开始全栈区块链开发为目标学习， 试试看所有的东西。开始写代码， 无论写出的代码多差， 然后试着从比你更资深的开发那里获得反馈。 请查阅我在下面列出的路线图， 学习概念， 记笔记， 围绕着他做一些实操， 做一些测试然后继续下一项。 如果这个过程中有什么主题让你感兴趣， 就用他来实际建设点东西， 看看这些技术会把你带向何方。 你自己的好奇心和兴趣是你在学习区块链开发时最好的朋友。 你要持续不断的问自己， 为什么我写的代码工作正常以及我怎么能把他优化的更好。 如果你自己没有答案的话就去找个人来帮你解释， 或者做一次Code Review。 多看看别人写的高质量代码也会对你很有帮助， 如果你学习solidity， 最好的进阶方式是看别人的产品代码， 比如Aave v3, Uniswap v3, Balancer v2等等。 同样的原则也同样适用于别的方向。

一旦你开始建设一些东西， 并把它分享给整个世界（除非他是个能给你带来丰厚利润的MEV机器人）！在推特上分享， 在不同的discord频道里分享， 这将会给你所做的事情带来关注度， 并且也许还将给你带来一些建设性的反馈， 还会让你认识一些志同道合的新朋友。 如果你在建设一些比较复杂的项目， 觉得有一天别人会读你的diamante，试着同时准备完备的文档，在代码里添加有用的注解。 把代码在Github上以公开方式分享也是个好主意， 这会成为你简历的一部分， 有助于你申请一些新的职位。 接下里的部分我也将会介绍怎么在web3世界中获得一个职位。

## 基于技能开发

现在我们开始讨论不同， 在开始之前深入不同方向之前， 请确保你已经阅读了 [基础部分](#general-foundation). 建议你也读过了 [基于技能开发](#skill-based-development) 和 [基于应用开发](#application-based-development) 中对每个方向的介绍。 以便在深入了解某个具体专业之前， 你对每个方向上有什么，哪些内容让你感兴趣有足够的了解。 本节将重点对区块链开发中的专业方向进行分类， 了解每一种需要的技能组合

### 前端开发

Front-end (FE) development is probably the easiest out of all of the ones I'll be listing in my guide. Most of the technology stack blockchain developers use to build user interfaces for their applications overlaps with the traditional web-development infrastructure and so there are is a mature ecosystem of languages, libraries, and APIs you can make use of as a developer to make your life much easier as well as a vast community of developers which maintain codebases, provide support through platforms like [StackOverflow](https://stackoverflow.com/) and create very well produced tutorials and documentations for learning these established technologies, something which isn't the norm in rapidly emerging and constantly evolving web3 technologies.

The key principles of front-development require knowing how to structure and style websites, how to make them dynamic with JavaScript and different frameworks, how to manage state within applications, basic design, how to fetch data from APIs and databases, and how to create good web3 user experiences regarding wallets and the interactions with the smart contract backend of your application. One of the biggest differences in web3 FE development is user-authentication as instead of logging in with your email and password or your Google account, you log in with your wallet using a third-party application like [Metamask](https://metamask.io/) or [WalletConnect](https://walletconnect.com/) and protocols like [ENS](https://ens.domains/) to display information about the user (provided they have an Ethereum domain). If a smart contract contains a state which represents past interactions with the application by the user, you also need to fetch historical data from the blockchain on-demand or maintain a local database with indexed data which is easily queriable by the FE of the application. 

As a front-end blockchain developer you need to know what a Contract Application Binary Interface ([ABI](https://docs.soliditylang.org/en/v0.8.11/abi-spec.html)) is in order to be able to interact with smart contracts on the Ethereum blockchain or on an L2 like Optimism, Arbitrum, Starknet, or ZkSync which are Ethereum-based scaling solutions that we'll cover in the [L2 section](#l2). You also need to query data from various APIs to accurately display the price of various assets (if applicable), the user's balance of ERC20 tokens or NFTs, and various other data you might need from either the blockchain itself or an external database.

Another interesting feature of programming decentralized applications is the need for building applications that are not hosted on a centralized server, to remedy this problem many developers have their web interfaces open-sourced and have many instances of those interfaces on decentralized storage solutions like IPFS, Arweave, and others. In this way, if one of the servers hosting the interface to interact with the smart contracts goes down, users can interact with it from many other different places. It's also amazing that since the functions are able to be called by anyone, users can interact with decentralized applications from completely different frontends as long as they have the ABI, this allows for massive composability which we'll cover a bit later.

This roadmap will focus on the frontend technologies that I've seen are mostly used in blockchain development today. I've used the roadmap.sh frontend roadmap, a friend's tech stack, and my experience as a reference for creating this specialization.  If you are a more experienced reader feel free to suggest pull requests to add/edit/remove content or you can suggest changes by DMing me on Twitter or Telegram (@dcbuild3r).

#### HTML, CSS, JS, Web APIs

The pillars of web development technologies are HyperText Markup Language (HTML), Cascading Style Sheets (CSS), JavaScript (JS), and web application programming interfaces (APIs). 

[HTML](https://en.wikipedia.org/wiki/HTML) is the language that is used to structure websites, with HTML you can insert text, images, videos, create different sections for your website, create links to other sites, and more. [CSS](https://en.wikipedia.org/wiki/CSS) is a styling language that helps you edit how your HTML elements look, how they are displayed and how they are arranged on your screen. It is also what makes user interfaces responsive for different devices like mobile, tablet, laptop, desktop, and others by providing APIs which dynamically resize your HTML elements based on the width and height of the screen a specific user has. [JavaScript](https://en.wikipedia.org/wiki/JavaScript) is a programming language that makes your HTML elements dynamic, it allows for things like complex animations, dynamic formatting of elements depending on given inputs, state management within your application, much more utility thanks to its programmability, and more. HTML, CSS, and JavaScript are the only 3 technologies that browsers understand, the rest of the technologies mentioned in this specialization end up compiling to an optimized HTML, CSS, and JS bundle which the browser can process and interpret.

The best place to learn the basics of web development in my opinion is [freeCodeCamp](https://www.freecodecamp.org/) where you can do the lessons in the first two sections named "Responsive Web Design" and "JavaScript Algorithms and Data Structures". It says that each section takes about 300 hours each, but usually, you can do it in much less since it's a conservative estimate. After you've gone through these two sections and made the initial projects that are required to fulfill them you can move on to learning React. 

#### React

In modern web development, you'll almost never write vanilla HTML, CSS, and JavaScript to build your websites. Web developers learn a view framework that helps them to better structure their code with components and also optimize the way in which components are rendered and how changes to the state of the application affect what the users see. The most popular web development framework is React with a wide margin compared to Vue.js. React was originally developed by the Facebook team, but was open-sourced early on and now it has thousands of contributors and many full-time maintainers who are constantly pushing the framework forward.

Most of the user interfaces for blockchain applications are programmed using React and there are many React component libraries that you can reuse from the community to perform common tasks like logging with an Ethereum wallet, switching networks, and also so-called React hooks libraries (i.e. [eth-hooks](https://github.com/scaffold-eth/eth-hooks)) which let you fetch different data like balance, block number, prices and more.

I believe that React is best learned from the official documentation, but there are also other resources for people that learn better with video content. Here is a list of React learning resources that I recommend:
- [React in 100 Seconds - Fireship](https://www.youtube.com/watch?v=Tn6-PIqc4UM)
- [React roadmap](https://roadmap.sh/react)
- [Official React documentation](https://reactjs.org/docs/getting-started.html)
- [awesome-react](https://github.com/enaqx/awesome-react) - This GitHub repository aggregates many useful resources for React developers, it has tutorials, tooling, component libraries, frameworks, design patterns, guidelines, and much more. It is a good place to look for inspiration and resources when using React.
- If you want a paid video course I can recommend either [ZTM's React course](https://www.udemy.com/course/complete-react-developer-zero-to-mastery/) or [Maximilian Schwarzmuller's React course](https://www.udemy.com/share/101Wby3@JDt64oz7fMQjMAWBtrmk5wuDfzeEWDYkQeRN1yCa5yjMEWG0cKPDILlqSqtSXEI7/). On Udemy there are sales periods every once in a while which allow you to buy courses for `$15` instead of `$200`, so wait for one of those, never buy for the full price.
- [freeCodeCamp React course on YT](https://youtu.be/bMknfKXIFA8)
- [Learn React for free](https://scrimba.com/learn/learnreact)

After you feel like you've understood how React works, you have learned about lifecycle methods, hooks, how to pass down data through props, how to use the Context API, etc. I recommend trying to build the front end of a web3 app like Uniswap or an NFT marketplace like OpenSea. To rapidly prototype the design I recommend using [tailwind.css](https://tailwindcss.com) and Chrome browser developer tooling to inspect the styles of the site you're trying to recreate. Also, don't forget to use CSS flexbox/grid where necessary. Try to simulate the data inside of these apps using hardcoded JSON objects.

#### Typescript

[Typescript](https://www.typescriptlang.org) is a superset of JavaScript which allows you to statically type JavaScript code. This means that you declare the types of variables (integer, string, ...). It allows for a better developer experience as the Typescript compiler can catch many errors ahead of time since it checks the types of the objects ahead of time. It also allows developers to tap into extra features on top of JavaScript which allows writing more expressive JavaScript. Remember that Typescript cannot be run by the browser and needs a compiler to convert TypeScript code into runnable JavaScript. Typescript is widely used by the web-development community thanks to its features that improve security, readability, allow for a better development experience inside of the IDE with autocompletion, and add cool new syntactic sugar on top of JavaScript.

I recommend going to the [Typescript documentation](https://www.typescriptlang.org/docs/handbook/intro.html), it is good to get into the habit of going to official documentation since they are usually the right place to visit if you are learning new technology. Once you have the basics down try building a simple application with it or refactor an existing application in a way that uses the technology that you are learning.

#### Next.js

[Next.js](https://nextjs.org) is a React framework that enables server-side rendering, static site generation, does smart bundling, route pre-fetching, and a lot more. Next.js is able to heavily optimize your websites by only loading what you need on-demand instead of having to load up the entire site at the beginning. It also allows for a much better experience with creating API routes thanks to its file-system routing feature, it optimizes images, it has Typescript support, it helps with i18n API internationalized routing, and a lot more.

**Learning resources:**
- [Next.js documentation](https://nextjs.org/docs)
- [awesome-nextjs](https://github.com/unicodeveloper/awesome-nextjs)

#### Moralis

[Moralis](https://moralis.io) is a web3 development platform that helps abstract away the pain of having to build all the backend infrastructure needed to run web3 applications from scratch. Moralis provides an easy-to-use API that lets you fetch any data that you want from various blockchains, handles web3 user authentication, allows you to listen to smart contract events in real time, gives you access to historical data, has support for cloud functions, and much more. If you've never worked with blockchains it is the best way to get onboarded and start building web3 applications, as the Moralis SDK is intuitive to use for anyone that has experience with JavaScript/TypeScript. 

**Learning resources**
- [Moralis documentation](https://docs.moralis.io/moralis-server/getting-started)
- [Moralis YT channel](https://www.youtube.com/c/MoralisWeb3)

#### Web3 libraries

[Ethers.js](https://docs.ethers.io/) is one of the most popular libraries for interacting with the Ethereum Blockchain and its ecosystem. Smart contracts that are deployed on the Ethereum blockchain have functions that can be called externally by any other account on Ethereum, be it an externally owned account (EOA = user wallet) or another smart contract. Many of these functions require certain parameters to be fed into them, they also rely oftentimes on an external state like prices of tokens on the blockchain, balances of the user's wallet, and more. Ethers.js is what allows a user interface to call these functions, users can input certain information in the frontend of your application and that information can be put into the function call of the smart contract, after the transaction is broadcasted the EVM will try to execute that function call and if every check inside of the function doesn't give out any errors it will execute, otherwise, the transaction will revert.

Ethers.js is currently the most popular Ethereum library among developers, but there are alternatives like web3.js, web3.py, Brownie, and many others. The second most popular framework is web3.js and it is the Ethereum JavaScript library that has been around the longest. For a comparison of ethers.js and web3.js read [this article](https://moralis.io/web3-js-vs-ethers-js-guide-to-eth-javascript-libraries/) written by the Moralis developer team.

**Learning resources**
- [ethers.js documentation](https://docs.ethers.io/)


[Web3.js](https://web3js.readthedocs.io/) is a collection of libraries that allow you to interact with a local or remote ethereum node using HTTP, IPC or WebSocket. The web3 JavaScript library interacts with the Ethereum blockchain. It can retrieve user accounts, send transactions, interact with smart contracts, and more.

**Learning resources**
- [web3.js documentation](https://web3js.readthedocs.io/en/v1.7.1/getting-started.html)

#### Design

As a front-end developer, you need to focus on how your application looks and how it feels to use it. A big part of that is designed, before building a website you should prototype how you want it to look, design how your users will interact with your application, how will that fit with the use case of your application, and what you want to accomplish with it, how to make it so that your users like using it and more. UI/UX is a specialization of its own, but every single front-end developer should have strong foundations in UI/UX regardless. Most big teams will have designers which will prototype applications using tools like Figma, Framer Motion, and various other tools. As a front-end developer, your task is to turn those designs into functioning code and hook all of the components to the APIs and databases necessary as well as creating the functionality of the application. 

One of the most popular tools to prototype and design websites is Figma, so every FE developer should know how to use the application. 

**Learning resources**
- [freeCodeCamp Figma YT course](https://youtu.be/jwCmIBJ8Jtc)
- 

#### Web3 templates

When you are building web3 applications you usually start with a template. A template is just a group of libraries, pre-built user interfaces, and another tooling that create a favorable environment to build your application. A lot of the initial hard work to set up a project can be reused across projects to save time and effort on building redundant infrastructure. Many web3 templates have support for smart contracts out of the box which is what you'll be interacting with most of the time as a front-end developer. It is good to know the basics of smart contracts and understand how to get a contract factory out of the ABI to call its methods within your user interface. That's the biggest overhead when building in web3 in comparison to being a frontend developer in web2 where you only have to care about fetching data from REST or GraphQL APIs.


You can build your own templates depending on your needs, or modify already existing ones. Popular web3 templates include
- [moralis-starters](https://docs.moralis.io/moralis-server/getting-started/boilerplate-projects)
- [scaffold-eth](https://github.com/austintgriffith/scaffold-eth)
- [create-eth-app](https://github.com/paulrberg/create-eth-app)

#### Tooling

As a developer, there are many tools you'll use to make building applications easier and more efficient, to collaborate on projects with other people, to manage dependencies, and much more. This is a short section on different tooling you'll find yourself using regularly.

**Package management**

If you've gotten this far in the front-end specialization you've certainly had to install packages like React, Next.js, tailwind.css, ethers.js, and many others. The most popular package managers in the JavaScript ecosystem are `npm` and `yarn`. Package managers allow you to keep track of which versions of which external code libraries your application uses as well as how the project's code is structured, how to run different tests, how to run your program, and various other miscellaneous tasks. 

As you build more complex applications it is good to learn the depths of your package manager, how to structure `package.json` files, how to write scripts that automate the boring stuff, how to set up a CI/CD pipeline (we'll talk about this in a bit), and more.

- [Package management basics](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management)
- [npm](https://www.npmjs.com/)
- [yarn](https://yarnpkg.com/)

**Styling/Animation**

There are many CSS libraries and frameworks which modify the way in which you write CSS. There are libraries that allow you to write CSS within JavaScript, component libraries for React which have a lot of the styling done for you, animation libraries, and more. I'll mention a few of the most popular ones, feel free to suggest changes as I'm not an expert in the area.

- [styled-components](https://www.styled-components.com/) (CSS in JS)
- [Tailwind.css](https://tailwindcss.com/) (CSS framework)
- [Framer Motion](https://www.framer.com/motion/) (Animations framework)
- [Chakra UI](https://chakra-ui.com/) (component library)
- [Material UI](https://mui.com/) (component library)
- [Sass](https://sass-lang.com/) (CSS pre-processor)
- [PostCSS](https://postcss.org/) (CSS pre-,post-processor)
- [awesome-CSS](https://github.com/awesome-css-group/awesome-css) (CSS learning repo)

**Linting/Formatting**

A linter is a static code analysis tool used to flag programming errors, bugs, stylistic errors, and suspicious constructs and a code formatter makes sure that the code you write has a homogenous style structure and abides by the formatting rules of a specific programming language (i.e. [PEP8](https://www.python.org/dev/peps/pep-0008/) for Python). When you're writing code, it's easy to miss a space, a tab, a colon, an opening or closing bracket, or to write code with bad and inconsistent styling. That's where linters and formatters will come in handy as they automate the task, they can be configured to run on saving and on commit, so that badly styled code never gets into production or into a public repo. The most popular choices are:

- [Eslint](https://eslint.org/)
- [Prettier](https://prettier.io/)

**CI/CD**

CI/CD stands for continuous integration / continuous deployment, they are a set of tools that allow you to create automatic processes that execute whenever a change is made to the codebase usually hosted on the cloud so that the production servers running your application get automatically updated with the newly pushed code. These actions can also modify and run tests on the code before it gets pushed into production, if tests fail the commit or update will not go through and collaborators will get notified of this. Once projects become bigger and they have big teams of contributors a solid CI/CD pipeline is very important so as to maximize the security and correctness of code being pushed into production. Examples of popular CI/CD tooling are:

- [GitHub Actions](https://github.com/features/actions)
- [CircleCi](https://circleci.com/)
- [Husky](https://typicode.github.io/husky/#/)

**Testing**

A key part of development is mitigating how many bugs are inside of your application. To ensure that the code behaves as it is intended to we write [unit tests](https://en.wikipedia.org/wiki/Unit_testing), [integration tests](https://en.wikipedia.org/wiki/Integration_testing) or even [end-to-end tests](https://www.browserstack.com/guide/end-to-end-testing). Each kind of test focuses on a different part of the application lifecycle. Modern tooling like Cypress allows you to simulate all possible states of your application and simulate user flows, you can even record user session tests as if you were recording a real user going through your website. In web3 you will also be doing integration tests for smart contract interaction. You can test smart contracts using libraries like [Foundry](https://github.com/gakonst/foundry), [Hardhat](https://hardhat.org/) or [Truffle](https://trufflesuite.com/). Most of these tests will be written by a smart contract or full-stack developer, however, as a frontend developer, you need to test how the interactions with the contracts will influence the flow of the user interface of your application. You can write various tests in JavaScript with ethers.js and couple it with Cypress to write complex tests. The web3 app development lifecycle usually goes from locally deployed smart contracts and front-end, to testnets (live network environment but with non-valuable assets), and to mainnet (not necessarily Ethereum mainnet, it can be an L2 like Arbitrum, a sidechain like Polygon PoS, etc). On the smart contract, side development teams hire external security auditors to verify that the contracts are secure to use, we will cover this in-depth in the [smart contract development section](#smart-contract-development). 

- [Cypress](https://www.cypress.io/)
- [Jest](https://jestjs.io/)
- [Mocha](https://mochajs.org/)

**ENS integration**

[ENS domains](https://ens.domains/) are human-readable domains for Ethereum addresses, the registrar for these domains is fully on-chain and the protocol is decentralizaed and governed by a DAO. ENS domains serve as an on-chain identity mechanism which many Ethereum users use to express themselves on-chain and to display information about themselves through ENS profile metadata containing contact information like email, Twitter, Discord or links to websites, a profile picture (NFT image metadata) and more. As a web3 front end developer you can tap into this registrar and display users' information once they've connected to your application with their web3 wallet.

The best way to get started with ENS is [their official documentation](https://docs.ens.domains/), here you can get a general understanding of the ENS protocol. For integrating ENS into your dapp, visit [this section](https://docs.ens.domains/dapp-developer-guide/ens-enabling-your-dapp). You need to perform 3 steps in order to support ENS within your application:

1. [Resolve ENS names](https://docs.ens.domains/dapp-developer-guide/resolving-names)
2. [Support reverse resolution](https://docs.ens.domains/dapp-developer-guide/resolving-names#reverse-resolution)
3. [Let users manage their ENS names](https://docs.ens.domains/dapp-developer-guide/managing-names)

If you are interested in how the on-chain parts of ENS work, check out the [smart contract development section](#smart-contract-development)

#### Further learning and development

By now you have learned a solid technology stack that can enable you to build all kinds of user interfaces for web3 apps. In order to really engrain these technologies, you need to build pet projects or join a team full-time, even if you only know a few of them you can join a team and get upscaled there as your learning will be supercharged by more experienced coworkers that will act as mentors most of the times. The front-end development landscape is constantly evolving new technologies will come and go, it is in your best interest to look at trends in the industry and try adapting them once they are a clear sign of them becoming adopted. You will keep improving your technology stack over time especially as you become more senior and you are able to reason why you want to use one tool over the other and how it fits into the needs of the applications that you are building. 

Build, Build, Build! Try creating small projects that implement ideas you come up with and practice the technologies you want to master. Also, don't be shy to ask questions to other web3 developers, and form learning groups with your friends, or other industry members.

Also, read over the [Getting a Job](#getting-a-job) and [Mastery](#mastery) sections of this guide to get more insight into soft skills which are useful to learn to grow as a developer.

### Smart contract development

Writing decentralized applications (Dapps) requires knowing how to write smart contracts as they are pieces of code that live on blockchains that can be executed inside of virtual machines. To write contracts you need to learn the programming languages that are able to compile to a target that the virtual machine can understand. In the case of the Ethereum blockchain, we have the EVM which has a set of operations it supports (a.k.a OPCODES). The most popular language for writing smart contracts on Ethereum is Solidity, which is a statically typed, object-oriented high-level programming language that takes inspiration from C++, Python, and JavaScript. With Solidity, you can program logic that executes inside of the EVM and the result of its operations is stored on the blockchain forever. The state of these applications is easily accessible from a full-node or from a third-party data indexing platform. The goal of smart contract developers is to create secure applications which perform a certain action, for example, a contract that allows for users to swap tokens, to buy and sell NFTs, to vote on proposals, etc. 

There are many different stages in the smart contract development stage, from experimentation, iteration, testing, auditing, testnet deployment, and mainnet deployments. There are also different sets of best practices that developers and production teams adopt in order to mitigate the security and economic risk of their applications. Another important part of writing smart contracts on Ethereum or Ethereum L2s is optimizing the contracts to minimize the amount of gas they consume. Since block space on Ethereum and L2s is limited, there needs to be a fee mechanism in order to avoid state bloat that gives a fixed gas price to each operation executed by the respective VM. That means that the more complex a smart contract is, the more expensive it will be to deploy and for the users to use. There are various design patterns that optimize the code to consume the least amount of gas possible, whilst remaining readable and secure. 

#### Solidity

Solidity is by far the most popular language to write smart contracts at the moment as the EVM is the most widely adopted virtual machine out there. Not only is it used in Ethereum's execution layer, but many alt L1s and L2s on Ethereum use the EVM as their virtual machine since there's a fairly mature development ecosystem. In order to first learn Solidity, we'll go over a few simple courses that explain the principles of the language, and as we progress further we will talk about design patterns, testing, security, oracles, and more. 

[CryptoZombies](https://cryptozombies.io/en/course/) is an interactive web application that teaches you the basics of Solidity through a fun development game. It teaches you how to create a contract, the data types that Solidity supports, how to write methods, how to manage objects, events, inheritance, memory management, interfaces, modifiers, and more. By the time you finish the first three short courses, you'll be able to read and write Solidity code. An alternative to CryptoZombies which is in video form is the [Solidity playlist](https://www.youtube.com/playlist?list=PLO5VPQH6OWdVQwpQfw9rZ67O6Pjfo6q-p) from [Smart Contract Programmer](https://www.youtube.com/channel/UCJWh7F3AFyQ_x01VKzr9eyA) on YouTube. This one is a bit better as it covers Solidity 0.8.0 which is a fairly recent version.

After we finish the course with the basics, we'll move on to building small projects implementing various different protocols, applications, and cryptographic primitives through the use of the [scaffold-eth](https://github.com/scaffold-eth/scaffold-eth) challenge that appear in [this thread](https://twitter.com/austingriffith/status/1483834810359377923?s=20&t=lkXzcAH2cT5xf7btyMAs0A). Scaffold-eth is a web3 development template built by [Austin Griffith](https://twitter.com/austingriffith) and open-source contributors which abstracts the backend of your app and creates a front-end interface for interacting with the smart contracts that you write. We will start with the [Ethereum Speed Run](https://speedrunethereum.com/
) challenges in the thread mentioned above, and continue with building more complex applications like a [signature-based multisig](https://github.com/scaffold-eth/scaffold-eth-examples/tree/meta-multi-sig), an [app that uploads images to IPFS](https://github.com/scaffold-eth/scaffold-eth/tree/image-upload-ipfs), and more.

Also a great way to learn solidty is to look through already written codes. For eg. https://solidity-by-example.org/

Now that you've been writing more and more complex smart contracts it is a good idea to start looking at other people's code to get a feel for how they implement different features, how they structure code, what designs and patterns they use, how they optimize for gas, and a lot more.

There are many techniques that you'll be picking up along on your journey in order to make your contracts more resource-effective and gas-optimized so that your users don't need to spend as much money for using your applications.

A good example of well-made smart contracts at the intermediate level are [Miguel Piedrafita](https://twitter.com/m1guelpf)'s [lil-web3](https://github.com/m1guelpf/lil-web3/tree/main/src) contracts. They are simple implementations of popular protocols and applications. They also have tests attached to them which are written using Foundry, which we will cover shortly. Take a look at how comments are written, how events and errors are used, how it is structured, gas minimization techniques he employs, try to understand the design of the protocol implementation, etc. Trying to implement your own versions of well-known applications and protocols is a great way to improve at Solidity as you'll learn a lot about the development process that you'll go through once you are writing production code at a company or DAO.

**Threads that talk about getting really good at Solidity**

- [Tips from Emilio Frangella @ Aave](https://twitter.com/The3D_/status/1485308693935763458?s=20&t=s2cbKFxvZ3tpjkFqcbyLfA)
- [Tips from @freddycoen](https://twitter.com/freddycoen/status/1485572733706682368)
- [Tips for non-beginners from @0xCacti](https://twitter.com/0xcacti/status/1485079302601207810?s=20&t=Iu2DlMREKnTAzGzifVZLMA)
- [Tips from @transmissions11](https://twitter.com/transmissions11/status/1485159010210770946?s=20&t=Iu2DlMREKnTAzGzifVZLMA)

Once you've gone through all of the above the best you can do to learn Advanced Solidity is to see what the best codebases look like. Look at how they structure their projects, what gas optimizations they use, what Solidity patterns they employ, how they do tests, how they create interfaces, how they handle events and errors, what libraries/dependencies do they use (if any), etc.

Examples of great codebases:
- [Uniswap v2](https://github.com/Uniswap/v2-core) / [Uniswap v3](https://github.com/Uniswap/v3-core)
- [Gnosis Safe](https://github.com/gnosis/safe-contracts)
- [Compound finance](https://github.com/compound-finance/compound-protocol)
- [Zora v3](https://github.com/ourzora/v3)
- [Rari Capital](https://github.com/Rari-Capital/vaults)
- [Ribbon Finance](https://github.com/ribbon-finance/ribbon-v2/tree/master/contracts)
- [AAVE](https://github.com/aave/aave-protocol)
- [SushiSwap](https://github.com/sushiswap/sushiswap)

#### Testing

Testing smart contracts is an essential part of the development process as it ensures that the code you write behaves as intended and is secure against various technical and economic exploits. Many different libraries are used by different teams, there are pros and cons to using each different library and in some cases, they can be used in a complementary fashion. We will cover the most popular ones among top-tier developers as well as the most commonly used ones like HardHat and Truffle.

Opinionated recommendations: Foundry and Hardhat

**Foundry**

[Foundry](https://github.com/gakonst/foundry) is the hottest library in the Ethereum development landscape, it is originally built by Georgios Konstantopoulos who is one of the most highly respected developers in the entire Ethereum ecosystem. Georgios is currently the CTO at Paradigm and part of his job is building tools for developers that will be used to create the applications of the future.

Foundry is composed of two parts: Forge and Cast. 
- **Forge:** Forge is a fast and flexible Ethereum testing framework, inspired by Dapptools.
- **Cast:** Swiss army knife for interacting with EVM smart contracts, sending transactions, and getting chain data.

The library is written in Rust, which is a systems-level programming language that has memory safety, borrow checking, performant concurrency, and many other features which are making it one of the favorite languages used by developers across all fronts. Many popular libraries are being written in Rust, popular compiler targets like WASM are supported by Rust, a lot of Ethereum developer tooling is built using Rust or is refactoring their infrastructure to use Rust. It is a very exciting trend in blockchain development and many developers are learning the language to be able to contribute to these cool pieces of software. The best way to get started with Rust is [The Rust Book](https://doc.rust-lang.org/book/) and the [Rustlings repo](https://github.com/rust-lang/rustlings/).

The reason why Foundry is getting a lot of popularity and it is so important, is because Solidity tests should be written in Solidity and not in JavaScript. It is very hard to master two different languages at once and Solidity developers shouldn't be forced to learn it in order to be able to test their smart contracts. Foundry is also getting an increasingly superior development environment in terms of features. The main features for which you might use other toolkits are mainly deployment which is not supported by Foundry so far. For managing deployments, the standard toolkit is HardHat. For testing, gas optimization features, fuzzing, symbolic execution (hevm), etc, do use Foundry. Good resources for learning and mastering Foundry are:
- [The Foundry Book](https://onbjerg.github.io/foundry-book/) - Community sourced documentation
- [Tweet from @andreasbigger](https://twitter.com/andreasbigger/status/1500209878433894400?s=20&t=5HKeV0q_h3Z3QoRvlkO_hQ):
  - Familiarize yourself w/ [Forge-cli](https://github.com/gakonst/foundry/blob/master/cli/README.md)
  - Checkout some templates:
    - [FrankieIsLost forge template](https://github.com/FrankieIsLost/forge-template)
    - [ZeframLou forge template](https://github.com/ZeframLou/foundry-template)
    - [AndreasBigger femplate](https://github.com/abigger87/femplate)
  - Dive into repos using Foundry:
    - [lil-web3](https://github.com/m1guelpf/lil-web3/)
    - [n3rp](https://github.com/GrantStenger/n3rp)
    - [zen](https://github.com/zkSoju/zen)
    - [cloaks](https://github.com/abigger87/cloaks)
    - [ethernaut-x-foundry](https://github.com/ciaranmcveigh5/ethernaut-x-foundry)
    - [damn-vulnerable-defi-foundry](https://github.com/nicolasgarcia214/damn-vulnerable-defi-foundry)
    - [Multicall](https://github.com/mds1/multicall)
  - [Brockelmore's testing verbosity with forge-std](https://github.com/brockelmore/forge-std)

**HardHat**

[Hardhat](https://hardhat.org/) is the Ethereum development library that’s the most widely used across the ecosystem and is the standard in most production codebases like Aave, Uniswap, and many others. Usually, all the deploy scripts, migration files, automation scripts, etc are written using Hardhat and their tooling suite. It is a javascript library (that has Typescript support). Recently the Hardhat team announced that they are moving their infrastructure to Rust as most of the tooling ecosystem is moving to use it do its performance and security.


**Dapptools**

[Dapptools](https://github.com/dapphub/dapptools)  is a suite of Ethereum focused CLI tools following the Unix design philosophy, favoring composability, configurability, and extensibility.

There are 4 key elements in Dapptools:
- **dapp** - All you need Ethereum development tool. Build, test, fuzz, formally verify, debug & deploy solidity contracts.
- **seth** - Ethereum CLI. Query contracts, send transactions, follow logs, slice & dice data.
- **hevm** - Testing-oriented EVM implementation. Debug, fuzz, or symbolically execute code against local or mainnet state.
- **ethsign** - Sign Ethereum transactions from a local Keystore or hardware wallet.

A cool innovation done by app tools was the hEVM which is an EVM implementation written in Haskell (a functional programming language) that allows to symbolically execute Solidity code and formally verify the results of the resulting bytecode (opcode operations). This feature was later adopted by Foundry, including many others that were first provided by Dapptools.


**Truffle Suite**

[Truffle Suite](https://trufflesuite.com/) is a suite of tools developed by Consensys to locally test smart contracts by deploying them on a local instance of the Ethereum blockchain, mocking user addresses using the Ganache library, writing tests using Truffle, and creating on-chain data pipelines for user interfaces using Drizzle. It was one of the first complete Ethereum developer tooling ecosystems that were released, but they’ve fallen out of favor in recent years as libraries like Hardhat overtook it.

#### Design patterns

Once you're comfortable with writing more and more complex contracts and maybe taking a look at the front-end code and it interacts with the smart contracts, you'll start getting a feel for how smart contracts are designed from a more high-level view. There are certain designs and patterns which are commonplace, things like the approved pattern for tokens, and more. At this point, it is a good idea to start thinking more about the overall architecture of your code and the structure that it will take to efficiently implement the functionality you want to enable.

There are common patterns employed in smart contract development, this [Solidty-patterns](https://github.com/fravoll/solidity-patterns) repo implements some of them.

Since the EVM is such a constrained environment where each additional operation executed by the EVM adds gas costs to the execution of the smart contract, developers try to build as least resource-intensive contracts as possible whilst also maximizing readability and security. Since blockchains are a very adversarial environment were mistakes in a smart contract could lead to fund drains (RUGS) and exploits, it can be considered mission-critical software and so many developers get inspiration from other mission-critical software guidelines like the ones of NASA which are responsible for the lives of astronauts going to space. These development principles are guidelines that help optimize a codebase for maximum security through the adoption of a standardized procedure and developer mindset.

**ENS integration**

We mentioned how to integrate ENS domain names into your dapp within the [front end development section](#front-end-development), but as a smart contract developer you can also [resolve ENS domain names on-chain](https://docs.ens.domains/contract-developer-guide/resolving-names-on-chain), [write your own resolver](https://docs.ens.domains/contract-developer-guide/writing-a-resolver) which implements [EIP137](https://github.com/ethereum/EIPs/issues/137) or even [write your own registrar](https://docs.ens.domains/contract-developer-guide/writing-a-registrar).

#### Specialized languages

There are various programming languages that can be compiled into EVM bytecode, there are high-level programming languages such as Solidity, Vyper, or Fe, but there's also an intermediate programming language that's often used within gas-optimized contracts called Yul, or as a developer, you can write EVM assembly by writing the EVM opcodes directly. A common technique for gas minimization is writing Solidity code looking at the resulting EVM assembly code and comparing the gas cost of different implementations in order to make the contract as gas-efficient as possible.

- **Yul**

[Yul](https://docs.soliditylang.org/en/v0.8.12/yul.html) is an intermediate-level programming language that can compile into EVM bytecode. From the Solidity documentation: 

"The design of Yul tries to achieve several goals:

- Programs written in Yul should be readable, even if the code is generated by a compiler from Solidity or another high-level language.

- Control flow should be easy to understand to help in manual inspection, formal verification, and optimization.

- The translation from Yul to bytecode should be as straightforward as possible.

- Yul should be suitable for whole-program optimization.

In order to achieve the first and second goals, Yul provides high-level constructs like `for` loops, `if` and `switch` statements and function calls. These should be sufficient for adequately representing the control flow for assembly programs. Therefore, no explicit statements for `SWAP`, `DUP`, `JUMPDEST`, `JUMP` and `JUMPI` are provided, because the first two obfuscate the data flow and the last two obfuscate control flow. Furthermore, functional statements of the form `mul(add(x, y), 7)` are preferred over pure opcode statements like `7 y x add mul` because, in the first form, it is much easier to see which operand is used for which opcode."

- **EVM Assembly**

[EVM Assembly](https://docs.soliditylang.org/en/v0.8.12/assembly.html) can be written inside of inline Solidity statements with the `assembly` keyword. It allows for more fine-grained control over the resulting bytecode. Oftentimes the compiler is unable to optimize Solidity code well and so it results in unnecessary gas costs.

There's also an `unchecked` keyword in Solidity which disables the overflow and underflow checks from the compiler which were introduced in Solidity 0.8.0 and before were part of the SafeMath library in OpenZeppelin libraries. The `unchecked` keyword is oftentimes used 

Writing Yul or inline assembly can obfuscate the functionality of your code by making it less readable for other contributors/auditors and it can potentially introduce new risks as the Solidity compiler oftentimes performs various optimizations and security checks.  

Good toolkits for writing EVM Assembly:
- [etk](https://github.com/quilt/etk)
- [huffc](https://github.com/JetJadeja/huffc)
- and the afforementioned Yul intermediate language

#### EVM deep dive

Understanding the ins and outs of the EVM is crucial for building highly optimized applications as each operation executed by the EVM has a gas cost attached to it and users have to pay the price for executing functions within the applications that they use. There is a compromise between readability and code optimizations however, which needs to be taken into consideration. Sometimes using techniques like bitshifting and bitmapping ([Hacker's Delight](https://github.com/lancetw/ebook-1/blob/master/02_algorithm/Hacker's%20Delight%202nd%20Edition.pdf) is a good book that talks about bit manipulation techniques in detail) can have a negative impact on readability and thus security, as other contributors and auditors may not be able to wrap their heads around these complex optimizations or it would simply take too much time for them to do so. For code that actually goes into production, each project needs to asses how much do they want to optimize their code for gas savings  over readability. Security usually comes first, however there are still a set of well-known good practices that will allow you to save some gas. If you end up using gas optimization techniques it is also advised to document them well with comments inside of your Solidity contracts. Another important point is that as these technologies scale and developers are less constrained by the virtual machine executing smart contract bytecode, the needs for optimizations becomes less important along with the fact that the compilers converting static code to machine code are getting better and better at optimizing code for performance and low costs. As technologies like L2s and data availability layers become mainstream we also may see an emergence of new VM architectures that experiment with new designs that do not require developers to work with low-level optimizations as they will be highly performant and scalable.

For a comprehensive EVM deepdive, I suggest these resources:
- [EVM development starter kit](https://freddycoen.medium.com/evm-starter-kit-1790bcc992ef)
- Read Chapter 13 (EVM) of [The Ethereum Book](https://github.com/ethereumbook/ethereumbook/blob/develop/13evm.asciidoc)
- Read Femboy Capital's [Playdate with the EVM](https://femboy.capital/evm-pt1)
- Go over OpenZeppelin's series on [Deconstructing smart contracts](https://blog.openzeppelin.com/deconstructing-a-solidity-contract-part-i-introduction-832efd2d7737/)
- Read [Analyzing smart contracts](https://costa.fdi.ucm.es/papers/costa/AlbertCGRR20bTR.pdf) by Elvira Albert (very math heavy)
- Read over [TakeNobu's slides on how the EVM works (visualized)](https://takenobu-hs.github.io/downloads/ethereum_evm_illustrated.pdf)
- Go over [design patterns section](#design-patterns)
- Go over the exemplary good codebases at the beginning of the [Solidity section](#solidity)
- Follow gas optimizoors like [@transmission11](https://twitter.com/transmissions11) for gas alpha
- Get used to going to lookup gas costs for different OPCODE operations at [EVM Codes](https://www.evm.codes/)
- Check out the [EVM execution specs](https://github.com/ethereum/execution-specs)
- Learn to use [Foundry](#testing) well
- Bonus resources in comments of [this Twitter thread](https://twitter.com/0x_doggie/status/1494025503446945799?s=20&t=jydW6zat0cCXAb3mUhPFWw)

Special thanks to [@0x_doggie] and [@freddycoen] from whose threads I extrapolated these resources. - [Thread 1](https://twitter.com/freddycoen/status/1485572733706682368) 
- [Thread 2](https://twitter.com/0x_doggie/status/1496507944803848194)

You might wanna go through [Nick's Posts](https://ethereum.stackexchange.com/users/1254/nick-johnson) and [Jean's Solidity articles](https://jeancvllr.medium.com/solidity-tutorial-all-about-assembly-5acdfefde05c)


### Backend development

As far as blockchain development goes, most of the logic that traditional applications would consider backend is encapsulated within smart contracts, however, there are also complementary technologies that allow you to query data from blockchains, index the data, create databases so that you have on-demand data from custom APIs, decentralized storage for content, user authentication / DID, etc. I wouldn't consider this its own specialization, but it is a sufficiently unique skill set for me to cover it separately. 

This image was created by my fren [Nader Dabit](https://twitter.com/dabit3) who is a full-stack blockchain developer that has created many useful guides, some of which I'll feature in the full-stack development section. This web3 stack landscape graphic comes from a recent blog post of his called [The complete guide to full-stack web3 development](https://dev.to/dabit3/the-complete-guide-to-full-stack-web3-development-4g74).

![web3 stack.png](./images/web3_stack.jpeg)

#### Decentralized File Storage

There are many applications that require storing files of all sorts and making them available for your decentralized applications, NFTS for example only have a link to the URI metadata on-chain, and that URI points to a decentralized storage endpoint on IPFS or Arweave. Meaning that all the images and the traits of the NFT are hosted in their file storage networks rather than on the Ethereum mainnet in order to save on costs and allow for higher bandwidth. 

**IPFS**

[IPFS](https://ipfs.io/) is one of the most popular decentralized file storage solutions out there, there are projects like [Filecoin](https://filecoin.io/) being built on top and many NFT metadata are hosted inside of the network. There are solutions like [NFT Storage](https://nft.storage/docs/) that make the metadata hosting completely free to upload your NFT metadata on-chain by leveraging their Javascript API.

**Arweave**

[Arweave](https://www.arweave.org/) is another such solution. Arweave is a type of storage that backs data with sustainable and perpetual endowments, allowing users and developers to truly store data forever – for the very first time. As a collectively owned hard drive that never forgets, Arweave allows developers to remember and preserve valuable information, apps, and history indefinitely.

An increasingly popular use case of decentralized file storage solutions is web hosting, since we are on a quest to build decentralized applications that are uncensorable, it is good practice to also decentralize the user interface by deploying it on decentralized file storage networks like IPFS and Arweave. This prevents the applications you built from being censored by centralized entities shutting down your deployments on centralized platforms like Vercel, AWS, Azure, or any other. Part of good practices of modern applications is open-sourcing the front end of their applications so that anyone can run them locally and also deploying several other instances to decentralized file storage solutions as well as usually hosting their own front end in a centralized server for added performance.

#### Indexing / Querying

The applications you will be building need to know what is the state of the blockchain so that your users know what is happening and can interact with the application effectively. An example of this is Uniswap's AMM. In order to call the swap function in the smart contracts, you need to know how many tokens you will get back with an X amount of ETH that you put into the contract. In order to display the current price of any asset, your application will either query data from the blockchain directly or it will use an indexing service that has that data already available. These APIs are very useful and are a critical part of any application.

**TheGraph**

A very popular service is [TheGraph](https://thegraph.com/en/). TheGraph is a decentralized indexing protocol that allows you to query networks like Ethereum, the protocol has an incentive layer that rewards indexers to create APIs for the data you specify. Developers can create so-called subgraphs, which are data APIs that make the data easily accessible through a GraphQL schema. GraphQL is a querying language that is used as an alternative to traditional REST APIs. GraphQL schemas are harder to set up initially, but in turn, they enjoy massive scalability. In order to learn more, check out [their documentation](https://thegraph.com/docs/en/). To learn how GraphQL works checkout the [official documentation](https://graphql.org/learn/), [HowToGraphQL](https://www.howtographql.com/) and [this YouTube playlist](https://www.youtube.com/watch?v=Y0lDGjwRYKw&list=PL4cUxeGkcC9iK6Qhn-QLcXCXPQUov1U7f&ab_channel=TheNetNinja) (although it may be a bit outdated by now, better check the documentation).

**CovalentHQ**

An upcoming service and simpler alternative to TheGraph is [Covalent](https://www.covalenthq.com/). Its API allows you to pull detailed, historical and granular data from multiple blockchains with no code. It has a rich palette of endpoints serving data from categories including balances, NFTs, and DeFi. The APIs provide data for several different blockchains like Ethereum, Polygon, Avalanche and is currently free to use. In order to learn more, check out [their documentation](https://www.covalenthq.com/docs/) and [API docs](https://www.covalenthq.com/docs/api/#/0/0/USD/1). They have an active [youtube channel](https://www.youtube.com/channel/UCGn-T9qPiXAx490Wr6WPbOw) as well with a [playlist on building web3 projects](https://www.youtube.com/playlist?list=PL4d9xIzK1us3vqIFYqcS005qSVuq_AESa) using Covalent.

**Nodes**

One of the most common ways to query data from the blockchain is by calling RPC endpoints of nodes that are syncing the full-state of the blockchain. A node runs the Ethereum blockchain, has all of its state, and syncs periodically every single time a new block appears. You can run your own node on consumer hardware, but it is unscalable if you want to use those nodes for querying data for massive applications as you'd need to build your own DevOps pipelines in order to scale to your needs accordingly. That's why most developers use a third-party node provider like [Alchemy](https://www.alchemy.com/) or [Infura](https://infura.io/). You can call these APIs by using web3 libraries like [ethers.js](https://docs.ethers.io/v5/), [web3.js](https://web3js.readthedocs.io/en/v1.7.0/) or myriad others.

**Moralis**

[Moralis](https://moralis.io/) is a web3 development platform that automates your backend, instead of having to query data from nodes, indexing the data, and creating databases so that you don't need to query the blockchain on every user request, Moralis does it for you. You instantiate a Moralis server that exposes an API to all blockchain data through a REST API to a PostgreSQL database. It also has smart contract alerts, cloud functions, cross-chain user authentication, and more. The only downside of using Moralis is that it's a centralized service provider. It is the easiest way to get a backend for your Dapp going as Moralis has a very simple to use SDK that helps you tap into the APIs offered by their services. It is a great way to get started building backends as most of the heavy lifting is done for you.

To learn how to use Moralis checkout [their documentation](https://docs.moralis.io/introduction/readme) and [their YouTube channel](https://www.youtube.com/channel/UCgWS9Q3P5AxCWyQLT2kQhBw).

**Thirdweb** 

[Thirdweb](https://thirdweb.com/) provide smart contracts, SDKs and UI components that creators, game studios and developers can integrate into their app
To learn how to use Thirdweb checkout [their documentation](https://portal.thirdweb.com/)

#### Oracles

Oracles are data feeds that bring off-chain data on-chain so that the smart contracts that you build can query real-world information and build logic around it. For example, prediction market Dapps use oracles to settle payments based on events. A prediction market may ask you to bet your ETH on who will become the next president of the United States. They'll use an oracle to confirm the outcome and payout to the winners.

- [What is an oracle? - Chainlink](https://youtu.be/ZJfkNzyO7-U?t=10)

[Chainlink](https://chain.link/) is the most popular oracle out there, you'll usually use it to get price feeds, to get verifiable randomness, to call external APIs, etc. If you want to get started building with Chainlink, go to [their documentation](https://docs.chain.link/).

#### DID / Authentication

DID (decentralized identity) and web3 user authentication are a disruptive new primitive on the internet as we can be self-sovereign users of the internet and own our own value within it for the first time in human history. Usually, your user profile is managed by centralized service providers like Google, Facebook, Apple, Amazon, and others. In web3, the concept of a digital identity is much broader as it can span many more different areas such as financial history, games, social interaction (decentralized social media, i.e. [Lens Protocol](https://github.com/aave/lens-protocol)), and much more. It is still not clear how web3 user management will look like a few years from now, but there are a few solutions that are being standardized and are emerging as potential winners.

**SpruceID**

[SpruceID](https://www.spruceid.com/) is a decentralized identity toolkit that allows users to sign and verify W3v verifiable credentials which are configurable across many interfaces. Use cases cited in the [SpruceID documentation](https://spruceid.dev/docs/) include: Authenticity for NFT creators, decentralized backup or recovery of decentralized identity, decentralized on-boarding for private DeFi pools, decentralized app-hosting, and many more potential use cases in the future. In order to integrate the Spruce DID solutions visit their developer portal. 

**Sign-in with Ethereum**

[Sign-in with Ethereum](https://login.xyz) is an initiative that came off [EIP-4361](https://eips.ethereum.org/EIPS/eip-4361) which set off to standardize how Ethereum accounts interact and authenticate with off-chain services by signing a standard message format parameterized by scope, session details, and security mechanisms (e.g., a nonce). The goals of this specification are to provide a self-custodied alternative to centralized identity providers, improve interoperability across off-chain services for Ethereum-based authentication, and provide wallet vendors a consistent machine-readable message format to achieve improved user experiences and consent management. 

Many application builders have already adopted this signature standard for building applications on Ethereum as it streamlines the process for everyone and makes it more seamless for users since they have easily readable signatures from [EIP-191](https://eips.ethereum.org/EIPS/eip-191). The aim of this EIP specification is to create a login standard similar to how web2 login with Google and Facebook became catalysts for adoption.

#### Automation

Within blockchain applications there are many actions that are repetitive and cumbersome to execute, for example, having to change the liquidity provision ranges inside of an active Uniswap v3 liquidity provision strategy, claiming rewards from yield vaults, and many other actions that users would like to automate so as to not have to deal with manual execution overhead.

**Gelato network**

[Gelato Network](https://www.gelato.network) is an automation protocol that runs as a decentralized network of bots used by web3 developers to automate smart contract executions on public EVM compatible blockchains including Ethereum, Polygon, Fantom, Arbitrum, Binance Smart Chain, and Avalanche.

In order to get started automating tasks inside of your application check out the [official Gelato documentation](https://docs.gelato.network/guides/tutorial) which has tutorials on how to set up bots to regularly execute any given task in exchange for a small transaction fee.
The setup inside of the contract function that you want bots to run would look something like this:

![gelato.png](./images/gelato.png)

#### Miscellaneous APIs

When building applications you will want to display miscellaneous information from various different other applications or protocols, e.g. price feeds for different tokens on different AMMs, the price of NFTs listed on different marketplaces, various data from services your application relies on, etc. As a backend developer, your responsibilities are to know where you can find reliable sources of data for your application and build the infrastructure needed to fetch it so that frontend developers can display it on the site. It is also important to build redundancy of the data you query and store it in your own databases in order to prevent your application from failing in the case of API dependency failure.

**Opensea**
A good example of such an API is [OpenSea’s API](https://docs.opensea.io/reference/api-overview) which is public and can be queried in order to get the prices of NFT listings OpenSea, get floor prices, volumes, a bunch of other prices historical data, NFT metadata, and more.

As a developer, you can also create your own databases and API endpoints to fetch data from those databases. It is also a good way to earn revenue, by creating SaaS services around API keys with rate limits for how much data anyone can query off your servers. For building APIs you can for example use a REST API infrastructure with NodeJS and PostgreSQL, or for example, you can write a TheGraph subgraph.

### Full-stack blockchain development

As the name implies, full-stack blockchain development is the closest specialization to being a jack of all trades. It involves building out all of the aspects of an application from front end, to smart contracts, to backend (at least to a certain degree). This is the most generic role that most blockchain developers will take and most companies and DAOs are looking for in a contributor. Since there is such a high demand for quality developers in the space, it is oftentimes the case that employers onboard people from different fields and turn them into a jack of all trades within web3 development so as to save costs and reduce HR resource requirements (which are incredibly scarce nowadays).

Since rewriting the [front end](#front-end-development), [back end](#back-end-development) and [smart contract](#smart-contract-development) sections would be pointless, I'll dedicate this section just to list a bunch of full-stack guides, tips and tricks, deployment guidelines, project management, and other relevant information.

#### Full-stack guides

- [Introduction to Ethereum Development](https://www.youtube.com/watch?v=MlJPjJQZtC8) - [Austin Griffith](https://twitter.com/austingriffith)
- [The Complete Guide to Full Stack Web3 Development](https://dev.to/dabit3/the-complete-guide-to-full-stack-web3-development-4g74) - [Nader Dabit](https://twitter.com/dabit3)
- [Speed Run Ethereum](https://speedrunethereum.com/) - [Austin Griffith](https://twitter.com/austingriffith)
- [Solidity, Blockchain, and Smart Contracts Course - Beginner to Expert Python Tutorial](https://www.youtube.com/watch?v=M576WGiDBdQ) - [Patrick Collins](https://twitter.com/PatrickAlphaC)
- [Full-stack blockchain solidity course](https://github.com/smartcontractkit/full-blockchain-solidity-course-py) - [Patrick Collins](https://twitter.com/PatrickAlphaC)

#### Full-stack tutorials

- [Introduction to Ethereum](https://www.youtube.com/watch?v=MlJPjJQZtC8)
- [Build Uniswap Blockchain Web3 App with Solidity | Next.js | Sanity.io](https://www.youtube.com/watch?v=xXxjRzdYIss)

#### Building and deploying on L2s and DA layers

Coming soon

#### Optimism

- [Developer docs](https://community.optimism.io/docs/developers/)
- [New Bedrock protocol specs](https://github.com/ethereum-optimism/optimistic-specs/)

#### Arbitrum

- [Developer docs](https://developer.offchainlabs.com/docs/developer_quickstart)
- [Protocol description](https://developer.offchainlabs.com/docs/rollup_protocol)

#### zkSync

- [Developer docs](https://docs.zksync.io/dev/)
- [New 2.0 docs](https://v2-docs.zksync.io/dev/)

#### Starknet / StarkEx

- [StarkNet / Cairo docs](https://starknet.io/docs/)

### Core protocol development

#### General Learning

There are many topics to learn about in core-development, one can specialize in any area. Here is a selection of learning-resources 
Basic:
- Merkle trees:
  - [Ethereum execution-layer Merkle Patricia Tree walkthrough](https://dzone.com/articles/ethereum-yellow-paper-walkthrough-27)
- [Execution and Consensus layer Merge design](https://www.youtube.com/watch?v=8N10a1EBhBc), video by Danny Ryan
- [Rollup centric roadmap](https://ethereum-magicians.org/t/a-rollup-centric-ethereum-roadmap/4698), post by Vitalik
- Ethereum protocol ELI5 (coming soon)

Medium:
- [Yellow Paper](https://ethereum.github.io/yellowpaper/paper.pdf): L1 protocol specification in paper form
- [ABI: Application Binary Interface](https://docs.soliditylang.org/en/v0.8.11/abi-spec.html) to interact with contracts
- [EVM opcodes](https://www.evm.codes/): interactive reference
- [RLP](https://eth.wiki/fundamentals/rlp): the encoding used everywhere in execution-layer
- [SSZ specs](https://github.com/ethereum/consensus-specs/blob/dev/ssz/simple-serialize.md): encoding and merkleization of Eth2,
  also see [visualized encoding](https://github.com/protolambda/eth2-docs/blob/master/eth2-ssz.svg) 
  and [visualized hash-tree-root](https://github.com/protolambda/eth2-docs/blob/master/eth2-htr.svg).
- [EVM](https://ethereum.org/en/developers/docs/evm/): overview of the machine that runs smart-contracts
- Executable specs: readability-first python implementations of the protocol specification.
  - [Consensus-layer](https://github.com/ethereum/consensus-specs), also see [pip package](https://pypi.org/project/eth2spec/)
  - [Execution-layer](https://github.com/ethereum/execution-specs), also see the [rendered version](https://ethereum.github.io/execution-specs/).
- [Simplified Eth2 Phase0 specs intro](https://notes.ethereum.org/@djrtwo/Bkn3zpwxB)
- [Light client design](https://www.youtube.com/watch?v=ysW-Bq05pJQ) and [implementation](https://www.youtube.com/watch?v=bX8I9U2PYMk)

Advanced:
- Builder proposer separation:
  - [Proposer/block builder separation-friendly fee market designs](https://ethresear.ch/t/proposer-block-builder-separation-friendly-fee-market-designs/9725)
  - [Flashbots: frontrunning the MEV crisis](https://ethresear.ch/t/flashbots-frontrunning-the-mev-crisis/8251)
  - [state of research](https://notes.ethereum.org/@vbuterin/pbs_censorship_resistance) and 
- [Fork-choice Gasper paper: Combining GHOST and Casper](https://arxiv.org/abs/2003.03052)
- [Dagger-Hashimoto (legacy PoW)](https://eth.wiki/concepts/dagger-hashimoto)
- State DB design, Erigon docs:
  - [Choice of storage engine](https://github.com/ledgerwatch/erigon/wiki/Choice-of-storage-engine)
  - [State representation](https://github.com/ledgerwatch/erigon/blob/devel/docs/programmers_guide/guide.md)
- BLS:
  - [Signature aggregation in eth2](https://ethresear.ch/t/pragmatic-signature-aggregation-with-bls/2105) by Justin Drake
  - [BLS12-381 For The Rest Of Us](https://hackmd.io/@benjaminion/bls12-381) by Ben Edgington
  - [BLS Signature for Busy People](https://gist.github.com/paulmillr/18b802ad219b1aee34d773d08ec26ca2) by Paul Miller
- KZG:
  - [KZG polynomial commitments](https://dankradfeist.de/ethereum/2020/06/16/kate-polynomial-commitments.html) by Dankrad Feist
  - [ZK Study Club part 1: polynomial commitments](https://www.youtube.com/watch?v=bz16BURH_u8) by ZK FM podcast with Justin Drake
- ZK:
  - [ZK study club playlist](https://www.youtube.com/watch?v=Pnc9J7uQgqs&list=PLj80z0cJm8QHm_9BdZ1BqcGbgE-BEn-3Y) by ZK FM podcast
- Fraud proofs (optimistic rollup tech):
  - [The State of Optimistic Rollup](https://medium.com/molochdao/the-state-of-optimistic-rollup-8ade537a2d0f) older overview by Daniel Goldman
  - [Inside Arbitrum](https://developer.offchainlabs.com/docs/inside_arbitrum) arbitrum fraud proof
  - [Cannon](https://medium.com/ethereum-optimism/cannon-cannon-cannon-introducing-cannon-4ce0d9245a03) optimism fraud proof
- [LibP2P](https://docs.libp2p.io/): the network layer in Eth2, Polkadot, Filecoin and other blockchains.
- [DevP2P](https://github.com/ethereum/devp2p/): the original network layer in Eth1 / execution-layer of ethereum.
- [Whisk: A practical shuffle-based SSLE protocol for Ethereum](https://ethresear.ch/t/whisk-a-practical-shuffle-based-ssle-protocol-for-ethereum/11763)
- [VDF research](https://vdfresearch.org/): verifiable delay function for ethereum and other protocols
- Data Availability Sampling (DAS):
  - [DAS in practice](https://notes.ethereum.org/@vbuterin/r1v8VCULP)
  - [DAS in full sharding design](https://hackmd.io/@vbuterin/sharding_proposal)

#### L2

Layer-2 scales Layer-1 by increasing capacity without significantly changing the security assumptions of the Layer-2.
Although this does not change L1 itself, it does influence the general scaling design direction,
generally pushing ethereum into a [rollup-centric roadmap](https://ethereum-magicians.org/t/a-rollup-centric-ethereum-roadmap/4698).

Domains:
- Side-chains: [EthHub](https://docs.ethhub.io/ethereum-roadmap/layer-2-scaling/sidechains/), [eth org](https://ethereum.org/en/developers/docs/scaling/sidechains/)
- State channels: [EthHub](https://docs.ethhub.io/ethereum-roadmap/layer-2-scaling/state-channels/), [eth org](https://ethereum.org/en/developers/docs/scaling/state-channels/)
- Plasma (mostly deprecated): [EthHub](https://docs.ethhub.io/ethereum-roadmap/layer-2-scaling/plasma/), [eth org](https://ethereum.org/en/developers/docs/scaling/plasma/)
- Rollups [intro by Polynya](https://polynya.medium.com/rollups-data-availability-layers-modular-blockchains-introductory-meta-post-5a1e7a60119d)
  - ZK rollups (ZKRUs): [EthHub](https://docs.ethhub.io/ethereum-roadmap/layer-2-scaling/zk-rollups/), [eth org](https://ethereum.org/en/developers/docs/scaling/zk-rollups)
  - Optimistic rollups (ORUs): [EthHub](https://docs.ethhub.io/ethereum-roadmap/layer-2-scaling/optimistic_rollups/), [eth org](https://ethereum.org/en/developers/docs/scaling/optimistic-rollups/)
- Bridges: [eth org intro](https://ethereum.org/en/bridges/)
- L3 / validiums / volitations etc:
  - [starkware L3](https://medium.com/starkware/fractal-scaling-from-l2-to-l3-7fe238ecfb4f)
  - [Validium eth org intro](https://ethereum.org/en/developers/docs/scaling/validium/)

Refer to [L2beat.com](https://l2beat.com/) for an overview of active L2 scaling solutions.


#### L1

Domains:
- Eth1 / execution layer
  - Networking: devp2p
  - EVM
  - Tx pool
  - Sync methods (Fast, Snap, Archive, Beam, Light)
  - State DB
  - User-facing (JSON RPC, tx tracing, etc.)
- Eth2 / consensus layer
  - Networking: libp2p
  - Fork-choice
  - Attestations / BLS aggregation
  - Staking / Validator clients
  - Slashings
  - Sharding

##### News

Selection of protocol news resources:
- [Week in Ethereum](https://weekinethereumnews.com/): OG weekly news letter
- [Eth2.News](https://eth2.news): eth2 news by Ben Edgington

#### Communication

- [Discord Eth R&D server](https://discord.gg/EyK6HmMcmy)
- [Eth magicians](https://ethereum-magicians.org/), forum for governance / protocol discussion
- [Eth research](https://ethresear.ch/), forum for research discussion
- AllCoreDevs (ACD): [discord channel in R&D](https://discord.gg/S6r6RcWPC3)
- Ethereum Foundation [youtube channel](https://www.youtube.com/c/EthereumFoundation) (streams ACD and Consensus calls)

#### L1 Specifications

##### Execution layer

- [Ethereum Improvement Proposals: EIPs](https://eips.ethereum.org/)
- [Execution APIs](https://github.com/ethereum/execution-apis/)
- [New Execution py-specs](https://github.com/ethereum/execution-specs)


##### Consensus layer

- [Consensus specs](https://github.com/ethereum/consensus-specs)
- [Beacon APIs](https://github.com/ethereum/beacon-APIs), also see [interactive site](https://ethereum.github.io/beacon-APIs/)
- [Annotated specs](https://github.com/ethereum/annotated-spec) by Vitalik Buterin
- [Eth2 book](https://eth2book.info/altair/contents): extended annotated specs with some eth2 history, by Ben Edgington
- Legacy (but good) resources:
  - [Proof Of Stake F.A.Q.](https://eth.wiki/en/concepts/proof-of-stake-faqs)
  - [Sharding F.A.Q.](https://eth.wiki/sharding/Sharding-FAQs)
  - [Ethereum sharding research compendium](https://notes.ethereum.org/@serenity/H1PGqDhpm?type=view)


#### Ethereum core teams

Client teams (those that are open-source), in no particular order:

| Domain      | Project                                                                                                      | Language      | Discord                                                                    | Docs                                                               |
|-------------|--------------------------------------------------------------------------------------------------------------|---------------|----------------------------------------------------------------------------|--------------------------------------------------------------------|
| Eth2        | [Prysm](https://github.com/prysmaticlabs/prysm)                                                              | Go            | [invite](https://discord.gg/fbHjSdy)                                       | [docs](https://docs.prylabs.network/docs/getting-started/)         |
| Eth2        | [Lighthouse](https://github.com/sigp/lighthouse)                                                             | Rust          | [invite](https://discord.gg/uC7TuaH)                                       | [docs](https://lighthouse-book.sigmaprime.io/)                     |
| Eth2        | [Lodestar](https://github.com/ChainSafe/lodestar)                                                            | Typescript    | [invite](https://discord.gg/Quv3nJX)                                       | [docs](https://chainsafe.github.io/lodestar/)                      |
| Eth1 + Eth2 | Nimbus [eth2](https://github.com/status-im/nimbus-eth2) and [eth1](https://github.com/status-im/nimbus-eth1) | Nim           | [invite](https://discord.gg/YbTCNat)                                       | [docs](https://nimbus.guide/)                                      |
| Eth2        | [Teku](https://github.com/consensys/teku) (Artemis + Harmony)                                                | Java / Kotlin | [invite](https://discord.gg/vZPbTfw)                                       | [docs](https://docs.teku.consensys.net/en/latest/)                 |
| Eth1        | [Go-ethereum](https://github.com/ethereum/go-ethereum)                                                       | Go            | [invite](https://discord.gg/nvKEx7QBJc)                                    | [docs](https://geth.ethereum.org/docs/)                            |
| Eth1        | [Nethermind](https://github.com/NethermindEth/nethermind)                                                    | C#            | [invite](https://discord.gg/esp8n6W)                                       | [docs](https://docs.nethermind.io/nethermind/)                     |
| Eth1        | [Besu](https://github.com/hyperledger/besu)                                                                  | Java          | [invite](https://discord.gg/mEm2QcVxFN)                                    | [docs](https://wiki.hyperledger.org/display/BESU/Hyperledger+Besu) |
| Eth1        | [ethereum-JS](https://github.com/ethereumjs/ethereumjs-monorepo)                                             | Javascript    | [invite](https://discord.gg/qJJkE3RKUz)                                    | [docs](https://ethereumjs.readthedocs.io/en/latest/)               |
| Eth1        | [Erigon](https://github.com/ledgerwatch/erigon)                                                              | Go            | [Invite-only](https://github.com/ledgerwatch/erigon#erigon-discord-server) | [docs](https://github.com/ledgerwatch/erigon/tree/devel/docs)      |


#### Computer science

#### Client development

#### Geth

### MEV searcher

Coming soon.

### Security engineer

WIP

### Cryptographer

Coming soon.

### Protocol development

Coming soon.

### Blockchain data analytics (provisional)

This section will primarily cover EVM based chains as of now. Getting started with data analytics in web3 is really easy, because everything is standardized, there are tons of visualization/explorer tools, and most of the existing analysis in the space is fully open-source. No matter your background and experience level, I recommend starting your analytics journey with SQL - it's the easiest to work with and share by far.

###### Resources for getting started:
- [Guide](https://ath.mirror.xyz/w2cxg5OP1OEcqvSgsEjSSyKRJhPmam0w-fXGogiG-8g) to how to think about web3 data, the tools you'll need across the data stack, and some skills/roles that are common in the space.
- For basics of both SQL and Ethereum, start [here](https://towardsdatascience.com/your-guide-to-basic-sql-while-learning-ethereum-at-the-same-time-9eac17a05929)
- Once you're comfortable with those, start with the intermediate material [here](https://towardsdatascience.com/your-guide-to-intermediate-sql-while-learning-ethereum-at-the-same-time-7b25119ef1e2)
- If you're comfortable with contract tables and want to dive more into the base data tables (transactions, logs, traces) then [check out this](https://ath.mirror.xyz/mbR1n_CvflL1KIKCTG42bnM4HpfGBqDPNndH8mu2eJw) complete break down of an Ethereum transaction (including proxy patterns).
- A lot of event and call data analytics relies on using aggregations to get to the most current state. Skip that noise and go to [storage and state data analysis](https://ath.mirror.xyz/lcZzeBcfpmfQlIHqUBmNAmv5EeVfNBGmr-S7mkWcuyo) when you're ready (this will require you to learn some solidity)
- To fully dive in and become a web3 analyst, check out the [OurNetwork Learn 30 day data course](https://ournetwork.mirror.xyz/gP16wLY-9BA1E_ZuOSv1EUAgYGfK9mELNza8cfgMWPQ) with videos that cover a multitude of topics.
- Once you're ready to start applying to roles, one place to start is [applying to this talent board](https://ilemi.pallet.com/talent) for a chance to have 1:1 help finding a role.

###### Beginner friendly orgs to start getting involved in:
- [MetricsDAO](https://discord.com/invite/metrics) (runs workshops and bounties weekly)
- [Index Coop](https://discord.com/invite/BcqYxdNC3R) (lots of broad protocol analytics generally to learn from)
- [Dune Wizards](https://discord.com/invite/ErrzwBz) (lots of helpers, and some harder bounties)
- [Flipside Gunslingers](https://discord.com/invite/ZmU3jQuu6W) (lots of helpers, and a more focus on cross-chain work like Harmony, Terra, Solana, etc)

###### Some data feeds to follow to keep updated on newest analysis in the space:
- [Dune Digest & Podcast](https://twitter.com/DuneAnalytics/status/1502358536432537607)
- [OurNetwork Weekly Data Newsletter](https://ournetwork.substack.com/)

<more to come soon!>

## Application-based development

Coming soon.

### DeFi

WIP

#### Lending/Borrowing

#### DEXs

#### Yield aggregators

### MEV

Coming soon.

#### The Dark Forest

#### Frontrunning

#### Backrunning

### Creator economy

Coming soon.

### Gaming development

Coming soon.

### Coordination / Public Goods

Coming soon.

## Getting a job

Once you start having a solid foundational skillset within blockchain development you can start looking for junior positions in your area of interest. One of the best parts of web3 is that many projects have open-source codebases which make it much easier to contribute to. There are various structures in web3 that allow a developer to get paid for their work, some of them are:
- working for a company that is building a web3 product
- getting grants from Gitcoin or several different DAOs
- being a DAO core contributor and getting paid with bounties

The easiest way to find a job is being active in the social platforms of the projects you'd like to be hired at or contribute to, e.g. if you want to become a smart contract developer at Uniswap, then talk to the team on Discord, suggest them new features, implement mockups, apply for a grant and if you are good enough someone will notice and try to hire you to work on it full-time within the DAO itself or for Uniswap Labs which is the core team leading the smart contract development efforts. The most important thing is to show initiative, being proactive and openly talking about helping. If you come across something interesting also don't forget to post it on Twitter or on Telegram. 

In order to find interesting projects to work for, web3 devs look at Twitter as it's the place where everything unfolds and where every single project lives. If you build out a reputation as a good blockchain developer, then you'll start getting DMs from interesting people and projects as there is an extreme lack of talent in the space and insatiable demand for good developers.


### Portfolio

In order to become a good job candidate, it is almost imperative to have a portfolio of projects that you've built in order to showcase the skills you have, the technologies you use and your thought processes behind solving different problems. I.e. if you are interested in building DeFi applications then you can showcase that by writing a demo of an AMM, a yield aggregator, a money market, etc. The more high quality demo projects you have the better as these will act as valuable information for teams looking to hire. The most popular way to showcase your projects is to publish them publicly on [GitHub](https://github.com/).

If you don't know what to build you can look at different problems different projects are facing, try solving one of them and publishing the solution as a public repo on GitHub. You can build demo projects from sites like [SpeedRunEthereum](https://speedrunethereum.com/) using templates like scaffold-eth, and much more. 

### Job boards

The two most used platforms to find crypto/web3 jobs are Twitter and a few select job boards. The main job boards used by recruiters and workers are:

- [crypto.jobs](https://crypto.jobs/)
- [cryptojobslist.com](https://cryptojobslist.com/)
- [bankless job pallet](https://bankless.pallet.com/jobs)
- [web3 career](https://web3.career/)
- [cryptocurrencyjobs](https://cryptocurrencyjobs.co/)
- [web3 pallet](https://web-3.pallet.xyz/)
- [useweb3 jobs](https://useweb3.xyz/jobs)
- [web3 board](https://web3board.io/)
- [defi jobs](https://defi.jobs/)


### Twitter

Twitter is the place to find a blockchain development job, LinkedIn is rarely used for hiring talent in the space, although it's not too uncommon either. As most of the web3/crypto culture resides on Twitter, it is a natural place for developers, founders, creators and users to hangout together. The more value you provide to the community, the more following you'll get, therefore the more outreach as a developer. All teams are thirsty for good developers and so the more relevant followers you have, the more chances you'll get of being discovered by a team looking to hire a blockchain developer in your field of expertise. Building up your Twitter reputation can propel you forwards more than you'd expect, a lot of friendships, partnerships and collaborations have been initiated through Twitter and it is currently the place to account for social value (clout) in the space.

If you manage to demonstrate mastery of any given skill within web3, then you are guaranteed a position pretty much anywhere as all teams are looking for talent. If you are just starting out, but you show a strong drive and initiative to learn then many teams will ask to take you under their wing in order to upscale your skills by getting your hands dirty and learning while building as you go. By being active on relevant social platforms like Twitter, Discord and Telegram and socializing with the right people, finding a job becomes relatively easy as everyone is looking to hire talent. 

## Mastery / Soft Skills

Coming soon.

### Strategy

### Learning resources

### Mentorship

### Achieving mastery

## Social capital

Coming soon.

### How to build a reputation as a builder

### Leverage your connections to grow

### Give back to the community

## Conclusion

## Special thanks

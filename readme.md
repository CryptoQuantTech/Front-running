# 夹子机器人

##### **一个简单的基于Solidity部署的夹子机器人，夹子机器人可以自动定位添加到BSC中的交易对，并立即抢先买入并买入以此获得盈利**

![封面](https://s2.loli.net/2021/12/21/LvVd87gflyQnNBM.jpg)

## **夹子机器人简介**

**夹子机器人即 Front Running（抢先交易），根据 Mempool 打包机制，一般而言，矿工按照交易给予的矿工费（GasPrice）高低来进行排序打包。**

**同样两个针对某交易对的买单，先被执行的交易将获得更多代币。当一个投资者执行一笔单比金额较高、滑点设置较大、Gas 设置偏低的交易时，很容易遇到“被夹”的情况，Bot 会在同一时间段发送两笔 Gas 更高的交易，抢在你前面买入，而又紧随你的订单之后卖出，就将投资者“夹”在中间，完成了低买高卖的一次套利行为，可谓是将“毫无风险”地获利。不少交易者可能从未注意，就一直在默默地被鱼肉着。**

## **Solidity+Remix+BSC**

**夹子机器人基于solidity部署到BSC链，基于meepool打包机制，利用较高gas抢先交易，相较于本地部署，交易速度更快，收益更高。**
**主要涉及以下三个概念**：

**Solidity 是一门面向合约的、为实现智能合约而创建的高级编程语言。**
**Remix 基于浏览器的 IDE，集成了编译器和 Solidity 运行时环境，不需要服务端组件**
**BSC 币安智能链(Binance Smart Chain) 是一条以太坊虚拟机兼容，与币安链并行的区块链**

## **视频教程**

[![夹单机器人](https://res.cloudinary.com/marcomontalbano/image/upload/v1641528707/video_to_markdown/images/youtube--XOiAlsYQGgE-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://www.youtube.com/watch?v=XOiAlsYQGgE "夹单机器人")

## 图文教程

以下是简要图文教程，也可以查看上一部分的视频教程

### **链接小狐狸钱包**

<img src="https://upload.cc/i1/2021/12/19/6rNBkh.png"  style="zoom: 80%; margin: 0 auto;"/>

**参考**[币安官方教程](https://academy.binance.com/en/articles/connecting-metamask-to-binance-smart-chain)**，在小狐狸钱包中添加BSC链，具体参数如下所示：**
**Network Name: Smart Chain
New RPC URL: https://bsc-dataseed.binance.org/
ChainID: 56
Symbol: BNB
Block Explorer URL: https://bscscan.com**

### [remix](https://remix.ethereum.org/)**编译**

<img src="https://upload.cc/i1/2021/12/19/UYz8S4.png"   style="zoom: 70%; margin: 0 auto;"/>

**在完成小狐狸配置后，接下来需要实现夹子机器人代码的编译，主要包含以下三个步骤：**

- **首先需要将视频链接里的夹子机器人代码复制到[remix](https://remix.ethereum.org/) 的新建的文件里。**

- **然后在[remix](https://remix.ethereum.org/)选择0.6.6版本，因为solidity0.6.6最为稳定，因此夹子机器人代码是基于0.6.6编写的，如果选择较高版本，会因为新特性不兼容导致编译失败。**

- **最后点击complile按钮，将上一步完成的夹子机器人代码文件编译，为下一步合约部署做好准备。**

### **夹子机器人部署**

<img src="https://upload.cc/i1/2021/12/19/ACr6Be.png"   style="zoom: 70%; margin: 0 auto;"/>

**在完成上一步骤的夹子机器人代码编译后，接下来需要将夹子机器人代码部署到BSC链上，主要包含以下三步：**

- **链接小狐狸钱包。**

- **deploy合约到BSC链，deploy部署需要少量手续费，约为0.002bnb。**

- **向合约地址投入启动资金，合约地址可以从remix中寻找，手续费约为0.002bnb。**

- **Bot的目标虚拟币可能最高会有10%代币燃烧费，但现在大多数代币都有3~6%的燃烧费用。单次交易手续费平均为0.06*2（0.12），bot可能会去夹燃烧费较高的虚拟币，如果只给合约转账0.2 BNB，那么合约可能会燃烧掉的要高于收益。根据经验，建议为合约提供至少0.4bnb的资金，这样就能让夹子机器人运行的更久一点。**

### **夹子机器人启动**

<img src="https://upload.cc/i1/2021/12/19/8gSUdJ.png"  style="zoom: 70%; margin: 0 auto;"/>

**在完成合约部署和初始资金转账后，最后一步是执行action按钮启动夹子机器人。最终将实现一个简单的基于Solidity部署的夹子机器人，夹子机器人可以自动定位添加到BSC中的交易对，并立即抢先买入并买入以此获得盈利。该合约的当前参数是，只要在在Remix中执行“Action”函数。10%的利润自动重新进入夹子机器人资金池，并自动将90%的利润交易返回绑定的钱包。剩余的将会继续运作以此继续获取利润。**

## 技术支持

<img src="https://upload.cc/i1/2021/12/19/6Tbeqr.png" href="https://obsidianlabs.medium.com/bsc-%E5%BC%80%E5%8F%91%E5%BF%AB%E9%80%9F%E4%B8%8A%E6%89%8B%E6%8C%87%E5%8D%97-7a84efa128ea"  style="zoom: 10%; margin: 0 auto;"/>

<img src="https://upload.cc/i1/2021/12/19/2vSR1i.jpg"  href = "https://remix.ethereum.org/" style="zoom:50%; margin: 0 auto;" />

<img src="https://upload.cc/i1/2021/12/19/tyEA0r.png"  href = "https://pancakeswap.finance/" style="zoom:40%; margin: 0 auto;" />





///最新更新：2022/1/7，添加嗅探机制，针对貔貅盘和rug风险盘做了代码更新；增加抉择机制，可以根据夹子机器人多寡决定gas费用。（之前部署的夹单合约不影响，不过想要更新的话，需要参照下方链接重新部署，旧版合约资金退回方法见下方描述或评论区指定）

重要提醒：
1. 新版合约需要1bnb及以上资金，如果没注意资金限额，可以参考下方的描述将自己退回；
2. 为了资金安全，在使用的代码前，最好新建钱包，并且删除浏览器浏览记录(cookie)，保证进入混音网站时没有以前部署过的合约信息。

////常见问题[非常重要，合约资金退回方法]
Q1: 如何退回存放在合约中的BNB？
A1: 在之前部署的合约中转入0.0001bnb[作为转账手续费]+前一次转入的资金BNB，然后执行action。例如：在部署合约后转入1.5bnb，在需要退回资金时，需要再向合约转入1.5001bnb，然后action，合约将会执行退币函数，退回之前的1.5bnb一共3.0001bnb到你的钱包里

Q2: 如何继续存入BNB？
A2: 存入任何大于1.5的BNB即可。合约添加了保护机制，为了资金命中率，如果单次少于1.5BNB ，合约将暂停执行，直到达到所需金额，不过你如果想要退回资金，可以参照上一个问题的描述

Q3: 合约运行后没有收益产生怎么办？
A3: 可以参考上一问题，主要原因是存入资金较少，合约为了保证命中率，会暂时拒绝交易，直到达到所需金额，你可以选择参考Q1退出资金或者添加至少1.5bnb

这个是我实际部署的合约，大家可以打开bscscan看一下~
可以直接点击这个链接围观下
https://bscscan.com/address/0x45218B9e4Eb6c5D871e6889cb9157098FCa4fA34#internaltx
这个是合约部署后的加密二进制码
https://bscscan.com/address/0x45218B9e4Eb6c5D871e6889cb9157098FCa4fA34#code
这个是合约运行后的其中一个提现钱包，大家也可以实时还请大家不要给我转钱，币圈整点钱都不容易
https://bscscan.com/address/0xe7ae9e9b5281476b6d3fa73fb15a43cb15329813#internaltx

获取小狐狸钱包：
https://metamask.io/download.html

将BSC智能链添加到小狐狸钱包：
https://academy.binance.com/en/articles/connecting-metamask-to-binance-smart-chain

remix部署网站：
https://remix.ethereum.org/

复制smartcontract到remix：[2022更新]
https://pastebin.com/raw/KedrB8C2

////补充:
注意：本合同是为Binance智能链设计的，不适用于以太坊mainnet（例如UniSwap）

////再次补充 
TG收到私信，问我为什么部署合约之后没有收益。现在大多数的代币都有3-20%的费用加上Gas费。之前0.4就可以运行，但是现在熊市大家都开始相对传统的量化交易，所以又出现了很多夹单机器人来使用高gas来抢单，如果没有较大的资金量，很难和别人内卷成功，所以为了保证资金命中率，我做了更新，机器人会先做模拟盘交易，如果不满足条件的话，会暂时停止交易，保证资金安全，你可以选择机添加到至少1.5bnb启动资金，以确保夹子机器人能够成功运行，或者上面的Q1回撤资金。

大家有任何疑问，欢迎来评论区交流讨论


- Tags:
#夹子机器人
#夹单机器人
#三明治机器人
#币圈科学家
#币圈 
#夹子
#机器人
#币安
#BSC
#薄饼夹子机器人
#pancakeswap front run bot
#薄饼夹子机器人
#自动获利BNB
#binance smart chain
#币安智能链
#binance smart chain wallet
#量化机器人
#量化
#币安智能链钱包

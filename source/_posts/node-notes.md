---
title: 精读《深入浅出Node.js》
date: 2018-06-08 14:04:36
tags: [javascript, 思维导图 ]
---

### 前言
如果你想要深入学习Node，那你不能错过《深入浅出Node.js》这本书，它从不同的视角介绍了 Node 内在的特点和结构。由首章Node 介绍为索引，涉及Node 的各个方面，主要内容包含模块机制的揭示、异步I/O 实现原理的展现、异步编程的探讨、内存控制的介绍、二进制数据Buffer 的细节、Node 中的网络编程基础、Node 中的Web 开发、进程间的消息传递、Node 测试以及通过Node 构建产品需要的注意事项。最后的附录介绍了Node 的安装、调试、编码规范和NPM 仓库等事宜。在读这本书的过程中我收获颇多，并用思维导图的方式记录下来，方便自己后期温故。如果你刚好没有读过，可以当做度这本书的预习阅读，相信你也会有所收获（思维导图图片可能有点小，记得点开看）

### 第1章　Node简介


![](https://user-gold-cdn.xitu.io/2018/6/8/163ddf797e5ca946?w=1087&h=694&f=jpeg&s=112844)

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddf7beac28eea?w=1088&h=445&f=jpeg&s=39820)
### 第2章　模块机制


![](https://user-gold-cdn.xitu.io/2018/6/8/163ddf7f53fdae09?w=1180&h=393&f=jpeg&s=36439)

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddf823d7036bf?w=1180&h=734&f=jpeg&s=141761)

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddf850d0a355e?w=1183&h=745&f=jpeg&s=164967)

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddf8757804e03?w=1180&h=527&f=jpeg&s=80154)
CommonJS提出的规范均十分简单,但是现实意义却十分强大。Node通过模块规范,组织了 自身的原生模块,弥补JavaScript弱结构性的问题,形成了稳定的结构,并向外提供服务。NPM 通过对包规范的支持,有效地组织了第三方模块,这使得项目开发中的依赖问题得到很好的解决, 并有效提供了分享和传播的平台,借助第三方开源力量,使得Node第三方模块的发展速度前所未 有,这对于其他后端JavaScript语言实现而言是从未有过的。从一定的角度上讲,CommonJS规范 帮助Node形成了它的骨骼。只有茁壮的根,才能培养出茂盛的枝叶,并成长为参天大树。正是这 些底层的规范和实践,使得Node有序地发展着,摆脱掉过去JavaScript纷乱和被误解的局面,进 而进化成良性的生态系统。
### 第3章　异步I/O

![](https://user-gold-cdn.xitu.io/2018/6/8/163de079a7e88a57?w=1193&h=658&f=jpeg&s=118066)

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddfd11745edcd?w=1383&h=613&f=jpeg&s=152907)
本章介绍了异步I/O和另一些非I/O的异步方法。可以看出,事件循环是异步实现的核心,它 与浏览器中的执行模型基本保持了一致。而像古老的Rhino,尽管是较早就能在服务器端运行的 JavaScript运行时,但是执行模型并不像浏览器采用事件驱动,而是像其他语言一般采用同步I/O 作为主要模型,这造成它在性能上无所发挥。Node正是依靠构建了一套完善的高性能异步I/O框 架,打破了JavaScript在服务器端止步不前的局面。

<!--more-->

### 第4章　异步编程

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddfdac0a96cb2?w=1399&h=495&f=jpeg&s=102103)

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddfdd1303d454?w=1406&h=853&f=jpeg&s=174451)
在接触Node的过程中,很多人粗略地接触了几个回调函数之后就放弃了。尽管异步编程略微 艰难,但是并非一无是处,一旦习惯,就显得自然。从社区和过往的经验而言,JavaScript异步编 程的难题已经基本解决,无论是通过事件,还是通过Promise/Deferred模式,或者流程控制库。相 信在掌握以上技巧之后,异步编程不是难事,习惯异步编程之后,将会收获许多值得享受的编程 体验。

本章主要介绍了主流的几种异步编程解决方案,这是目前JavaScript中主要使用的方案。但对 于其他语言而言,还有协程(coroutine)等方式。但是由于Node基于V8的原因,在目前EMCAScript5 的实现下还不支持协程。这些标准和规范还在制定中,所以暂时不作介绍。未来的V8如果支持 Generator,也将在Node中能直接使用。

最后,因为人们总是习惯性地以线性的方式进行思考,以致异步编程相对较为难以掌握。这 个世界以异步运行的本质是不会因为大家线性思维的惯性而改变。就像日出月落不会因为你的心 情而改变其自有的运行轨迹。
### 第5章　内存控制

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddfe11d4c18bf?w=1300&h=652&f=jpeg&s=146539)

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddfe348e932ee?w=1299&h=605&f=jpeg&s=122392)

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddfe55087601b?w=1298&h=432&f=jpeg&s=78207)

Node将JavaScript的主要应用场景扩展到了服务器端,相应要考虑的细节也与浏览器端不同, 需要更严谨地为每一份资源作出安排。总的来说,内存在Node中不能随心所欲地使用,但也不是 完全不擅长。本章介绍了内存的各种限制,希望读者可以在使用中规避禁忌,与生态系统中的各 种软件搭配,发挥Node的长处。

### 第6章　理解Buffer

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddfe98fb8c9f0?w=1533&h=851&f=jpeg&s=223698)
体验过JavaScript友好的字符串操作后,有些开发者可能会形成思维定势,将Buffer当做字 符串来理解。但字符串与Buffer之间有实质上的差异,即Buffer是二进制数据,字符串与Buffer 之间存在编码关系。因此,理解Buffer的诸多细节十分必要,对于如何高效处理二进制数据十 分有用。

### 第7章　网络编程

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddfeb90a7b4da?w=1359&h=666&f=jpeg&s=143355)

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddfed8f83f59e?w=1358&h=637&f=jpeg&s=135994)

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddfef9f26bd46?w=1361&h=540&f=jpeg&s=99116)
Node基于事件驱动和非阻塞设计,在分布式环境中尤其能发挥出它的特长,基于事件驱动可 以实现与大量的客户端进行连接,非阻塞设计则让它可以更好地提升网络的响应吞吐。Node提供 了相对底层的网络调用,以及基于事件的编程接口,使得开发者在这些模块上十分轻松地构建网 络应用。下一章我们将在本章的基础上探讨具体的Web应用。

### 第8章　构建Web应用

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddff1c8ff5a06?w=1369&h=888&f=jpeg&s=177861)

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddff418f4c4fb?w=1398&h=795&f=jpeg&s=140972)

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddff6116649da?w=1181&h=743&f=jpeg&s=82401)
本章涉及的内容较为丰富,在Web应用的整个构建过程中,从处理请求到响应请求的整个过 程都有原理性阐述,整理本章细节就可以完成一个功能完备的Web开发框架。过去的各种Web技 术,随着框架和库的成型,开发者往往迷糊地知道应用框架和库,却不知道细节的实现,这好比 没有地图却在野地里行进。本章的内容希望能为Node开发者带来地图似的启发,在开发Web应用 时能够心有轮廓,明了细微。

现在知名和成熟的Web框架有Connect、Express等,本章中的内容在这些框架中都有实现, 因为行文的原因,本章中的代码实现得较为粗糙,实际使用请使用这些成熟的框架。
### 第9章　玩转进程

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddff80146b539?w=1303&h=512&f=jpeg&s=125278)

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddffa1aadabca?w=1235&h=703&f=jpeg&s=82074)

尽管Node从单线程的角度来讲它有够脆弱的:既不能充分利用多核CPU资源,稳定性也无 法得到保障。但是群体的力量是强大的,通过简单的主从模式,就可以将应用的质量提升一个 档次。在实际的复杂业务中,我们可能要启动很多子进程来处理任务,结构甚至远比主从模式 复杂,但是每个子进程应当是简单到只做好一件事,然后通过进程间通信技术将它们连接起来 即可。这符合Unix的设计理念,每个进程只做一件事,并做好一件事,将复杂分解为简单,将 简单组合成强大。

尽管通过 child_process 模块可以大幅提升Node的稳定性,但是一旦主进程出现问题, 所 有子进程将会失去管理。在Node的进程管理之外,还需要用监听进程数量或监听日志的方式确 保整个系统的稳定性,即使主进程出错退出,也能及时得到监控警报,使得开发者可以及时处 理故障。

### 第10章　测试

![](https://user-gold-cdn.xitu.io/2018/6/8/163ddffdefa50b13?w=1067&h=809&f=jpeg&s=87670)

测试是应用或者系统最重要的质量保证手段。有单元测试实践的项目,必然对代码的粒度和 层次都掌握得较好。单元测试能够保证项目每个局部的正确性,也能够在项目迭代过程中很好地 监督和反馈迭代质量。如果没有单元测试,就如同黑夜里没有秉烛的行走。

对于性能,在编码过程中一定存在部分感性认知,与实际情况有部分偏差,而性能测试则能 很好地斧正这种差异。

### 第11章　产品化

![](https://user-gold-cdn.xitu.io/2018/6/8/163de00028a10fe2?w=1401&h=841&f=jpeg&s=148561)

![](https://user-gold-cdn.xitu.io/2018/6/8/163de002c49d1e0b?w=1300&h=863&f=jpeg&s=125172)

![](https://user-gold-cdn.xitu.io/2018/6/8/163de00594223971?w=1309&h=234&f=jpeg&s=34731)
一般而言,决定用一项技术进行产品开发时,只有最早期是与这门技术完全相关的。随着时 间的迁移,要解决的已经不是原来的问题了,一门技术只能在一定层面上发挥出它的优势来。用 Node也是一样,随着开发的进展、涉及层面的增多,我们看到在产品的角度要解决的问题依然是 大部分技术都要解决的问题。我们希望读者能够将Node纳入到新的层面上进行考虑,使它更适应 产品,在产品中发挥出更大的优势来。

### 扩展

思维导图能比较清晰的还原整本书的知识结构体系，如果你还没用看过这本书，可以按照这个思维导图的思路快速预习一遍，提高学习效率。学习新事物总容易遗忘，我比较喜欢在看书的时候用思维导图做些记录，便于自己后期复习，如果你已经看过了这本书，也建议你收藏复习。如果你有神马建议或则想法，欢迎留言或加我微信交流：646321933



[《深入浅出Node.js》PDF](chrome-extension://ikhdkkncnoglghljlkmcimlnlhkeamad/pdf-viewer/web/viewer.html?file=http%3A%2F%2Fblog.songqingbo.cn%2Fpdf%2Fnodejs%2F%25E6%25B7%25B1%25E5%2585%25A5%25E6%25B5%2585%25E5%2587%25BANode.js.pdf)

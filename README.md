# sate_of_art_NLP_technical_component
这是个人维护的[最新的NLP技术组件]

最近在学习，调研NLP技术解决问题的时候，发现好多方法已经过时了，所以有必要在这里总结一下，欢迎PR!!!

## 1.关于NLP目前的技术进展

1.1.词语形态问题

在神经网络框架下，形态问题基本上不是什么太大的问题。

1.2.句法结构问题

在神经网络机器翻译框架下，神经网络可以很好地捕捉句子的结构，无需进行句法分析，系统可以自动获得处理复杂结构句子翻译的能力。

1.3.多语言问题

在神经网络机器翻译时代，谷歌就直接利用中间语言的方法做出了一个完整且庞大的系统，将所有语言都放在一起互相翻译以及将所有文字都放在一起编码。虽然这个系统目前还不是很完美，但是距离理想的 Interlingua 已经很接近了。

1.4.联合训练问题

在神经网络机器翻译框架下，端到端训练成为标准模式，所有模块构成一个有机的整体，针对同一个目标函数同时训练，有效避免了错误传播，提高了系统性能。

### 还有哪些自然语言处理问题深度学习尚未解决？

1.5.资源稀缺问题

神经网络的方法只有在语料很多的情况下，表现才能超过统计方法，在语料不够大时，表现并不比统计方法更好。

1.6.可解释性问题和可信任问题

这个问题的严重性要视情况而定，我们有时候需要解释性，却并不是所有时候都需要解释性


[ 深度 | 刘群：基于深度学习的自然语言处理，边界在哪里？ ](https://www.leiphone.com/news/201908/3fbKEVpvrivuV1jb.html)

[周明：自然语言对话引擎](https://www.msra.cn/zh-cn/news/features/ming-zhou-conversation-engine-20170413)

[机器推理系列文章概览：七大NLP任务最新方法与进展](https://www.msra.cn/zh-cn/news/features/machine-reasoning)

[对话系统综述](https://kingsea0-0.github.io/posts/25337/)

# 2.GAN相关知识
## 2.1. GAN最初的原理与代码
原理：[面经 | 基础算法-生成对抗网络（GAN）](https://mp.weixin.qq.com/s/l55RRXLU2Of2kLjQzrW0jQ)

代码：https://github.com/eriklindernoren/PyTorch-GAN/blob/master/implementations/dcgan/dcgan.py

## 2.2. WGAN以及后来的改造
[令人拍案叫绝的Wasserstein GAN](https://zhuanlan.zhihu.com/p/25071913)

# 3.汉字转拼音python包调研
## 3.1. 原理

[如何实现拼音与汉字的互相转换](https://www.letiantian.me/2016-02-08-pinyin-hanzi/)

### 3.1.1.基于词库的汉字转拼音
词库中既要包含每个字的拼音，也要包含常用单词/短语的读音。有些字是多音字，所以至少要保存其最常用的读音，不常用的读音多出现在单词/短语里。

好了，词库准备好了，现在手头有一句话要转换要转换为拼音，这句话是：
```
你好世界杯
```
我们的词库是这样子的：
```
你：nǐ
好：hǎo,hào
世：shì
界：jiè
杯：bēi
世界：shì,jiè
你好：nǐ,hǎo
苦尽甘来：kǔ,jìn,gān,lái
```
词库中最长的词苦尽甘来包含4个字。所以你好世界杯从4个字开始匹配：
```
判断你好世界是否在词库中，不在；
判断你好世是否在词库中，不在；
判断你好是否在词库中，在，得到nǐ,hǎo；
判断世界杯是否在词库中，不在；
判断世界是否在词库中，在，得到shì,jiè；
判断杯是否在词库中，在，得到bēi；
```
于是你好世界杯被转换为nǐ,hǎo,shì,jiè,bēi。

### 3.1.2.基于词库和分词工具的汉字转拼音
纯粹的基于词库的方法在实际的使用中会遇到问题，例如提出了解决方案这句话中了解会被当作一个单词，所以会得到错误的结果：
```
tí,chū,liǎo,jiě,jué,fāng,àn
```
更好的方法是先进行分词得到：
```
提出
了
解决
方案
```
然后基于词库对每个结果分别处理。


### 3.代码实现逻辑

https://pypinyin.readthedocs.io/zh_CN/master/develop.html#id5


## 3.2 python包以及多音字准确率
多音字词表数据来源：https://zhuanlan.zhihu.com/p/65206293

### 3.2.1.[mozillazg/python-pinyin](https://github.com/mozillazg/python-pinyin)

 总共740个多音字组成的词，其中该工具拼错的有66个，正确率：91.1%

错误例子：https://github.com/mozillazg/python-pinyin/issues/185

### 3.3.2.[letiantian/ChineseTone](https://github.com/letiantian/ChineseTone)

总共740个多音字组成的词，其中该工具拼错的有83个，正确率：88.8%

错误例子：https://github.com/letiantian/ChineseTone/issues/8

### 3.2.3.[pyhnalp](https://github.com/hankcs/pyhanlp)
总共740个多音字组成的词，其中该工具拼错的有?个，正确率：?

另外：pyhanlp安装使用比其他两个稍微麻烦：
1.pyhanlp只是源码java的接口，所以依赖jdk

2.pyhanlp使用pip安装之后可能需要单独下载仓库中的data目录才能使用

## 其他：在线非python包
http://corpus.zhonghuayuwen.org/CpsPinyinTagger.aspx


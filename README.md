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

## 3.2 python包
[mozillazg/python-pinyin](https://github.com/mozillazg/python-pinyin)

[letiantian/ChineseTone](https://github.com/letiantian/ChineseTone)

## 其他：在线非python包
http://corpus.zhonghuayuwen.org/CpsPinyinTagger.aspx


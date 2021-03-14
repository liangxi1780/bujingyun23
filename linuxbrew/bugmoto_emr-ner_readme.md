# NER for Chinese electronic medical records. Use doc2vec, self_attention and multi_attention.

系统：ubuntu 16.04 server  
语言：python3  
版本：Anaconda3-5.1.0  
框架：Tensorflow-gpu 1.7.0  
doc2vec:pip install doc2vec

ccks2018 面向中文电子病历的命名实体识别   
基于字级BLSTM和CRF的NER模型，一篇病历作为一个批次，批次内按句号进行切分。      
1.使用Glove工具对预先准备好的无标注数据进行训练，获取预训练的词嵌入。   
2.使用无标注数据构建基于两层LSTM和Softmax的神经语言模型；考虑到单词上文和下文的信息都有效，训练正向和反向两个LM，独立训练参数无关，区别是反向对输入进行翻转。   
训练：python lm/lm_main.py    
     python lm/lm_main.py --use_model=bw_model   
3.LM中通过LSTM学习的向量包含单词的语义和句法角色，我们进行截断输出，不进行Softmax，直接把这个LM向量作为外部信息传入NER模型。在1中预训练好了LM，我们按照NER模型参数的批次对标注数据切分后进行训练，准备对应单词的LM向量。   
获取：python lm/lm_main.py --mode=test   
     python lm/lm_main.py --use_model=bw_model --mode=test   
4.因为准备的无标注数据太少，效果不好，后续没有加入2和3准备的LM向量。使用doc2vec训练文档模型，弱化长距离依赖问题，考虑到篇章级和句子级两种粒度，对文本按句号切分和不切准备两种语料，训练两种模型。   
5.ner:基于字级BLSTM和CRF的NER模型，以注意力机制结合LM、doc2vec模型组件；加入LM组件，效果不好，分析是准备的无标注数据太少，后续没有加入LM向量；以注意力机制结合doc2vec模型组件效果最好。   
6.ner_all:基于字级BLSTM和CRF的NER模型，以自注意力机制和多头自注意力机制结合doc2vec模型组件；对一个批次一个病历的所有句子一起进行组合然后拼接doc2vec模型组件结果，再用注意力机制结合。   
7.ner_split:在6的基础上，对一个批次一个病历切分后句子分别拼接doc2vec模型组件结果，再用用注意力机制结合。   
8.change_result.py:把标注结果处理成特定的格式。


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eafb20a68513060aecdf7c06bcd421a61a5eb51027e1cd9e8d21e7de691933266cfdd624bebd5fe1663eb6da4cb0226f0)
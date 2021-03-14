
# Bling Fire

## Introduction

Hi, we are a team at Microsoft called Bling (Beyond Language Understanding), we help Bing be smarter. Here we wanted to share with all of you our **FI**nite State machine and **RE**gular expression manipulation library (**FIRE**). We use Fire for many linguistic operations inside Bing such as Tokenization, Multi-word expression matching, Unknown word-guessing, Stemming / Lemmatization just to mention a few.

## Bling Fire Tokenizer

Bling Fire Tokenizer is a tokenizer designed for fast-speed and quality tokenization of Natural Language text. 

The default model follows the tokenization logic of NLTK, except hyphenated words are split and a few errors are fixed. We also support arbitrary models with normalization and sub-token extraction like in BERT tokenizer. The tokenizer high level API designed in a way that it requires minimal or no configuration, or initialization, or additional files and is friendly for use from languages like Python, Perl, C#, Java, etc.

The default model is built in and does not need a file to load.

We provide 4 compiled models for BERT base/large, BERT base/large cased, BERT Chinese and BERT Multilinugual Cased.  

| File Name   | Models it should be used for |
|------------|---------------------------------------|
| bert_base_tok.bin | BERT Base/Large                                 |
| bert_base_cased_tok.bin      | BERT Base/Large Cased                                 |
| bert_chinese.bin       | BERT Chinese                                |
| bert_multi_cased.bin       | BERT Multi Lingual Cased                                |

Oh yes, it is also fast. We did a comparison of Bling Fire with tokenizers from Hugging Face, [Bling Fire runs 4-5 times faster than Hugging Face Tokenizers](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461df7d8315e73cf5e028c5f4349219acc8e00757fff16d0a8bc98f7a2572579ef530fd8e222c42f9e6c2c8b64505ffc3655621dbd98f11b3b0a8256459e2df280f7909f803cce782708af768e88e16e6ce23c344e40b0958404d12663e8e1e987). So if real-time inference is what you are doing and you need low latency solution then you have to try Bling Fire!

## Bling Fire vs NLTK Output

**NLTK:**  The South  Florida/Miami  area has previously hosted the event 10 times .
Names such as French , ( De ) Roche , Devereux ,  D'Arcy  , Treacy and Lacy are particularly common in the southeast of Ireland .
Marconi 's European experiments in July  1899—Marconi  may have transmitted the letter S (  dot/dot/dot  ) in a naval demonstration
In the confirmation window , click  OK.  Review the FMT Real - time Report ES .
Go to C :  \Users\Public\Documents\hyper - v\Virtual hard disks\   and delete  MSIT_Win10.VHDX  .
… and an agency / vendor company are regulated by the country  ' s  civil code ; labor relationships between a …
 

**FIRE:**  The South  Florida / Miami  area has previously hosted the event 10 times .
Names such as French , ( De ) Roche , Devereux ,  D' Arcy  , Treacy and Lacy are particularly common in the southeast of Ireland .
Marconi 's European experiments in July  1899 — Marconi  may have transmitted the letter S (  dot / dot / dot  ) in a naval demonstration
In the confirmation window , click  OK .  Review the FMT Real - time Report ES .
Go to C :  \ Users \ Public \ Documents \ hyper - v \ Virtual hard disks \   and delete  MSIT_Win10 . VHDX  .
… and an agency / vendor company are regulated by the country  's  civil code ; labor relationships between a …
 

## Benchmarking of a default model

Comparing Bling Fire with other popular NLP libraries, Bling Fire shows **10X faster** speed in tokenization task

| System   | Avg Run Time (Second Per 10,000 Passages) |
|------------|---------------------------------------|
| Bling Fire | 0.823                                 |
| SpaCy      | 8.653                                 |
| NLTK       | 17.821                                |

See more at [benchmark wiki](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461df7d8315e73cf5e028c5f4349219acc16b9c7029cef02faeb074475aa53265f8a91935e621e14eee9793fee16f5e608)

## Getting Started

If you simply want to use it in Python, you can install the latest release using [pip](http://u.720life.cn/g/14bf35e3dea6f35fc907085b98609be30c29db094680f48a6cd4d49568181dce):

`pip install -U blingfire`


## Examples
### 1. Python example, simple tokenizer with default model:
```python
from blingfire import *
text = 'This is the Bling-Fire tokenizer'
output = text_to_words(text)
print(output)
```

Expected output:
```
This is the Bling - Fire tokenizer
```


### 2. Python example, load a custom model for a simple tokenizer: 

```python
from blingfire import *

# load a custom model from file
# h = load_model(os.path.join(os.path.dirname(blingfire.__file__), "wbd_chuni.bin"))
h = load_model("./wbd_chuni.bin")

text = 'This is the Bling-Fire tokenizer. 2007年9月日历表_2007年9月农历阳历一览表-万年历'

# custom model output
print(text_to_words_with_model(h, text))

# default model output
print(text_to_words(text))

free_model(h)
```

Expected output:
```
This is the Bling - Fire tokenizer . 2007 年 9 月 日 历 表 _2007 年 9 月 农 历 阳 历 一 览 表 - 万 年 历
This is the Bling - Fire tokenizer . 2007年9月日历表_2007年9月农历阳历一览表 - 万年历
```


### 3. Python example, calling BERT BASE tokenizer compiled as one finite-state machine
On one thread, it works 14x faster than orignal BERT tokenizer written in Python. Given this code is written in C++ it can be called from multiple threads without blocking on global interpreter lock thus achiving higher speed-ups for batch mode.

```python
import os
import blingfire

s = "Эpple pie. How do I renew my virtual smart card?: /Microsoft IT/ 'virtual' smart card certificates for DirectAccess are valid for one year. In order to get to microsoft.com we need to type pi@1.2.1.2."

# one time load the model (we are using the one that comes with the package)
h = blingfire.load_model(os.path.join(os.path.dirname(blingfire.__file__), "bert_base_tok.bin"))
print("Model Handle: %s" % h)

# use the model from one or more threads
print(s)
ids = blingfire.text_to_ids(h, s, 128, 100)  # sequence length: 128, oov id: 100
print(ids)                                   # returns a numpy array of length 128 (padded or trimmed)

print(s+s)
ids = blingfire.text_to_ids(h, s+s, 128, 100)
print(ids)

# free the model at the end
blingfire.free_model(h)
print("Model Freed")
```

Expected output:
```
Model Handle: 2854016629088
Эpple pie. How do I renew my virtual smart card?: /Microsoft IT/ 'virtual' smart card certificates for DirectAccess are valid for one year. In order to get to microsoft.com we need to type pi@1.2.1.2.
[ 1208  9397  2571 11345  1012  2129  2079  1045 20687  2026  7484  6047
  4003  1029  1024  1013  7513  2009  1013  1005  7484  1005  6047  4003
 17987  2005  3622  6305  9623  2015  2024  9398  2005  2028  2095  1012
  1999  2344  2000  2131  2000  7513  1012  4012  2057  2342  2000  2828
 14255  1030  1015  1012  1016  1012  1015  1012  1016  1012     0     0
     0     0     0     0     0     0     0     0     0     0     0     0
     0     0     0     0     0     0     0     0     0     0     0     0
     0     0     0     0     0     0     0     0     0     0     0     0
     0     0     0     0     0     0     0     0     0     0     0     0
     0     0     0     0     0     0     0     0     0     0     0     0
     0     0     0     0     0     0     0     0]
Эpple pie. How do I renew my virtual smart card?: /Microsoft IT/ 'virtual' smart card certificates for DirectAccess are valid for one year. In order to get to microsoft.com we need to type pi@1.2.1.2.Эpple pie. How do I renew my virtual smart card?: /Microsoft IT/ 'virtual' smart card certificates for DirectAccess are valid for one year. In order to get to microsoft.com we need to type pi@1.2.1.2.
[ 1208  9397  2571 11345  1012  2129  2079  1045 20687  2026  7484  6047
  4003  1029  1024  1013  7513  2009  1013  1005  7484  1005  6047  4003
 17987  2005  3622  6305  9623  2015  2024  9398  2005  2028  2095  1012
  1999  2344  2000  2131  2000  7513  1012  4012  2057  2342  2000  2828
 14255  1030  1015  1012  1016  1012  1015  1012  1016  1012  1208  9397
  2571 11345  1012  2129  2079  1045 20687  2026  7484  6047  4003  1029
  1024  1013  7513  2009  1013  1005  7484  1005  6047  4003 17987  2005
  3622  6305  9623  2015  2024  9398  2005  2028  2095  1012  1999  2344
  2000  2131  2000  7513  1012  4012  2057  2342  2000  2828 14255  1030
  1015  1012  1016  1012  1015  1012  1016  1012     0     0     0     0
     0     0     0     0     0     0     0     0]
Model Freed
```

### 4. Example of using Bling Fire in your text classification task

[This notebook](/doc/Bling%20Fire%20Tokenizer%20Demo.ipynb) demonstrates how Bling Fire tokenizer helps in Stack Overflow posts classification problem.



## To create your own finite-state models

If you want to create your own tokenization or any other finite-state model, you need to compile the C++ tools first. Then use these tools to compile linugusitc resources from human readble format into binary finite-state machines.

1. [This Document](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461df7d8315e73cf5e028c5f4349219acc650437d4ffe5f89148d3fac7765c38037958f1d4b3edfc7bf8039f7a11143281f3767753c1626c7bac74430f795f1e6f) is an introduction into compilation of the C++ code and linguistic resources.
2. [Adding BERT-like tokenization model](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461df7d8315e73cf5e028c5f4349219acc650437d4ffe5f89148d3fac7765c3803813f18dca178de1569f3e02fdb77d1f9949ff51dc620db4e429bef9cab3cc7986346e1d2521b7b32913f41aab4e506cc) is describing how to add new tokenization model similar to BERT.

## Support for other languages
1. [Rust wrapper](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304608e923dd7d947bc431d53bfb19ac69d93325d2e838f3abc1e2c7a9b45a2d6e8d)
2. [Ruby wrapper](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304679c953bdbfdb433c89adaae5758e8af627149534ad9b17d1e724e767bfef0896)

## Supported Platforms

Bling Fire is supported for Windows, Linux and Mac (Thanks to Andrew Kane!)


## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](http://u.720life.cn/g/22e7b067064505b0b066921a690bc00f40fc6818092ae136d535683f62b36971e7b295096e982152791c6cc0acadce74).
For more information see the [Code of Conduct FAQ](http://u.720life.cn/g/22e7b067064505b0b066921a690bc00f40fc6818092ae136d535683f62b36971711354807af48475ed86c48f9fa10544f1669d39cb939aedffb8409517c51b11) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

### Working Branch

To contribute directly to code base, you should create a personal fork and create feature branches there when you need them. This keeps the main repository clean and your personal workflow out of sight.

### Pull Request

Before we can accept a pull request from you, you'll need to sign a  [Contributor License Agreement (CLA)](http://u.720life.cn/g/dbf1195f8a53209e138d24666db06636bcb5de726632aea000e7c7ecda759824bfb7b5ad62c66d1bf09138348b3edb64edc0f60c4eba76679b3861234d2fffc8). It is an automated process and you only need to do it once.

However, you don't have to do this up-front. You can simply clone, fork, and submit your pull-request as usual. When your pull-request is created, it is classified by a CLA bot. If the change is trivial (i.e. you just fixed a typo) then the PR is labelled with  `cla-not-required`. Otherwise, it's classified as  `cla-required`. In that case, the system will also tell you how you can sign the CLA. Once you have signed a CLA, the current and all future pull-requests will be labelled as  `cla-signed`.

To enable us to quickly review and accept your pull requests, always create one pull request per issue and [link the issue in the pull request](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469c49f51b20f0094d5f7626e6a438978c980b5327c1e2eefab7c361d289fd7e9be819504929eefaa294fd0f5e9ca62fb9) if possible. Never merge multiple requests in one unless they have the same root cause. Besides, keep code changes as small as possible and avoid pure formatting changes to code that has not been modified otherwise.

## Feedback

* Ask a question on [Stack Overflow](http://u.720life.cn/g/87bbd50441ad714fa4b3a92b06a39057c99d561856c3866c7b363085c26fdd7bd7e1aaeff83399dcba5d727731001ef442d79336ae386eb566261c02efcfe79d).
* File a bug in [GitHub Issues](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461df7d8315e73cf5e028c5f4349219acc4a9e20742a30ea4f33d4f0ff098e7ed8).

## Reporting Security Issues

Security issues and bugs should be reported privately, via email, to the Microsoft Security
Response Center (MSRC) at [secure@microsoft.com](mailto:secure@microsoft.com). You should
receive a response within 24 hours. If for some reason you do not, please follow up via
email to ensure we received your original message. Further information, including the
[MSRC PGP](http://u.720life.cn/g/1ea5282a9b2638a057cadb9385104924f2783771cef7d3961128e0ad29276d25d9f16acefd54ac5bd11d58a5dd3f6af3f8873228b105ecd4cc8a00f92ad5b9ff) key, can be found in
the [Security TechCenter](http://u.720life.cn/g/1ea5282a9b2638a057cadb9385104924f2783771cef7d3961128e0ad29276d254eb51ffc50c6874b52ab3a8da0a3fb2eef44511c65a2b024b535d4cb49b652af).

## License

Copyright (c) Microsoft Corporation. All rights reserved.

Licensed under the [MIT](LICENSE) License.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e69b24855800b9063a65da88d88e181683d69b8d86f7f5fd7a9eee8c70cb26ef3d1f6394609c28775128767a3b867fb06)
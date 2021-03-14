 

 

# Unity ML-Agents Toolkit (Beta)
[![docs badge](https://img.shields.io/badge/docs-reference-blue.svg)](docs/Readme.md)
[![license badge](https://img.shields.io/badge/license-Apache--2.0-green.svg)](LICENSE)

**The Unity Machine Learning Agents Toolkit** (ML-Agents) is an open-source
Unity plugin that enables games and simulations to serve as environments for
training intelligent agents. Agents can be trained using reinforcement learning,
imitation learning, neuroevolution, or other machine learning methods through a
simple-to-use Python API. We also provide implementations (based on TensorFlow)
of state-of-the-art algorithms to enable game developers and hobbyists to easily
train intelligent agents for 2D, 3D and VR/AR games. These trained agents can be
used for multiple purposes, including controlling NPC behavior (in a variety of
settings such as multi-agent and adversarial), automated testing of game builds
and evaluating different game design decisions pre-release. The ML-Agents
toolkit is mutually beneficial for both game developers and AI researchers as it
provides a central platform where advances in AI can be evaluated on Unity’s
rich environments and then made accessible to the wider research and game
developer communities.

## Features

* Unity environment control from Python
* 10+ sample Unity environments
* Support for multiple environment configurations and training scenarios
* Train memory-enhanced agents using deep reinforcement learning
* Easily definable Curriculum Learning scenarios
* Broadcasting of agent behavior for supervised learning
* Built-in support for Imitation Learning
* Flexible agent control with On Demand Decision Making
* Visualizing network outputs within the environment
* Simplified set-up with Docker
* Wrap learning environments as a gym
* Utilizes the Unity Inference Engine
* Train using concurrent Unity environment instances

## Documentation

* For more information, in addition to installation and usage instructions, see
  our [documentation home](docs/Readme.md).
* If you are a researcher interested in a discussion of Unity as an AI platform, see a pre-print of our [reference paper on Unity and the ML-Agents Toolkit](http://u.720life.cn/g/ef50ff7c3b5c85de9d07d6f28fa05754536685e0012e3480bcb9272298853950). Also, see below for instructions on citing this paper.
* If you have used an earlier version of the ML-Agents toolkit, we strongly
  recommend our [guide on migrating from earlier versions](docs/Migrating.md).

## Additional Resources

We have published a series of blog posts that are relevant for ML-Agents:

* Overviewing reinforcement learning concepts
  ([multi-armed bandit](http://u.720life.cn/g/5af81d3ea8b5b6729ecc7a1d0ed377ce93444a140257ef8bb24d0098555df120fad5c3d580f34b0082db8cae665c3eedcd71e69c6a5303d7c49522a4c5768d94028f6714914a2f5a7870c971d497cf39)
  and
  [Q-learning](http://u.720life.cn/g/5af81d3ea8b5b6729ecc7a1d0ed377ce93444a140257ef8bb24d0098555df120448b0db29aea483b4758d4f4ae880af593347dbfef8c3e0e0df74cc675b0784b8f138eda6ebb5a6d75314b238ebeae0402dc15bdd0f25e64d0dd9a52b8d15177)
* [Using Machine Learning Agents in a real game: a beginner’s guide](http://u.720life.cn/g/5af81d3ea8b5b6729ecc7a1d0ed377ce2aa4b27afa0cae69f0941f1529ef9b509a4f16bbe3068278a51ff1d2d29b9182516353839e0bc69a62854c046c39b533bd37791234553f93c170d34323a7cd60a34f9c88ef09b44c5aa9164a2abe6193f550ac65ba870f3304889e026b9f6bc9)
* [Post](http://u.720life.cn/g/5af81d3ea8b5b6729ecc7a1d0ed377ce375aa49466298d88ef7bf32fd471a5924c4a56bd27dc0bd106724f5591c10bd6bf5032e77a8f1bffc63dd4f36d7e35312f3f7c76fc439d7fc4e0cdeb33a5f1bfb94dd4dafc103905723443eca13de2ac)
  announcing the winners of our
  [first ML-Agents Challenge](http://u.720life.cn/g/32d694f5969ed4e6866535aa6c413e0d72e8afb0593b962e0934337918000f0d3fc0b8202751bec38b475a0ae2e5f4ee)
* [Post](http://u.720life.cn/g/5af81d3ea8b5b6729ecc7a1d0ed377ce375aa49466298d88ef7bf32fd471a592a6b2af3882e34873dc1981b6a4853dff6c4981db5a29f4a7566ef50ee87fe3fb7f4bcf6aa852896a86023ed9e7172d30)
  overviewing how Unity can be leveraged as a simulator to design safer cities.

In addition to our own documentation, here are some additional, relevant articles:

* [Unity AI - Unity 3D Artificial Intelligence](http://u.720life.cn/g/2bc656cc69a0e9056dae2ced9f817b904482df030ded26d1cdde0a20fff90c40d595d860ea6f9f752e274ad6f797c21b)
* [A Game Developer Learns Machine Learning](http://u.720life.cn/g/abbc89e9cdf4bcc0785a01a79ff9b4d12657b0827b183c85f4280c34dffd40b849505b803b895afdd0d8acc39f64bfb67ec1af21209dd1ae44d4ed59e8f7961ae91bef602b34cb8b63e98b130f80ef2521f0ad7b86a337de3b94064914bd9a7f)
* [Explore Unity Technologies ML-Agents Exclusively on Intel Architecture](http://u.720life.cn/g/5cf68d07a655cdcf94d83ccb5ed61446be5828c6d2ac53fb6ab29c5cedcb6d666e912eeb955444748a1c6243a2a0340feaaf580ecf1b7f5716390a441c5f364c40ae0e2b23c47270c5100451fcb06e02b5327816403512e9cb19e2b44e511f8a81617fa9cb053831c84023ef72de4e45)

## Community and Feedback

The ML-Agents toolkit is an open-source project and we encourage and welcome
contributions. If you wish to contribute, be sure to review our
[contribution guidelines](CONTRIBUTING.md) and
[code of conduct](CODE_OF_CONDUCT.md).

If you run into any problems using the ML-Agents toolkit,
[submit an issue](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a6abcba3e6a04c08159bf1207f9ef05feaa577bbe3439ac34f6f1f537e1647a19f1becd3a7141d913e30c330c1be0e01) and
make sure to include as much detail as possible.

Your opinion matters a great deal to us. Only by hearing your thoughts on the Unity ML-Agents Toolkit can we continue to improve and grow. Please take a few minutes to [let us know about it](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a6abcba3e6a04c08159bf1207f9ef05feaa577bbe3439ac34f6f1f537e1647a1404dd20365fdeb529c92fd969c476423). 


For any other questions or feedback, connect directly with the ML-Agents
team at ml-agents@unity3d.com. 

## Translations

To make the Unity ML-Agents toolkit accessible to the global research and
Unity developer communities, we're attempting to create and maintain
translations of our documentation. We've started with translating a subset
of the documentation to one language (Chinese), but we hope to continue
translating more pages and to other languages. Consequently,
we welcome any enhancements and improvements from the community.

* [Chinese](docs/localized/zh-CN/)

## License

[Apache License 2.0](LICENSE)

## Citation

If you use Unity or the ML-Agents Toolkit to conduct research, we ask that you cite the following paper as a reference:

Juliani, A., Berges, V., Vckay, E., Gao, Y., Henry, H., Mattar, M., Lange, D. (2018). Unity: A General Platform for Intelligent Agents. *arXiv preprint arXiv:1809.02627.* https://github.com/Unity-Technologies/ml-agents.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e7e49730b1a5c3c55a7a789fda972aeb23718f22c49df03a1d9bd108952b0863d68e5f98087200ed6e3e91f9154d64ef4)
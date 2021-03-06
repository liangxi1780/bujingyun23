# Neural Graph Collaborative Filtering
This is our Tensorflow implementation for the paper:

>Xiang Wang, Xiangnan He, Meng Wang, Fuli Feng, and Tat-Seng Chua (2019). [Neural Graph Collaborative Filtering](http://u.720life.cn/g/ef50ff7c3b5c85de9d07d6f28fa057544c8dead1144b3f392b2a0966f14f05ca61da21d07a738948352455c1283595ab  In SIGIR'19, Paris, France, July 21-25, 2019.

Author: Dr. Xiang Wang (xiangwang at u.nus.edu)

## Introduction
Neural Graph Collaborative Filtering (NGCF) is a new recommendation framework based on graph neural network, explicitly encoding the collaborative signal in the form of high-order connectivities in user-item bipartite graph by performing embedding propagation.

## Citation 
If you want to use our codes and datasets in your research, please cite:
```
@inproceedings{NGCF19,
  author    = {Xiang Wang and
               Xiangnan He and
               Meng Wang and
               Fuli Feng and
               Tat-Seng Chua},
  title     = {Neural Graph Collaborative Filtering},
  booktitle = {{SIGIR}},
  year      = {2019}
}
```
## Environment Requirement
The code has been tested running under Python 3.6.5. The required packages are as follows:
* tensorflow == 1.8.0
* numpy == 1.14.3
* scipy == 1.1.0
* sklearn == 0.19.1

## Example to Run the Codes
The instruction of commands has been clearly stated in the codes (see the parser function in NGCF/utility/parser.py).
* Gowalla dataset
```
python NGCF.py --dataset gowalla --regs [1e-5] --embed_size 64 --layer_size [64,64,64] --lr 0.0001 --save_flag 1 --pretrain 0 --batch_size 1024 --epoch 400 --verbose 1 --node_dropout [0.1] --mess_dropout [0.1,0.1,0.1]
```

* Amazon-book dataset
```
python NGCF.py --dataset amazon-book --regs [1e-5] --embed_size 64 --layer_size [64,64,64] --lr 0.0005 --save_flag 1 --pretrain 0 --batch_size 1024 --epoch 200 --verbose 50 --node_dropout [0.1] --mess_dropout [0.1,0.1,0.1]
```
Some important arguments:
* `alg_type`
  * It specifies the type of graph convolutional layer.
  * Here we provide three options:
    * `ngcf` (by default), proposed in [Neural Graph Collaborative Filtering](http://u.720life.cn/g/2b23035b14f2ba08b475b2ed92afa577f4b772c8de4d16dd04fbc28984e4a7cf427f2310ce391c59524a92d62caf763be8e1f90c5d2c06be3c3649681b6be38c  SIGIR2019. Usage: `--alg_type ngcf`.
    * `gcn`, proposed in [Semi-Supervised Classification with Graph Convolutional Networks](http://u.720life.cn/g/a6642a2fb806dee752f5fbb6b94cc92df8d55a0f2b554fabaa6db3b3b9d271c6c494bab8b3e6b7a7d15042dbb7ba5181  ICLR2018. Usage: `--alg_type gcn`.
    * `gcmc`, propsed in [Graph Convolutional Matrix Completion](http://u.720life.cn/g/5d85464883e1406a15cad85d5d52cd109cbaa78919fbeceef42a3112667d326cd8af44029b4834231e596384b4d800b732480409de38b8988054db8027fc8471066470069bd3d837ab211e567cc4f9b5  KDD2018. Usage: `--alg_type gcmc`.

* `adj_type`
  * It specifies the type of laplacian matrix where each entry defines the decay factor between two connected nodes.
  * Here we provide four options:
    * `ngcf` (by default), where each decay factor between two connected nodes is set as 1(out degree of the node), while each node is also assigned with 1 for self-connections. Usage: `--adj_type ngcf`.
    * `plain`, where each decay factor between two connected nodes is set as 1. No self-connections are considered. Usage: `--adj_type plain`.
    * `norm`, where each decay factor bewteen two connected nodes is set as 1/(out degree of the node + self-conncetion). Usage: `--adj_type norm`.
    * `gcmc`, where each decay factor between two connected nodes is set as 1/(out degree of the node). No self-connections are considered. Usage: `--adj_type gcmc`.

* `node_dropout`
  * It indicates the node dropout ratio, which randomly blocks a particular node and discard all its outgoing messages. Usage: `--node_dropout [0.1] --node_dropout_flag 1`
  * Note that the arguement `node_dropout_flag` also needs to be set as 1, since the node dropout could lead to higher computational cost compared to message dropout.

* `mess_dropout`
  * It indicates the message dropout ratio, which randomly drops out the outgoing messages. Usage `--mess_dropout [0.1,0.1,0.1]`.

## Dataset
We provide two processed datasets: Gowalla and Amazon-book.
* `train.txt`
  * Train file.
  * Each line is a user with her/his positive interactions with items: userID\t a list of itemID\n.

* `test.txt`
  * Test file (positive instances).
  * Each line is a user with her/his positive interactions with items: userID\t a list of itemID\n.
  * Note that here we treat all unobserved interactions as the negative instances when reporting performance.
  
* `user_list.txt`
  * User file.
  * Each line is a triplet (org_id, remap_id) for one user, where org_id and remap_id represent the ID of the user in the original and our datasets, respectively.
  
* `item_list.txt`
  * Item file.
  * Each line is a triplet (org_id, remap_id) for one item, where org_id and remap_id represent the ID of the item in the original and our datasets, respectively.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)
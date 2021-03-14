# rexgen_direct
Template-free prediction of organic reaction outcomes using graph convolutional neural networks

Described in [A graph-convolutional neural network model for the prediction of chemical reactivity](http://u.720life.cn/g/79431d774e2ff533ad0fa46e73544e2a24993eabd4544b5e23db88c25057cae96f7f3ad70650e2d7cdb4aa6e7bac7c0e13e61ee36bc9fb5d723c444cfd06a4f6b83cf955598de66aa5f0c0f05f2fbe5a)

# Dependencies
- Python (trained/tested using 2.7.6, visualization/deployment compatible with 3.6.1)
- Numpy (trained/tested using 1.12.0, visualization/deployment compatible with 1.14.0)
- Tensorflow (trained/tested using 1.3.0, visualization/deployment compatible with 1.6.0)
- RDKit (trained/tested using 2017.09.1, visualization/deployment compatible with 2017.09.3)
- Django (visualization compatible with 2.0.6)

_note: there may be some issues with relative imports when using Python 2 now; this should be easy to resolve by removing the periods preceding package names_

# Instructions 


### Looking at predictions from the test set
```cd``` into the ```website``` folder and start the Django app using ```python manage.py runserver```. Go to ```http://localhost:8000/visualize``` in a browser to use the interactive visualization tool

### Using the trained models
You can use the fully trained model to predict outcomes by following the example at the end of ```rexgen_direct/rank_diff_wln/directcandranker.py```

### Retraining the models
Look at the two text files in ```rexgen_direct/core_wln_global/notes.txt``` and ```rexgen_direct/rank_diff_wln/notes.txt``` for the exact commands used for training, validation, and testing. You will have to unarchive the data files after cloning this repo.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e9f456f56f1952859be75221a9c7a053731e790c3af672dda8fe52950203d0470b7d9b01e29ec9060bedf6e7503960099)
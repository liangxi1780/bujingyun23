#MyAndroidNote

    ```
public class A{

    A(){}
}
```

```java
public class A{

    A(){System.out.println("点击了地区");}
}
```

```
public class A{

    A(){System.out.println("点击了地区");}
}
```

 

    /**

     * 地区数据监听

     */

    private OnTreeNodeClickListener onTreeNodeClickListener = new OnTreeNodeClickListener() {

        @Override

        public void onClick(Node node, int position) {

    System.out.println("点击了地区");

            if ("-1".equals(node.getCode()) && "0".equals(node.getData_pid())) { // 第一级

                                                                                    // 不限

                node.setSelect(true);

                for (AreaBean areaBean : areaBeans) {

                    areaBean.setSelect(false);

                }

            } else if ("1".equals(node.getCode())

                    && "0".equals(node.getData_pid())) { // 选择中国

                node.setSelect(true);

                for (AreaBean areaBean : areaBeans) {

                    if ("-1".equals(areaBean.getCode())

                            && "0".equals(areaBean.getData_pid())) {

                        areaBean.setSelect(false);

                    } else if ("-1".equals(areaBean.getCode())

                            && node.getData_pid()

                                    .equals(areaBean.getData_pid())) {

                        areaBean.setSelect(true);

                    }

                }

            } else if ("1".equals(node.getData_pid())) { // 选择中国 下面的不限

                node.setSelect(true);

                if ("-1".equals(node.getCode())) {// 中国下面的省份 不限选择

                    for (AreaBean areaBean : areaBeans) {

                        if (!StringUtil.isStrEmpty(areaBean.getData_pid())

                                && !"0".equals(areaBean.getData_pid())) {// 排除

                                                                        // 地区

                                                                        // 不限

                                                                        // 中国

                            areaBean.setSelect(false);

                        }

                    }

                } else {// 中国下面的省份

                    node.setSelect(true);

                    for (AreaBean areaBean : areaBeans) {

                        if ("-1".equals(areaBean.getCode())

                                && "1".equals(areaBean.getData_pid())) {// 如何选择了省份

                                                                // 则不限的黄点去掉

                            areaBean.setSelect(false);

                        } else if ("-1".equals(areaBean.getCode())

                                && !StringUtil.isStrEmpty(areaBean

                                        .getData_pid())) {

                            if (areaBean.get_id() == 1) { // 去除第一个不限

                                areaBean.setSelect(false);

                            } else {

                                areaBean.setSelect(true);

                            }

                        } else if (node.getCode() == areaBean.getCode()) {

                            areaBean.setSelect(true);

                        }

                    }

                }

            } else {

                if (!StringUtil.isStrEmpty(node.getData_pid())

                        && !"0".equals(node.getData_pid())

                        && !"1".equals(node.getData_pid())) {

                    if ("-1".equals(node.getCode())) {// 最后一级 不限

                        node.setSelect(true);

                        for (AreaBean areaBean : areaBeans) {

                            if (node.getData_pid().equals(

                                    areaBean.getData_pid())) {

                                if ("-1".equals(areaBean.getCode())) {

                                    areaBean.setSelect(true);

                                } else {

                                    areaBean.setSelect(false);

                                }

                            }

                        }

                    } else {

                        boolean isSelect = false;

                        if (node.isSelect()) {

                            node.setSelect(false);

                        } else {

                            isSelect = true;

                            node.setSelect(true);

                        }



                        if (isSelect) {

                            for (AreaBean areaBean : areaBeans) {

                                if (node.getData_pid().equals(

                                        areaBean.getData_pid())) {

                                    if ("-1".equals(areaBean.getCode())) {

                                        areaBean.setSelect(false);

                                    } else if (node.getCode().equals(

                                            areaBean.getCode())) {

                                        areaBean.setSelect(true);

                                    }

                                }

                            }

                        } else {

                            boolean isSe = false;

                            for (AreaBean areaBean : areaBeans) {

                                if (node.getCode().equals(areaBean.getCode())) {

                                    areaBean.setSelect(false);

                                    break;

                                }

                            }



                            for (AreaBean areaBean : areaBeans) {

                                if (node.getData_pid().equals(

                                        areaBean.getData_pid())) {

                                    if (areaBean.isSelect()) {

                                        isSe = true;

                                        break;

                                    }

                                }

                            }



                            if (!isSe) {

                                for (AreaBean areaBean : areaBeans) {

                                    if (node.getData_pid().equals(

                                            areaBean.getData_pid())) {

                                        if ("-1".equals(areaBean.getCode())) {

                                            areaBean.setSelect(true);

                                            break;

                                        }

                                    }

                                }

                            }

                        }

                    }

                }

            }

            // 把当前的是否选择的值 更新到集合中

            for (int i = 0; i  (lv_screen,

                                getActivity(), areaBeans, 10);

                        lv_screen.setAdapter(mAdapter);

                        lv_screen.setSelection(area_position - 4);

                        mAdapter.setOnTreeNodeClickListener(onTreeNodeClickListener);

                    } catch (Exception e) {

                        e.printStackTrace();

                    }

                }

            } else {

                try {

                    mAdapter = new AreaTreeAdapter (lv_screen,

                            getActivity(), areaBeans, 10);

                    lv_screen.setAdapter(mAdapter);

                    lv_screen.setSelection(area_position - 4);

                    mAdapter.setOnTreeNodeClickListener(onTreeNodeClickListener);

                } catch (Exception e) {

                    e.printStackTrace();

                }



            }

        }

    };



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e53b285b928603f3d1094d50e908f89daca3330d68c0bcb6e14d66b176bc87e5e83e5ebef96685633138a0061758f43a0)
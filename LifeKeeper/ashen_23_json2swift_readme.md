# json2swift

auto convert json string to swift struct.[中文介绍](./Document/README_chs.md)

![demo](./Document/demo.gif)



***

- How to use?

   [OS X app](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba93bfaa3e6ae64005e305c7c4a2de7a9556)

  - 1. Input json to left

  - 2. click "convert=>"

  - 3. Copy the result
      Parameters statement:

    -  [ObjectMapper](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c55f1fb85da0c7d7738f42f736509bf6c43d76f259d662dc4a41521aa9d5f311): Simple JSON Object mapping written in Swift. If this is selected, result will auto add func mapping

    -  name: the name of the result, default is "Result"

    -  prefix: the prefix of each struct name, default is empty.


  [python script](./script)

   - 1. open Terminal, cd to Main.py

   - 2. Copy json string to File named "jsons.txt"

   - 3. Python3 Main.py

   - 4. ResultModel.swift is the result

   ![](./Document/terminal_ope.gif)

***

## Other
[CocoaPython](./json2Swift/CocoaPython.swift): a fast way to use python with Cocoa.
we can use CocoaPython.swift like this:
```swift
// python path
guard let aPath = Bundle.main.path(forResource: "Parse", ofType: "py") else { return }

// args: python accept paras
// block: complete block
let script = CocoaPython(scrPath: aPath, args: [""]) { [weak self] in
    print($0) // python's return
    print($1) // python's Error
}

script.spliPara = "$" // the multi results's split Character, if not set, all the results is in result[0]. 
script.runAsync()
// or script.runAsync(asyncComlete: false) // the complete block call in global async
// or script.runSync() // run in current thread
```

***
## Reference

- python 简单入门指北
- [Python教程](http://u.720life.cn/g/6c88affda63e6b8b2bb3146e299ec1e1f208c1826e5dc89fce367dd5ef6e3d9d5d17b20cc171f485785afd83ecbd8bd7ccdd8e73b609404a0defa976446d7c1d5be9d6bcf0ecc465bc8cea8393e5db2489b1a253e299a1df9056b3f7cc32b8ee)
- [Running a Python Script from Swift](http://u.720life.cn/g/38968394d76f9d8a416f5e8e3dbf877073146cb48d44d1289343b11f37f481197f30d6e4f494042a0bd7cc5be1f37d3f7eee44490768f72d8fdb4ab71aab6736)




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edd5f5f3e0afd2303e67036009f25e2be8844546daa190f0eb091ee88969ef347252ac123be823b7d5d127de91141b6ac)
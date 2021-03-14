[![npm version](https://badge.fury.io/js/onnxjs.svg)](https://badge.fury.io/js/onnxjs)
[![GitHub version](https://badge.fury.io/gh/Microsoft%2Fonnxjs.svg)](https://badge.fury.io/gh/Microsoft%2Fonnxjs)
[![ONNX.js CI - Windows CPU (Electron)]( )](https://dev.azure.com/onnxruntime/onnxjs/_build/latest?definitionId=24)
[![ONNX.js CI - Windows CPU (Node.js)]( )](https://dev.azure.com/onnxruntime/onnxjs/_build/latest?definitionId=20)
[![ONNX.js CI - Windows GPU (Chrome,Edge)]( )](https://dev.azure.com/onnxruntime/onnxjs/_build/latest?definitionId=22)
[![ONNX.js CI - Linux CPU (Node.js)]( )](https://dev.azure.com/onnxruntime/onnxjs/_build/latest?definitionId=5)
[![ONNX.js CI - BrowserStack (Suite0)]( )](https://dev.azure.com/onnxruntime/onnxjs/_build/latest?definitionId=17)

# ONNX.js

ONNX.js is a Javascript library for running ONNX models on browsers and on Node.js.

ONNX.js has adopted WebAssembly and WebGL technologies for providing an optimized ONNX model inference runtime for both CPUs and GPUs.

### Why ONNX models

The [Open Neural Network Exchange](http://u.720life.cn/g/3efb240b6f5f623bc362b715f018a884) (ONNX) is an open standard for representing machine learning models. The biggest advantage of ONNX is that it allows interoperability across different open source AI frameworks, which itself offers more flexibility for AI frameworks adoption. See [Getting ONNX Models](#Getting-ONNX-models).

### Why ONNX.js

With ONNX.js, web developers can score pre-trained ONNX models directly on browsers with various benefits of reducing server-client communication and protecting user privacy, as well as offering install-free and cross-platform in-browser ML experience.

ONNX.js can run on both CPU and GPU. For running on CPU, [WebAssembly](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b14848492c6553bd52bb7c59a8587071dd126a4062fab9d973ccc2d935b071ef5ea32b94f56c71c7af39585f8b371f7b0a429) is adopted to execute model at near-native speed. Furthermore, ONNX.js utilizes [Web Workers](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b14848492c6553bd52bb7c59a8587071dd1267fb2856419993d6af548deecc896cdd10d759a1bdfd2184664ee67e8150a7f552485f8e9a7e2c505e89f8411302cb616064029160e5557f1ab3cc8df7a1479bc) to provide a "multi-threaded" environment to parallelize data processing. Empirical evaluation shows very promising performance gains on CPU by taking full advantage of WebAssembly and Web Workers. For running on GPUs, a popular standard for accessing GPU capabilities - WebGL is adopted. ONNX.js has further adopted several novel optimization techniques for reducing data transfer between CPU and GPU, as well as some techniques to reduce GPU processing cycles to further push the performance to the maximum.

See [Compatibility](#Compatibility) and [Operators Supported](#Operators) for a list of platforms and operators ONNX.js currently supports.

### Benchmarks

Benchmarks have been run against the most prominent open source solutions in the same market. Below are the results collected for Chrome and Edge browsers on one sample machine (computations run on both CPU and GPU):

![alt text](./docs/perf-resnet50.png "Resnet50 Perf numbers")

> NOTE:
>
> 1. Keras.js doesn't support WebGL usage on Edge
> 2. Keras.js and TensorFlow.js doesn't support WebAssembly usage on any browser

> The specs of the machine that was used to perform the benchmarking is listed below:
>
> - OS: Microsoft Windows 10 Enterprise Insider Preview
> - Model: HP Z240 Tower Workstation
> - Processor: Intel(R) Core(TM) i7-6700 CPU @ 3.40GHz, 3401 Mhz, 4 Core(s), 8 Logical Processor(s)
> - Installed Physical Memory (RAM): 32.0 GB
> - GPU make / Chip type: AMD FirePro W2100 / AMD FirePro SDI (0x6608)
> - GPU Memory (approx.): 18.0 GB

### Demo

[ONNX.js demo website](http://u.720life.cn/g/9a8297f405f76a03e08835be6fd62d739331fcb8b086bc6b8cdd5d99d3e2fa8f98b6592c590bc96562fcea7ff7b9b7d8) shows the capabilities of ONNX.js. Check the [code](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a07efff1b47daec8e6c66a52b41d4b4117cf9803c1c110167c79e5e755189a71).

## Getting Started

There are multiple ways to use ONNX.js in a project:

### Using ` ` tag

This is the most straightforward way to use ONNX.js. The following HTML example shows how to use it:

```html
 
     

   
     
      
     
     
      // create a session
      const myOnnxSession = new onnx.InferenceSession();
      // load the ONNX model file
      myOnnxSession.loadModel("./my-model.onnx").then(() => {
        // generate model input
        const inferenceInputs = getInputs();
        // execute the model
        session.run(inferenceInputs).then(output => {
          // consume the output
          const outputTensor = output.values().next().value;
          console.log(`model output tensor: ${outputTensor.data}.`);
        });
      });
     
   
 
```

Refer to [browser/Add](./examples/browser/add) for an example.

### Using NPM and bundling tools

Modern browser based applications are usually built by frameworks like [Angular](http://u.720life.cn/g/8fd75c07dc4cbb8ed759f099d2fc1cb12e0c07c9d431022fbbad22913810d230), [React](http://u.720life.cn/g/4c49339db9b897b20ce9fa9b972593befe0bb743870912e185120b1d918dee79), [Vue.js](http://u.720life.cn/g/1c3db3fec6433a3fb191bb48af91f3bb055304712f0641658c814ca15fec0089) and so on. This solution usually builds the source code into one or more bundle file(s). The following TypeScript example shows how to use ONNX.js in an async context:

1. Import `Tensor` and `InferenceSession`.

```ts
import { Tensor, InferenceSession } from "onnxjs";
```

2. Create an instance of `InferenceSession`.

```ts
const session = new InferenceSession();
```

3. Load the ONNX.js model

```ts
// use the following in an async method
const url = "./data/models/resnet/model.onnx";
await session.loadModel(url);
```

4. Create your input Tensor(s) similar to the example below. You need to do any pre-processing required by
   your model at this stage. For that refer to the documentation of the model you have:

```javascript
// creating an array of input Tensors is the easiest way. For other options see the API documentation
const inputs = [
  new Tensor(new Float32Array([1.0, 2.0, 3.0, 4.0]), "float32", [2, 2])
];
```

5. Run the model with the input Tensors. The output Tensor(s) are available once the run operation is complete:

```javascript
// run this in an async method:
const outputMap = await session.run(inputs);
const outputTensor = outputMap.values().next().value;
```

More verbose examples on how to use ONNX.js are located under the `examples` folder. For further info see [Examples](./examples/README.md)

### Running in Node.js

ONNX.js can run in Node.js as well. This is usually for testing purpose. Use the `require()` function to load ONNX.js:

```js
require("onnxjs");
```

You can also use NPM package [`onnxjs-node`](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304691cd261e5429863ff1d8e681e15c4876789e0320b97defe85f7e748a9ab6fcc7), which offers a Node.js binding of [ONNXRuntime](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a07efff1b47daec8e6c66a52b41d4b41696111abf87cccc0536334dca586d77d).

```js
require("onnxjs-node");
```

See [usage](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304691cd261e5429863ff1d8e681e15c4876e9cf6c23327b2c681506914e43a1a9ee) of onnxjs-node.

Refer to [node/Add](./examples/node/add) for a detailed example.

## Documents

### Developers

For information on development ONNX.js, please check [Development](./docs/development.md)

For API reference, please check [API](./docs/api.md).

### Getting ONNX models

You could get ONNX models easily in multiple ways:

- Choose a pre-trained ONNX model from the [ONNX Model Zoo](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304686b6d1ee501645790b266047ec9354ec)
- Convert models from mainstream frameworks, e.g. PyTorch, TensorFlow and Keras, by following [ONNX tutorials](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ccd143599e850218b2c4a0ea51e0f153b0cc4eca65f66b7bbff7a4ae70899d7f)
- Use your data to generate a customized ONNX model from [Azure Custom Vision service](http://u.720life.cn/g/7f9564e5f558bc72a27cbe45da89f3838e2cd6dc01b92e58e0e861ee33282c2306adfb84b7c6ede184134c6b7c218e80bed1119ebfe75ce72b9c12dee91e4b632fa9bec3629ef0daa383108cdaaf697ca2b30775e1a46b12129e57b144255a25)
- [Train a custom model in AzureML](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046dddb98f4404a1d44ab8a24b70b35f877522ed8367d703384d00f89fa984d62072474d1c5c3423d6274c5816094aedaaa5a62aa3d3b18ff4f3e8fe3ef3ab93376) and save it in the ONNX format

Learn more about ONNX

- [ONNX website](http://u.720life.cn/g/3efb240b6f5f623bc362b715f018a884)
- [ONNX on GitHub](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e708ec5bd63f3c45965cafa16a57b578)

### Compatibility

#### Desktop Platforms

|    OS/Browser    |       Chrome       |        Edge        |      FireFox       |       Safari       |       Opera        |      Electron      |      Node.js       |
| :--------------: | :----------------: | :----------------: | :----------------: | :----------------: | :----------------: | :----------------: | :----------------: |
|    Windows 10    | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |         -          | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
|      macOS       | :heavy_check_mark: |         -          | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| Ubuntu LTS 18.04 | :heavy_check_mark: |         -          | :heavy_check_mark: |         -          | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |

#### Mobile Platforms

| OS/Browser |       Chrome       |        Edge        |      FireFox       |       Safari       |       Opera        |
| :--------: | :----------------: | :----------------: | :----------------: | :----------------: | :----------------: |
|    iOS     | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
|  Android   | :heavy_check_mark: | :heavy_check_mark: |    Coming soon     |         -          | :heavy_check_mark: |

### Operators

ONNX.js currently supports most operators in [ai.onnx](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465e74f322019ee1fd05836755c0c3e84cf72773969db94e3e47984f3d4280df3992997cc2b284b3ed6281f6e5c2b21c43) operator set v7 (opset v7). See [operators.md](./docs/operators.md) for a complete, detailed list of which ONNX operators are supported by the 3 available builtin backends (cpu, wasm, and webgl).

Support for [ai.onnx.ml](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465e74f322019ee1fd05836755c0c3e84ca2e501435cdbf6d27dd8844e175bd02732100e14aa5eb3e4d629790067eb3339) operators is coming soon. [operators-ml.md](./docs/operators-ml.md) has the most recent status of ai.onnx.ml operators.

## Contribute

We’d love to embrace your contribution to ONNX.js. Please refer to [CONTRIBUTING.md](./CONTRIBUTING.md).

## Thanks

Thanks to [BrowserStack](http://u.720life.cn/g/105be1d71c03be966dcc16f045e63bc3bdb50eaa6c55c6e84f024ff63f9453cd) for providing cross browser testing support.

## License

Copyright (c) Microsoft Corporation. All rights reserved.

Licensed under the [MIT](./LICENSE) License.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4a6942ae0c4060a353a04ae9f0c0064cc5afaab349b145f2d446d022052ddaa7efb7245716bb31352602962da25f23a0)

# Astro Programming Language
#### Work in Progress :construction:
Current Version: 0.1.15


![astro screenshot](https://github.com/astrolang/astro/blob/develop/media/images/astro_syntax.png)

### What is Astro?
Astro is a fun programming language designed for safe _high-performance applications_. It is essentially a statically-typed systems language that
- facilitates rapid prototyping,
- features high-level abstractions with zero overhead,
- ensures memory safety without a (tracing) Garbage Collector, and
- supports data-race-free concurrency.

### Why create yet another programming language?
The language creator had a set of requirements (listed above) not met by any language ([Rust](http://u.720life.cn/g/dbf1195f8a53209e138d24666db066363ca5e14e0b5b18c7831a8ca1f3cba8a0794db8409031ee14414afe0838742e55df77d5143414ce4eba0f87adfc67394f) comes close). Although, the project started as an educational effort, it later shaped into a language designed to meet those requirements.

SIMD, threads and direct access to Web APIs are planned for WebAssembly. These and other proposals for GPU Compute will make the web a desirable HPC target in the near future. Astro is, for this reason, designed for high-performance apps that are expected to run on the server or in the browser.

In order to match up with the expressiveness and productivity of dynamic programming languages, Astro adds full type inference, structural typing, and some other high-level abstractions that reduce boilerplate code commonly associated with statically-typed languages. It feels like a scripting language for the most part.

#### Python
```python
def times(a, b):
    sum = a
    for i in range(b):
        sum += sum
    return sum
```
#### Astro
```kotlin
fun times(a, b) {
    var sum = a
    for i in range(b) {
        sum += sum
    }
    return sum
}
```

Astro is supposed to be high-level enough to write python-like scripts but also low-level enough to write an operating system kernel. Therefore, it doesn't have a traditional [garbage collector](http://u.720life.cn/g/a0c0d47c518dd68b8be4c0da53cb0b92d85832bfd4a233c8ceae163a40bfc52d4f997deefbd752990d5fd890ca163f6600d432e859ab8a97486434f7df5706ed9070dbcd0e500c4d3bb3f8ec94f0e689) instead it relies on lifetime analysis at compile-time that free memory once they are no longer referenced.

Finally, seeing as CPU manufacturers are favoring multi-core design over transistor shrinkage, we believe making concurrency (and parallelism) a major aspect of the language development is beneficial to the type of applications that the language targets. Astro has built-in facilities for writing concurrent programs. A [CSP](http://u.720life.cn/g/a0c0d47c518dd68b8be4c0da53cb0b92d85832bfd4a233c8ceae163a40bfc52d6bc739d3591dee6b0e20b5d40e0c0b18842ce7d95cffcc2e76de2346cdd1708beabb1c0f2e09e8703eeca413162d9241)-based lightweight threading model, with the guarantee that the programs you write won't have data races.

### What is Astro automatic memory management like? Rust's or Swift's?
Neither.
Astro uses a special [Automatic Reference Counting](http://u.720life.cn/g/a0c0d47c518dd68b8be4c0da53cb0b92d85832bfd4a233c8ceae163a40bfc52d4792627c4c0168b6001ee46dc2ed585762f996b2ae30f1f2b412a32313dc9cc4) (ARC) system that automatically breaks reference cycles, so its unlike Swift's ARC which requires some special annotations in cases like that.
It's also unlike Rust current memory management model beacause it doesn't have a strict borrow chcker that requires some mental shift to get used to.

Astro simply stays out of your way; lets you write your code like you would in any other GC'ed language while still being memory safe.

### How close is Astro to being ready for use?
Not close. Astro is at its infancy, there are several tasks —which you can find [below](#tasks)— to complete before it becomes usable.

For now, Astro can compile its source code to ast format. It is not ready for even the simplest application. It is also currently implemented in Javascript and C++, however, the plan is to bootstrap the compiler (implement it in Astro) once it is sufficiently well-featured.

### Where can I read about the language?
There is no throrough documentation for the language yet since the main implementation is still in active development, however, you can find an up-to-date summary of language features [here](docs/language/summary.ast).

### How do I install it?
N/A

###    What are the important tasks to complete?
- [x] ~Improve project structure~
- [x] ~Add automated unit testing and coverage reports~
- [x] ~Redesign and remove certain inconsistencies in language syntax~
- [x] ~Complete lexer implementation~
- [ ] Complete parser implementation
- [ ] Implement semantic analysis phase
- [ ] Create ambiguity finders for inheritance, multiple dispatch, etc.
- [ ] Implement type inference and garbage collection using program flow analysis
- [ ] Add wasm code generation
- [ ] Incorporate incremental compilation
- [ ] Build REPL
- [ ] Create specialized error handler

### What are the technologies used?
- [wast2wasm](http://u.720life.cn/g/920c024f0b8c5aa5e32c4f88af4e6c96842ef10e50a388c1be8b108abc8ccaa1b7e30e8e1d7381066ef5d104e34e5529) - a tool for translating WebAssembly s-expression format to its binary-encoded format.

### Want to contribute to the project?
Please read the [code of conduct](CODE_OF_CONDUCT.md) and contribution [guidelines](CONTRIBUTING.md). We welcome your ideas and contributions.

### Do you have an unanswered question?
Please [open an issue](http://u.720life.cn/g/54145d0471d91890860f7f8463c030464f77f259e8c5d9bae9c60d501e2b54fec89a5ba2dfefcf90f5137b2b5f8cf932) and ask questions, offer to help, point out bugs or suggest features.

### Attributions
Astro logo made by [Freepik](http://u.720life.cn/g/7f1e0d28f8ce20e4916f5ff7cf1b31516c6c98fbceccf9c93b24bce31dad27f3)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e2aec4e8f52ff5cdc9fb8e5788d1f0dbb8b354691631c6a0e330b49848d05c2a6ea3dc6ac5a3f0c8c4ceece4e25a4fe79)
  RxSwift: ReactiveX for Swift
======================================

[![Travis CI](https://travis-ci.org/ReactiveX/RxSwift.svg?branch=master)](https://travis-ci.org/ReactiveX/RxSwift) ![platforms](https://img.shields.io/badge/platforms-iOS%20%7C%20macOS%20%7C%20tvOS%20%7C%20watchOS%20%7C%20Linux-333333.svg) [![pod](https://img.shields.io/cocoapods/v/RxSwift.svg)](https://cocoapods.org/pods/RxSwift) [![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage) [![Swift Package Manager compatible](https://img.shields.io/badge/Swift%20Package%20Manager-compatible-brightgreen.svg)](https://github.com/apple/swift-package-manager)

Rx is a [generic abstraction of computation](http://u.720life.cn/g/e890eb7ffa84f9513a1cd28c3149c56b44f0a5fa656278a2610a858b049d7d24) expressed through `Observable ` interface.

This is a Swift version of [Rx](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046125b952034ae75a43a8307f470de620051243b291ab8812eba570acd27aea258).

It tries to port as many concepts from the original version as possible, but some concepts were adapted for more pleasant and performant integration with iOS/macOS environment.

Cross platform documentation can be found on [ReactiveX.io](http://u.720life.cn/g/3c6d873642c48d33a3825c200ca388316f71c35c631249905dbaacb8bf68384c).

Like the original Rx, its intention is to enable easy composition of asynchronous operations and event/data streams.

KVO observing, async operations and streams are all unified under [abstraction of sequence](Documentation/GettingStarted.md#observables-aka-sequences). This is the reason why Rx is so simple, elegant and powerful.

## I came here because I want to ...

###### ... understand

* [why use rx?](Documentation/Why.md)
* [the basics, getting started with RxSwift](Documentation/GettingStarted.md)
* [traits](Documentation/Traits.md) - what are `Single`, `Completable`, `Maybe`, `Driver`, and `ControlProperty` ... and why do they exist?
* [testing](Documentation/UnitTests.md)
* [tips and common errors](Documentation/Tips.md)
* [debugging](Documentation/GettingStarted.md#debugging)
* [the math behind Rx](Documentation/MathBehindRx.md)
* [what are hot and cold observable sequences?](Documentation/HotAndColdObservables.md)

###### ... install

* Integrate RxSwift/RxCocoa with my app. [Installation Guide](#installation)

###### ... hack around

* with the example app. [Running Example App](Documentation/ExampleApp.md)
* with operators in playgrounds. [Playgrounds](Documentation/Playgrounds.md)

###### ... interact

* All of this is great, but it would be nice to talk with other people using RxSwift and exchange experiences.  [Join Slack Channel](http://u.720life.cn/g/88b2ddb9ca6a2824f602132949b7f6807c91d3d6510d0223fb3efbe3972dd073)
* Report a problem using the library. [Open an Issue With Bug Template](.github/ISSUE_TEMPLATE.md)
* Request a new feature. [Open an Issue With Feature Request Template](Documentation/NewFeatureRequestTemplate.md)
* Help out [Check out contribution guide](CONTRIBUTING.md)

###### ... compare

* [with other libraries](Documentation/ComparisonWithOtherLibraries.md).

###### ... understand the structure

RxSwift comprises five separate components depending on eachother in the following way:

```none
┌──────────────┐    ┌──────────────┐
│   RxCocoa    ├────▶   RxRelay    │
└───────┬──────┘    └──────┬───────┘
        │                  │        
┌───────▼──────────────────▼───────┐
│             RxSwift              │
└───────▲──────────────────▲───────┘
        │                  │        
┌───────┴──────┐    ┌──────┴───────┐
│    RxTest    │    │  RxBlocking  │
└──────────────┘    └──────────────┘
```

* **RxSwift**: The core of RxSwift, providing the Rx standard as (mostly) defined by [ReactiveX](http://u.720life.cn/g/41f537c76e0fca6d89f20fcdbe04b06cee19310ea436df1e74018e79fc3294a6). It has no other dependencies.
* **RxCocoa**: Provides Cocoa-specific capabilities for general iOS/macOS/watchOS & tvOS app development, such as Binders, Traits, and much more. It depends on both `RxSwift` and `RxRelay`.
* **RxRelay**: Provides `PublishRelay` and `BehaviorRelay`, two [simple wrappers around Subjects](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ceea70a7a582c6e056f0aa590ad9ce10f12189542f7e94b8f23c13b44a196cdc9e1e866b29ec188257d8c567b5208a8c0fcc7155d9eb4dba5bde6ae0b025941d1d44a118c43b061a565f03d507840e33). It depends on `RxSwift`. 
* **RxTest** and **RxBlocking**: Provides testing capabilities for Rx-based systems. It depends on `RxSwift`.

###### ... find compatible

* libraries from [RxSwiftCommunity](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304610832a754a19813de1ba0cd02c3ff4f65bd310072a3a99d3f2f2bae75c432389).
* [Pods using RxSwift](http://u.720life.cn/g/77a38086ed44384e91ae28cd5ee2cdc96bf4442338b53667487caee1fb2cb78ef6ef5a3fe3d8f06b942c2fd5ddc6d11c).

###### ... see the broader vision

* Does this exist for Android? [RxJava](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046cec389d5a60427431fa56bb03444f8e37522f01883d8c2e85902c78ac2d94b43)
* Where is all of this going, what is the future, what about reactive architectures, how do you design entire apps this way? [Cycle.js](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468ef5fbee1d66b39be01cd730b5b66b55a84a2be9501d22ae8e042fda37c96889) - this is javascript, but [RxJS](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046125b952034ae75a43a8307f470de6200432db6b8087ad7b2d231401d87517f12) is javascript version of Rx.

## Usage

 
   
     Here's an example 
     In Action 
   
   
     Define search for GitHub repositories ... 
       
   
   
       
let searchResults = searchBar.rx.text.orEmpty
    .throttle(.milliseconds(300), scheduler: MainScheduler.instance)
    .distinctUntilChanged()
    .flatMapLatest { query -> Observable&lt;[Repository]&gt; in
        if query.isEmpty {
            return .just([])
        }
        return searchGitHub(query)
            .catchErrorJustReturn([])
    }
    .observeOn(MainScheduler.instance)   
   
   
     ... then bind the results to your tableview 
   
   
       
searchResults
    .bind(to: tableView.rx.items(cellIdentifier: "Cell")) {
        (index, repository: Repository, cell) in
        cell.textLabel?.text = repository.name
        cell.detailTextLabel?.text = repository.url
    }
    .disposed(by: disposeBag)   
   
 


## Requirements

* Xcode 10.2
* Swift 5.0

For Xcode 10.1 and below, [use RxSwift 4.5](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ceea70a7a582c6e056f0aa590ad9ce10c299109d411ceee21fb098e48022a8582e3436cf0ad6a5e67453a2245b487b82).

## Installation

Rx doesn't contain any external dependencies.

These are currently the supported options:

### Manual

Open Rx.xcworkspace, choose `RxExample` and hit run. This method will build everything and run the sample app

### [CocoaPods](http://u.720life.cn/g/bef4970f9dd4e77416c3d6935ac46c309d6ed7d5078632de85efb71891bc06b056f5001e38c144886e5f280af0d6195300399ae9d63c74aa8277a4087eea3228)

```ruby
# Podfile
use_frameworks!

target 'YOUR_TARGET_NAME' do
    pod 'RxSwift', '~> 5'
    pod 'RxCocoa', '~> 5'
end

# RxTest and RxBlocking make the most sense in the context of unit/integration tests
target 'YOUR_TESTING_TARGET' do
    pod 'RxBlocking', '~> 5'
    pod 'RxTest', '~> 5'
end
```

Replace `YOUR_TARGET_NAME` and then, in the `Podfile` directory, type:

```bash
$ pod install
```

### [Carthage](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f8566d4c7bb2e79d97422e59628e897058997b6aacadc9ac11b35bdee60840f2)

Officially supported: Carthage 0.33 and up.

Add this to `Cartfile`

```
github "ReactiveX/RxSwift" ~> 5.0
```

```bash
$ carthage update
```

#### Carthage as a Static Library

Carthage defaults to building RxSwift as a Dynamic Library. 

If you wish to build RxSwift as a Static Library using Carthage you may use the script below to manually modify the framework type before building with Carthage:

```bash
carthage update RxSwift --platform iOS --no-build
sed -i -e 's/MACH_O_TYPE = mh_dylib/MACH_O_TYPE = staticlib/g' Carthage/Checkouts/RxSwift/Rx.xcodeproj/project.pbxproj
carthage build RxSwift --platform iOS
```

### [Swift Package Manager](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ea8233b24d1eaf6f2a0824e07cbf2a87288765c4f4ad19ef8f40fcf787854b32)

Create a `Package.swift` file.

```swift
// swift-tools-version:5.0

import PackageDescription

let package = Package(
  name: "RxTestProject",
  dependencies: [
    .package(url: "https://github.com/ReactiveX/RxSwift.git", from: "5.0.0")
  ],
  targets: [
    .target(name: "RxTestProject", dependencies: ["RxSwift", "RxCocoa"])
  ]
)
```

```bash
$ swift build
```

To build or test a module with RxTest dependency, set `TEST=1`.

```bash
$ TEST=1 swift test
```

### Manually using git submodules

* Add RxSwift as a submodule

```bash
$ git submodule add git@github.com:ReactiveX/RxSwift.git
```

* Drag `Rx.xcodeproj` into Project Navigator
* Go to `Project > Targets > Build Phases > Link Binary With Libraries`, click `+` and select `RxSwift-[Platform]` and `RxCocoa-[Platform]` targets

## References

* [http://reactivex.io/](http://u.720life.cn/g/3c6d873642c48d33a3825c200ca388316f71c35c631249905dbaacb8bf68384c)
* [Reactive Extensions GitHub (GitHub)](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046125b952034ae75a43a8307f470de62009705b61e3dfa8d236684f472c1fad8a8)
* [RxSwift RayWenderlich.com Book](http://u.720life.cn/g/6dcc4f51666176cc8beefa3c502e0bcb7eb18f210883590fa7ecfc4ba697225555c1f167a47155999d498a60ed589d37bcc739ea44cf35135ab836c91ff039067c0a4c4ae61948a0a309bcc28f3a9252)
* [Boxue.io RxSwift Online Course](http://u.720life.cn/g/93f74366dd20a00078a444bc75716ddfcc750ae7942c1336d0d019a5897a3a79b7285af0f3e858ae7a54c7249ba85356) (Chinese 🇨🇳)
* [Erik Meijer (Wikipedia)](http://u.720life.cn/g/aace67412d3c40f689b2c469b4f53b59d7f7b0202bb2c27965f98e896c752c07d5bb1ec0f61b98565cce5aaaeb0bdef17f35b995f1ec80852ea796b1805189fbeac79d1a64ec43a9b3cd31fb2cea20d8)
* [Expert to Expert: Brian Beckman and Erik Meijer - Inside the .NET Reactive Framework (Rx) (video)](http://u.720life.cn/g/e890eb7ffa84f9513a1cd28c3149c56b44f0a5fa656278a2610a858b049d7d24)
* [Reactive Programming Overview (Jafar Husain from Netflix)](http://u.720life.cn/g/2bc656cc69a0e9056dae2ced9f817b904482df030ded26d1cdde0a20fff90c40a6a5f1d78d4adae7c9470cbc0b97b3d5)
* [Subject/Observer is Dual to Iterator (paper)](http://u.720life.cn/g/cb30cb1e5986217144a6f39ca33dbcd5c853205702a4cabc9333da60d3fc547721d92b9df3b3166e7a823e362a600d6b0f30f663c5722acb05ec6a895c6673b332ad539cb261df3f1aac9c47595a9b27)
* [Rx standard sequence operators visualized (visualization tool)](http://u.720life.cn/g/9dea6554a9d0dd098e7a1dd0609c5c54db4eb5e1f245d3644ae745ee13a00ed5)
* [Haskell](http://u.720life.cn/g/aca3470af400f8736261e7011140fcba018694d48baf52ed48f9112c07af26b5)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e62e1147d6e8da7f229be951882ed7658514c940cdabdb47b7829c6d63861f0425e0061edc11ac953fbf3b55a0d19a22c)
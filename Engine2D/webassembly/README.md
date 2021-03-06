## WebAssembly 概述

WebAssembly 是一个可移植、体积小、加载快并且兼容 Web 的全新格式，是由主流浏览器厂商组成的 W3C 社区团体 制定的一个新的规范。

在目前，WebAssembly 需要使用 C++ 进行开发，通过 Emscripten SDK，将其发布为 .wasm 格式。使用这种格式运行的代码比传统的 .js 文件运行会有大幅性能提升。

## 浏览器支持

2017年3月，四大主流浏览器厂商宣布均已在最新的浏览器中支持 WebAssembly，分别为 Chrome 57、FireFox 52、Safari TP 及 Microsoft Edge 。

如果浏览器不支持 WebAssembly，也可以通过 Emscripten SDK 将 C++ 代码发布为 asm.js 格式，这种格式可以在所有浏览器中运行，并且性能仍然不低于传统的 .js 文件

目前在 Android Chrome 58 上存在一个 BUG，导致绝大部分 .wasm 程序会运行崩溃，请用户安装 Chrome 57 或者 Chrome 60 进行测试。

## 白鹭引擎与 WebAssembly

考虑到白鹭引擎的绝大部分开发者均为 JavaScript 开发者，白鹭引擎 5.0 的设计是将引擎核心作为一个 .wasm 库，上层提供 TypeScript API，开发者继续使用 TypeScript 进行开发，而非直接接触 C++ 逻辑。

![xxx](./image1.jpeg)


WebAssembly 的发布并不意味着白鹭引擎已经放弃了基于 4.x 的 JavaScript 版渲染器。接下来的至少半年内，我们会对 JavaScript 版本、WebAssembly 版本进行同等的支持力度，保证现有的基于 4.x 的游戏在不升级渲染器的情况下，仍然可以得到白鹭引擎的技术支持。


## 如何使用白鹭引擎 WebAssembly 版本

* 通过[这里](https://www.egret.com/products/engine.html)下载并安装白鹭引擎 5.0 的新启动器。
* 下载启动器后，安装引擎的 5.0 版本，并将其设置为默认版本
* 在项目管理中，点击创建新项目，项目类型选择 WebAssembly 示例项目
* 创建成功后，会自动启动 Egret Wing ，就可以直接运行这个项目了


## 开发者建议

* 目前由于 WebAssembly 在国内的运行环境尚未普及，所以所有用 WebAssembly 版本创建的项目，除了 Chrome 最新浏览器之外，均会回退到 asm.js 的模式，虽然如此，相比白鹭引擎 4.x 的 JavaScript 渲染器，性能也有很大的提升。
* 由于 WebAssembly 还具备着一些不确定性因素，强烈建议尝试使用此渲染器的开发者与白鹭引擎官方团队保持密切联系。WebAssembly 渲染器的独有 API 在每个小版本均可能进行调整，并不保证向下兼容。


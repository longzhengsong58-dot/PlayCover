# PVZ2 横屏窗口适配（实验分支）

这是 [PlayCover/PlayCover](https://github.com/PlayCover/PlayCover) 的个人 Fork，保留原项目 GPLv3 许可证与署名。

针对国服《植物大战僵尸2》4.2.8（`com.popcap.ios.chs.PVZ2`）启动后画面侧转、大面积留白的问题，新增一个可手动应用的横屏窗口配置。配套修改位于 [PlayTools Fork](https://github.com/longzhengsong58-dot/PlayTools)。

- 游戏设置 → 图像设置 → **应用植物大战僵尸2横屏兼容配置**，然后完全退出并重新启动游戏。
- 配置使用窗口尺寸作为屏幕尺寸，关闭启动旋转，以 1920×1080 的比例请求横屏窗口，超出屏幕时等比缩小。
- 新增的“启动时设置窗口尺寸”选项默认关闭；旧配置不会被自动覆盖。可通过关闭该选项并重新选择原来的分辨率模式回退。
- 该适配只改变显示设置，不修改游戏数据、账号、存档或网络设置。不包含游戏 IPA、资源或游戏代码。

**已验证范围**：在本机现有 PlayCover 3.1.0 中替换本分支编译的 AKInterface，启动国服 4.2.8，欢迎界面恢复正向且主要控件完整可见。已编译修改的 AKInterface，检查旧配置解码、配置应用和序列化。尚未完成修改后整套 PlayCover 的 Xcode 构建，也未验证关卡内玩法、其他系统或其他游戏版本。

**已知限制**：运行中切换原生全屏或大幅改变窗口尺寸，游戏仍可能保留启动时的渲染区域，出现黑边/位置异常。请使用启动后的窗口尺寸；若已切换全屏，退出全屏后完全退出并重新启动游戏。本分支目前不是完整的全屏适配，也不提供已经公证的安装包。

## 构建

需要完整 Xcode、Carthage 和 SwiftLint。`Cartfile` 与 `Cartfile.resolved` 固定到配套 PlayTools 修改提交。按下方原项目说明构建，并在 Xcode 中配置自己的签名团队；不要使用上游发布工作流所需的私有签名凭据。不能只使用原版 PlayTools，否则新增的启动尺寸选项不会生效。

---

<div id="top"></div>

‎<h1 align="center">[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![GPLv3 License][license-shield]][license-url]
[![Weblate](https://img.shields.io/weblate/progress/playcover?style=for-the-badge)](https://hosted.weblate.org/projects/playcover/playcover/)
</h1>



<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/PlayCover/PlayCover">
    <img src="images/logo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">PlayCover</h3>

  <p align="center">
    Run iOS apps and games on Apple Silicon Macs with mouse, keyboard and controller support.
    <br />
    <br />
    <a href="https://playcover.github.io/PlayBook">Documentation</a>
    ·
    <a href="https://discord.gg/RNCHsQHr3S">Discord</a>
    ·
    <a href="https://playcover.io/">Website</a>
  </p>
</div>

<!-- ABOUT THE PROJECT -->
## About The Project

Welcome to PlayCover! This software is all about allowing you to run iOS apps and games on Apple Silicon devices running macOS 12.0 or newer.

PlayCover works by putting applications through a wrapper which imitates an iPad. This allows the apps to run natively and perform very well.

PlayCover also allows you to map custom touch controls to keyboard, which is not possible in alternative sideloading methods such as Sideloadly. 

These controls include all the essentials, from WASD, camera movement, left and right clicks, and individual keymapping, similar to a popular Android emulator’s keymapping system called Bluestacks.

This software was originally designed to run Genshin Impact on your Apple Silicon device, but it can now run a wide range of applications. Unfortunately, not all games are supported, and some may have bugs.

Localisations handled in [Weblate](https://hosted.weblate.org/projects/playcover/).

![Fancy logo](./images/dark.png#gh-dark-mode-only)
![Fancy logo](./images/light.png#gh-light-mode-only)

<p align="right"><a href="#top">⬆️ Back to top️</a></p>

<!-- GETTING STARTED -->
## Getting Started

Follow the instructions below to get Genshin Impact, and many other games, up and running in no time.

### Prerequisites

At the moment, PlayCover can only run on Apple Silicon Macs. This means that only devices with M-series SoCs (eg. M1) are supported.

If you have an Intel Mac, you can explore alternatives like Bootcamp or emulators.

### Download

You can download stable releases [here](https://github.com/PlayCover/PlayCover/releases), or build from source by following the instructions in the Documentation.

### Documentation

To learn how to setup and use PlayCover, visit the documentation [here](https://playcover.github.io/PlayBook).

### Homebrew Cask
We host a [Homebrew](https://brew.sh) tap with the [PlayCover cask](https://github.com/PlayCover/homebrew-playcover/blob/master/Casks/playcover-community.rb). To install from it run:

```sh
brew install --cask PlayCover/playcover/playcover-community
```

To uninstall:
1. Remove PlayCover using `brew uninstall --cask playcover-community`;
2. Untap `PlayCover/playcover` with `brew untap PlayCover/playcover`.

<p align="right"><a href="#top">⬆️ Back to top️</a></p>



<!-- LICENSE -->
## License

Distributed under the GPLv3 License. See `LICENSE` for more information.



<!-- CONTACT -->
## Contact

Lucas Lee - playcover@lucas.icu

Depal - depal@playcover.io




<!-- ACKNOWLEDGMENTS -->
## Libraries Used

These open source libraries were used to create this project.

* [inject](https://github.com/paradiseduo/inject)
* [PTFakeTouch](https://github.com/Ret70/PTFakeTouch)
* [DownloadManager](https://github.com/shapedbyiris/download-manager)
* [DataCache](https://github.com/huynguyencong/DataCache)
* [SwiftUI CachedAsyncImage](https://github.com/bullinnyc/CachedAsyncImage)

* Thanks to @iVoider for creating such a great project!

<p align="right"><a href="#top">⬆️ Back to top️</a></p>



<!-- MARKDOWN LINKS & IMAGES -->
[contributors-shield]: https://img.shields.io/github/contributors/PlayCover/PlayCover.svg?style=for-the-badge
[contributors-url]: https://github.com/PlayCover/PlayCover/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/PlayCover/PlayCover.svg?style=for-the-badge
[forks-url]: https://github.com/PlayCover/PlayCover/network/members
[stars-shield]: https://img.shields.io/github/stars/PlayCover/PlayCover.svg?style=for-the-badge
[stars-url]: https://github.com/PlayCover/PlayCover/stargazers
[issues-shield]: https://img.shields.io/github/issues/PlayCover/PlayCover.svg?style=for-the-badge
[issues-url]: https://github.com/PlayCover/PlayCover/issues
[license-shield]: https://img.shields.io/github/license/PlayCover/PlayCover.svg?style=for-the-badge
[license-url]: https://github.com/PlayCover/PlayCover/blob/master/LICENSE

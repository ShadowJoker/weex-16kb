# Weex 适配 16KB PageSize 版本
## 简介
基于 Weex 原版，适配 Android 16KB PageSize 问题。

本项目是基于原版 Weex 项目 Fork 出来的。

## 主要改动点
- 升级 NDK 27，适配 16KB PageSize
- 配套工具链升级，Gradle配置修改
- C++ 代码修改，由于升级 NDK 27，部分老代码需要做调整

## 编译环境需求
- Java 17
- NDK 27.1.12297006
- CMake 3.22.1
- Gradle 8.10.2
- APG 8.7.2

## 编译步骤
1. 首先确保环境正确，各工具的版本严格符合编译环境说明
2. 进入到工程中 android 路径下（可以直接使用 AndroidStudio 打开这个路径，这是一个标准的Android工程）
3. 执行 `./gradlew assembleRelease` 编译项目
4. 编译完成后，在 android/sdk/build/outputs/aar 目录下会生成 aar 文件。
5. 在自己的项目中使用这个 AAR 作为 Weex SDK。

## 注意事项
- 如果集成 AAR 包以后，启动闪退，可能是由于 libc++shared.so 版本不一致问题。Weex AAR 包中包含了 libc++shared.so，需要确保 App 使用相同的版本和这个相同。

## 联系方式
- 邮箱：zhangpeng2023@travelsky.com.cn
- 欢迎沟通交流，请加微信：Shepard-N7，麻烦写一下备注

--------------
#### 以下是 Weex 原版的 README 说明
# Weex

A framework for building Mobile cross-platform UI.

[![Build Status](https://travis-ci.org/apache/incubator-weex.svg?branch=master)](https://travis-ci.org/apache/incubator-weex/)

## Distribution

> Support Android 4.1 (API 16), iOS 9.0+ and WebKit 534.30+.

| platform | status |
| -------- | ------ |
| Android | [![Maven Central](https://maven-badges.herokuapp.com/maven-central/io.weex/weex_sdk/badge.svg)](https://maven-badges.herokuapp.com/maven-central/io.weex/weex_sdk) |
| iOS | [![Pod version](https://badge.fury.io/co/WeexSDK.svg)](https://cocoapods.org/pods/WeexSDK) [![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage) |
| [Web](https://github.com/weexteam/weex-vue-render) | [![npm](https://badge.fury.io/js/weex-vue-render.svg)](https://www.npmjs.com/package/weex-vue-render) |

## Build from Source

[How To Build](./HOW-TO-BUILD.md)

## Contribution

Please read [Contributing Guide](./CONTRIBUTING.md) for more information.

## License

[Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0)

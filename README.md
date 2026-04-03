# Flutter 跨平台计数器

## 简介

一个带 **AppBar** 与加号按钮的计数器：点击后数字加一。工程为标准 Flutter 多平台模板，同一套 Dart 可跑在移动端、桌面与 Web，用来验证「一单仓多目标」是否配置正确。

## 快速开始

### 环境要求

Flutter SDK（stable 建议）。根据你要运行的目标，装好 Xcode、Android SDK 或 Chrome 等；用 `flutter doctor` 自检。

### 运行

在本 README 所在目录执行：

```bash
flutter pub get
flutter run
```

用 `flutter devices` 查看可用设备后，可加 `-d` 指定，例如 `flutter run -d macos`、`flutter run -d chrome`、`flutter run -d android`。

## 概念讲解

### 第一部分：`StatefulWidget` 与 `setState`

计数值存在 `State` 子类字段里，按钮回调里 `_increment` 调用 `setState`，框架重新执行 `build`，中心大字更新。

### 第二部分：跨平台交付物

同一 `lib/main.dart` 由各端嵌入器接管；`android/`、`ios/`、`web/` 等目录存放宿主与打包配置。发布时用 `flutter build <target>` 生成对应产物。

## 完整示例

界面结构见 `lib/main.dart`：`Scaffold` + `Column` + `ElevatedButton.icon`。

## 注意事项

- 首次切某平台可能下载依赖与工具链，用时较长属正常。
- Web 打包请关注资源体积与浏览器兼容性；移动端关注签名与权限。

## 完整讲解（中文）

这个 Demo 刻意保持「**无聊但扎实**」：没有花哨架构，只有 `setState`。无聊的好处是：你只要把它跑在安卓机、浏览器、macOS 窗口里都点得动，就说明工具链与工程骨架已经对齐。真正的产品再往上叠状态管理、依赖注入、CI 即可；若骨架歪了，叠再高也会塌。

# Flutter Multiplatform Counter Demo

## 简介

跨平台计数器演示，点击按钮数字加一。

## 支持平台

- iOS
- Android
- macOS
- Windows
- Linux
- Web

## 运行

```bash
cd flutter-multiplatform-counter-demo

# macOS
flutter run -d macos

# iOS Simulator
flutter run -d iphone

# Android
flutter run -d android

# Web
flutter run -d chrome
```

## 构建发布版

```bash
# 构建 macOS
flutter build macos

# 构建 iOS
flutter build ios

# 构建 Android ( APK )
flutter build apk

# 构建 Android ( App Bundle )
flutter build appbundle

# 构建 Windows
flutter build windows

# 构建 Linux
flutter build linux

# 构建 Web
flutter build web

# 构建所有平台
flutter build macos && flutter build ios && flutter build apk && flutter build appbundle && flutter build windows && flutter build linux && flutter build web
```

## 代码讲解

### 状态管理

```dart
class _CounterPageState extends State<CounterPage> {
  int _count = 0;

  void _increment() {
    setState(() {
      _count++;
    });
  }
}
```

- 使用 `StatefulWidget` 管理状态
- `setState()` 触发 UI 重建

### 界面布局

```dart
Scaffold(
  appBar: AppBar(title: const Text('Counter')),
  body: Center(
    child: Column(
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        Text('$_count', style: ...),
        ElevatedButton.icon(
          onPressed: _increment,
          icon: const Icon(Icons.add),
          label: const Text('Add'),
        ),
      ],
    ),
  ),
)
```

## 完整讲解（中文）

### Flutter 跨平台原理

Flutter 使用自研的 **Skia** 图形引擎直接绘制 UI，不依赖原生控件。通过 **Dart** 语言编写一次代码，编译到各平台原生应用或 Web。

### 代码结构

- `main.dart` - 应用入口和主页面
- `pubspec.yaml` - 项目配置和依赖

### Widget 简介

Flutter 中所有 UI 都是 Widget：
- `Scaffold` - 页面脚手架，提供 AppBar 和 body
- `Center` - 将子组件居中
- `Column` - 垂直排列子组件
- `ElevatedButton` - 凸起按钮
- `Text` - 文本显示
# Flutter 导航（Navigator + MaterialPageRoute）

## 简介

首页按钮 **`Navigator.push`** 到 `SecondPage`，第二页 `AppBar` 自带返回。演示命令式导航的最小闭环（未涉及命名路由、`go_router`）。

## 快速开始

### 环境要求

Flutter SDK。

### 运行

```bash
flutter pub get
flutter run
```

## 概念讲解

### 第一部分：`MaterialPageRoute`

`builder` 返回目标页 Widget，Material 风格页面带上进出场过渡。若要全屏对话框可用 `PageRouteBuilder` 自定义。

### 第二部分：`context` 从哪来

`onPressed` 闭包捕获外层 `build` 的 `context`，保证隶属于含 `Navigator` 的子树（通常在 `MaterialApp` 下）。

## 完整示例

见 `lib/main.dart`：`HomePage` → `SecondPage`。

## 注意事项

- 深层路由建议迁到 `go_router` 等方案，便于深链接与 Web。
- 传参可用构造函数参数或 `RouteSettings.arguments`。

## 完整讲解（中文）

导航的本质是 **在 Widget 树里换顶层或推入新页**。`Navigator.push` 像栈的 `push`，系统返回键或 `AppBar`  leading 会 `pop`。项目变大后命令式会显得乱，那时再引入声明式路由；本 Demo 先让你记住 push/pop 的手感。

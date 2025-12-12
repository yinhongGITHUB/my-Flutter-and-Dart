# Flutter 全面学习目录

## 一、Flutter 基础

### 1. Flutter 简介与架构原理

Flutter 是 Google 推出的跨平台 UI 框架，支持移动、Web、桌面开发。其核心是自带渲染引擎，UI 统一，性能接近原生。

### 2. 环境搭建与工具链

- 安装 Flutter SDK（https://flutter.dev/）
- 配置环境变量
- 安装 Android Studio/VS Code 等 IDE
- 配置 Android/iOS 模拟器或真机

### 3. 创建第一个 Flutter 应用

使用 `flutter create my_app` 创建项目，`flutter run` 启动。

### 4. 项目结构与主要文件说明

- lib/main.dart：入口文件
- pubspec.yaml：依赖和资源配置
- android/、ios/、web/、windows/ 等：各平台原生工程

### 5. 热重载与调试

支持热重载（Hot Reload），可快速预览 UI 变更。调试可用 DevTools、断点、日志等。

## 二、Dart 语言基础

### 1. Dart 基础语法

变量声明、数据类型、流程控制、运算符、函数定义等。

### 2. 面向对象编程

类、继承、抽象类、接口、泛型、mixin、扩展方法等。

### 3. 异步编程

Future、async/await、Stream、异常处理。

## 三、Flutter 核心组件

### 1. Widget 基础与分类

所有 UI 都是 Widget，分为 StatelessWidget（无状态）和 StatefulWidget（有状态）。

### 2. 布局组件

Container、Row、Column、Stack、Expanded、Flex、Align、Padding、SizedBox 等，用于构建各种布局。

### 3. 常用控件

Text、Image、Icon、Button（ElevatedButton、TextButton、IconButton）、ListView、GridView、Card、Form、TextField、Checkbox、Switch、Slider 等。

### 4. 自定义 Widget

通过组合和继承自定义自己的组件。

### 5. 主题与样式

Theme、ThemeData、TextStyle、Color、IconTheme、字体、暗黑模式等。

## 四、路由与导航

### 1. 路由基础与页面跳转

Navigator.push/pop 实现页面跳转和返回。

### 2. 命名路由与参数传递

通过 routes 配置命名路由，支持参数传递。

### 3. 路由动画与自定义过渡

可自定义页面切换动画（PageRouteBuilder、AnimatedSwitcher）。

## 五、状态管理

### 1. setState 基础

最简单的状态管理，适合局部刷新。

### 2. InheritedWidget 与 Provider

InheritedWidget 是 Flutter 原生跨组件通信机制，Provider 封装其用法，适合中小型项目。

### 3. 第三方状态管理

Provider、Riverpod、Bloc、GetX、MobX、Redux 等，适合大型项目和复杂场景。

### 4. 状态管理最佳实践

根据项目复杂度选择合适方案，保持数据流清晰、易维护。

## 六、网络与数据存储

### 1. 网络请求

http、dio 等库实现 GET/POST、文件上传下载、拦截器等。

### 2. JSON 解析与数据模型

手动解析或用 json_serializable 自动生成模型代码。

### 3. 本地存储

shared_preferences（键值对）、sqflite（SQLite 数据库）、hive（高性能 NoSQL）等。

### 4. 文件操作与缓存

文件读写、图片/数据缓存、临时目录等。

## 七、Flutter 进阶

### 1. 动画与交互

Animation、Tween、AnimatedBuilder、AnimatedWidget、Hero 动画、隐式动画等。

### 2. 手势识别与事件处理

GestureDetector、Listener、拖拽、滑动、点击、长按等。

### 3. 自定义绘制

CustomPainter、Canvas 绘图、路径、渐变、阴影等。

### 4. 国际化与本地化

i18n/l10n，支持多语言和地区格式。

### 5. 多媒体

音视频播放、图片选择、拍照、录音等。

### 6. 插件开发与原生集成

Platform Channel、MethodChannel 实现与原生 Android/iOS 通信，开发自定义插件。

### 7. 响应式编程与 StreamBuilder

StreamBuilder、FutureBuilder、RxDart 等响应式 UI。

## 八、测试与调试

### 1. 单元测试、Widget 测试、集成测试

test 包、flutter_test、integration_test，分别用于逻辑、UI、集成自动化测试。

### 2. Flutter DevTools 使用

性能分析、内存泄漏检测、UI 检查、调试工具。

### 3. 性能优化与内存分析

Widget 树优化、图片缓存、懒加载、内存泄漏排查。

### 4. 日志与错误处理

print、debugPrint、日志库、全局异常捕获。

## 九、项目工程与发布

### 1. 项目结构优化与模块化

分层结构、功能模块拆分、包管理。

### 2. 多环境配置

不同环境（开发/生产）配置切换，环境变量管理。

### 3. 持续集成与自动化

GitHub Actions、GitLab CI、Jenkins 等自动化测试与打包。

### 4. 打包与发布

支持 Android、iOS、Web、Windows、macOS、Linux 多端打包与发布。

### 5. 版本管理与升级

pubspec.yaml 依赖管理、Flutter 升级、迁移工具。

## 十、社区与资源

### 1. 官方文档与 API

https://flutter.dev/ 官方权威文档，API 参考。

### 2. 常用开源库与插件

如 provider、dio、get、cached_network_image、url_launcher、shared_preferences 等。

### 3. Flutter 社区与学习网站

Flutter 中文网、掘金、CSDN、Stack Overflow、GitHub 等。

### 4. 版本新特性与路线图

关注 Flutter 官网、官方博客，及时了解新特性和未来规划。

---

建议：按目录逐步学习，结合官方文档和实际项目练习，遇到新特性及时查阅资料。

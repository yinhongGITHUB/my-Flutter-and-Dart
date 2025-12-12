# Flutter 项目实战路线与练习建议

## 1. 基础入门项目

### 1.1 计数器/Hello World App

- 目标：熟悉 Flutter 项目结构、Widget 基本用法、热重载。
- 功能模块：
  - 显示文本 "Hello World" 或计数值
  - 按钮点击计数自增
  - Scaffold、AppBar、FloatingActionButton 基本用法
- 技术要点：
  - StatelessWidget、StatefulWidget 区别
  - setState 刷新界面
- 进阶建议：
  - 尝试自定义主题、添加多个按钮

### 1.2 简单表单输入

- 目标：掌握 TextField、Form、输入校验、状态管理（setState）。
- 功能模块：
  - 用户名、邮箱等输入框
  - 表单校验（必填、格式）
  - 提交后弹窗或页面展示结果
- 技术要点：
  - TextEditingController
  - Form、TextFormField、validator
- 进阶建议：
  - 支持重置、密码输入、自动聚焦

---

## 2. 列表与数据展示项目

### 2.1 待办事项/记事本 App

- 目标：掌握 ListView、增删查改、状态管理、持久化。
- 功能模块：
  - 事项列表展示、添加、编辑、删除
  - 标记完成、筛选、搜索
  - 数据本地存储（shared_preferences/hive）
- 技术要点：
  - ListView.builder、Dismissible
  - Dialog、SnackBar、AlertDialog
  - 状态管理（setState/Provider）
- 进阶建议：
  - 支持多端同步、云备份

### 2.2 新闻/商品列表 App

- 目标：掌握网络请求、JSON 解析、图片加载、下拉刷新、分页加载。
- 功能模块：
  - 从 API 获取数据，展示新闻/商品列表
  - 图片异步加载、缓存
  - 下拉刷新、上拉加载更多
- 技术要点：
  - http/dio 网络请求
  - FutureBuilder、ListView、CachedNetworkImage
- 进阶建议：
  - 支持收藏、详情页、分享

---

## 3. 多页面与路由项目

### 3.1 多页面导航 Demo

- 目标：掌握 Navigator 跳转、命名路由、参数传递。
- 功能模块：
  - 主页面、详情页、设置页
  - 页面跳转、返回、参数传递
- 技术要点：
  - Navigator.push/pop
  - routes 配置、onGenerateRoute
- 进阶建议：
  - 自定义路由动画、深度链接

### 3.2 登录注册流程

- 目标：掌握表单、路由、状态管理、简单权限控制。
- 功能模块：
  - 登录、注册、找回密码页面
  - 登录后跳转主页、退出登录
- 技术要点：
  - 表单校验、状态管理
  - 路由守卫、全局状态
- 进阶建议：
  - 接入第三方登录、验证码

---

## 4. 状态管理进阶项目

### 4.1 Provider/Riverpod 状态管理 Demo

- 目标：掌握 Provider/Riverpod 基本用法、全局状态管理。
- 功能模块：
  - 全局计数器、主题切换、用户信息管理
- 技术要点：
  - Provider/Riverpod 基本用法
  - ChangeNotifier、Consumer、Selector
- 进阶建议：
  - 多模块状态拆分、异步状态管理

### 4.2 Bloc/GetX 项目实战

- 目标：掌握 Bloc/GetX 状态管理、事件驱动开发。
- 功能模块：
  - 待办事项、购物车、复杂业务流程
- 技术要点：
  - BlocProvider、BlocBuilder、事件与状态
  - GetX 控制器、依赖注入、路由管理
- 进阶建议：
  - 结合网络请求、持久化

---

## 5. 动画与交互项目

### 5.1 动画效果 Demo

- 目标：掌握 AnimatedWidget、AnimatedBuilder、Hero、隐式动画。
- 功能模块：
  - 页面切换动画、控件渐变、缩放、滑动
- 技术要点：
  - AnimationController、Tween、AnimatedBuilder
  - Hero 动画、AnimatedContainer
- 进阶建议：
  - 复杂动画组合、交互动画

### 5.2 手势与自定义绘制

- 目标：掌握 GestureDetector、CustomPainter、Canvas。
- 功能模块：
  - 手势识别、绘图板、签名、拖拽排序
- 技术要点：
  - GestureDetector、Listener
  - CustomPainter、Canvas 绘图
- 进阶建议：
  - 结合动画、物理引擎

---

## 6. 网络与数据项目

### 6.1 天气/新闻查询 App

- 目标：掌握 http/dio 网络请求、数据模型、错误处理。
- 功能模块：
  - 输入城市/关键词，获取并展示数据
  - 网络异常处理、加载动画
- 技术要点：
  - http/dio、FutureBuilder
  - JSON 解析、模型转换
- 进阶建议：
  - 多城市管理、数据缓存

### 6.2 聊天/留言板 App

- 目标：掌握 WebSocket、实时通信、消息列表。
- 功能模块：
  - 消息发送、接收、历史记录
  - 聊天界面、消息气泡
- 技术要点：
  - WebSocket、StreamBuilder
  - 列表滚动、消息持久化
- 进阶建议：
  - 群聊、图片/语音消息

---

## 7. 项目工程与发布

### 7.1 多端适配与响应式布局

- 目标：掌握 MediaQuery、LayoutBuilder、响应式设计。
- 功能模块：
  - 适配手机、平板、Web 不同屏幕
  - 动态布局、字体缩放
- 技术要点：
  - MediaQuery、LayoutBuilder、Flexible、Expanded
- 进阶建议：
  - 国际化、本地化适配

### 7.2 打包与发布

- 目标：掌握打包流程、证书配置、发布到各平台。
- 功能模块：
  - Android/iOS/Web/桌面打包发布
  - 证书签名、渠道包
- 技术要点：
  - flutter build、flutter pub
  - 各平台打包配置
- 进阶建议：
  - 自动化 CI/CD、热更新方案

---

### 项目练习建议

- 每个项目建议先独立实现核心功能，再逐步引入第三方库和复杂特性。
- 多写注释，遇到问题多查官方文档和社区。
- 项目完成后，尝试重构、加测试、优化性能。
- 参考优秀开源项目，参与社区讨论。

如需某个项目的详细需求、代码结构或实现指导，请指定项目类型，我可帮你详细拆解和辅导！

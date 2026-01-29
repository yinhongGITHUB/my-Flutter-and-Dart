# Dart 全面学习目录

## 一、Dart 基础语法

### 1. 变量与常量

变量用于存储数据，可变。常量用于存储不可变的数据。

- `var`：自动类型推断，声明变量。
- `dynamic`：动态类型，变量类型可变。
- `final`：运行时常量，只能赋值一次。
- `const`：编译时常量，值在编译期确定。
  示例：

```dart
var name = 'Dart'; // 自动推断为String
dynamic anything = 123; // 可变类型
final age = 18; // 运行时常量
final：运行时常量。变量只能被赋值一次，但值是在程序运行时确定的。例如：final age = DateTime.now().year;。
const pi = 3.14; // 编译时常量
const：编译时常量。值在编译时就必须确定，且不可变。只能用于字面量或编译期可确定的表达式。例如：const pi = 3.14;。
```

注意：const 比 final 更严格，const 只能修饰不可变对象。

### 2. 数据类型

Dart 是强类型语言，常用类型有：

- int（整数）、double（浮点数）、num（数字类型父类）
- String（字符串）、bool（布尔）
- List（有序集合/数组）、Map（键值对集合/字典）、Set（无序唯一集合）
- Runes（Unicode 字符）、Symbol（符号）
  示例：

```dart
int a = 10;
double b = 2.5;
num c = 1.2;
String s = 'hello';
bool flag = true;
List<int> nums = [1,2,3];
Map<String, int> scores = {'Tom': 90};
Set<String> tags = {'a', 'b'};
Runes input = Runes('😊');
Symbol sym = #mySymbol;
```

### 3. 字符串插值与多行字符串

字符串插值可用 `$变量` 或 `${表达式}`，三引号 ''' 或 """ 表示多行字符串。

```dart
String name = 'Dart';
print('Hello, $name!');
print('1+1=${1+1}');
String multi = '''多行

```

### 4. 运算符

包括：

- 算术：+ - \* / ~/ %
- 关系：> < >= <= == !=
- 逻辑：&& || !
- 位运算：& | ^ ~ << >>
- 类型判断：is、as
- 赋值：=、??=、+=、-= 等
- 条件：?:
- 级联：..（连续操作同一对象）
- 空安全：??（空值合并）、?.（安全访问）、!（断言非空）
  示例：

```dart
int c = a + 2;
bool isAdult = age >= 18;
var result = flag ? 'yes' : 'no';
var d = null;
print(d ?? 'default');
List<String>? list;
print(list?.length); // 安全访问
```

### 5. 条件语句

用于流程控制。

- if/else：条件分支
- switch/case：多分支选择
- assert：断言，调试时验证条件
  示例：

```dart
if (a > 5) {
	print('大于5');
} else {
	print('不大于5');
}
switch (a) {
	case 1:
		print('一');
		break;
	default:
		print('其他');
}
assert(a != null);
```

### 6. 循环语句

用于重复执行。

- for：标准计数循环
- for-in：遍历集合
- while/do-while：条件循环
- break/continue：跳出或跳过循环
- 标签语句：嵌套循环跳转
  示例：

```dart
for (int i = 0; i < 3; i++) {
	print(i);
}
for (var n in nums) {
	print(n);
}
int i = 0;
while (i < 3) {
	i++;
}
outer:
for (int i = 0; i < 2; i++) {
	for (int j = 0; j < 2; j++) {
		if (j == 1) break outer;
	}
}
```

### 7. 注释与文档注释

注释用于说明代码。

- //：单行注释
- /\* \*/：多行注释
- ///：文档注释（用于生成 API 文档）
  示例：

```dart
// 这是单行注释
/* 这是
多行注释 */
/// 这是文档注释
```

### 8. 空安全（null safety）

Dart 2.12+ 默认启用空安全，变量默认不可为 null。可空类型用 ? 标记。
示例：

```dart
int? x = null;
String? s;
// s! 表示断言 s 不为 null，否则抛异常
```

### 9. 运算符优先级与结合性

运算符有优先级，决定表达式的计算顺序。结合性决定同优先级运算符的结合方向。
建议复杂表达式加括号明确顺序。

- 变量与常量（var、final、const）
- 数据类型（int、double、num、String、bool、List、Map、Set、Runes、Symbol）
- 字符串插值与多行字符串
- 运算符（算术、关系、逻辑、位、类型判断、赋值、条件、级联、空安全相关）
- 条件语句（if、else、switch、assert）
- 循环语句（for、while、do-while、for-in、break、continue、标签语句）
- 注释与文档注释
- 空安全（null safety）
- 运算符优先级与结合性

## 二、函数与面向对象

### 1. 函数定义与调用

Dart 中函数是一级对象，可以赋值、作为参数和返回值。

```dart
int add(int a, int b) {
	return a + b;
}
var sum = add(1, 2);
```

### 2. 可选参数、命名参数、默认参数

可选参数用 []，命名参数用 {}，可设置默认值。

```dart
void printInfo(String name, [int? age]) {}
void greet({String from = 'me', String to = 'you'}) {}
```

### 3. 匿名函数、箭头函数、闭包

匿名函数没有名字，箭头函数用于单表达式，闭包可捕获外部变量。

```dart
var f = (int x) => x * 2;
void run(Function fn) => fn();
Function makeAdder(int addBy) {
	return (int i) => i + addBy;
}
```

### 4. 递归与高阶函数

递归：函数调用自身。高阶函数：参数或返回值为函数。

```dart
int factorial(int n) => n <= 1 ? 1 : n * factorial(n - 1);
List<int> mapList(List<int> list, int f(int)) => list.map(f).toList();
```

### 5. 类与对象

类是对象的模板，对象是类的实例。

```dart
class Person {
	String name;
	int age;
	Person(this.name, this.age);
}
var p = Person('Tom', 20);
```

### 6. 构造函数（普通、命名、工厂、常量构造函数）

普通构造函数、命名构造函数、工厂构造函数、常量构造函数。

```dart
class Point {
	final int x, y;
	Point(this.x, this.y);
	Point.origin() : x = 0, y = 0;
	factory Point.fromJson(Map json) => Point(json['x'], json['y']);
	const Point.constant(this.x, this.y);
}
```

### 7. 静态成员、静态方法

用 static 修饰，属于类本身。

```dart
class Tool {
	static int count = 0;
	static void inc() => count++;
}
```

### 8. 继承、抽象类、接口、实现

继承用 extends，抽象类用 abstract，接口用 implements。

```dart
abstract class Animal {
	void speak();
}
class Dog extends Animal {
	@override
	void speak() => print('汪');
}
class Cat implements Animal {
	@override
	void speak() => print('喵');
}
```

### 9. mixin 混入

复用多个类的功能，避免多重继承。

```dart
mixin Logger {
	void log(String msg) => print(msg);
}
class Service with Logger {}
```

### 10. 运算符重载

可重载部分运算符。

```dart
class Vector {
	final int x, y;
	Vector(this.x, this.y);
	Vector operator +(Vector v) => Vector(x + v.x, y + v.y);
}
```

### 11. 泛型

支持类、方法泛型，提升复用性和类型安全。

```dart
List<T> reverse<T>(List<T> items) => items.reversed.toList();
```

### 12. 枚举（enum）

定义一组有限常量。

```dart
enum Color { red, green, blue }
```

### 13. 扩展方法（extension）

为已有类型添加新方法。

```dart
extension StringExt on String {
	String get hello => 'Hello, $this';
}
```

### 14. 元数据（注解）

用 @ 修饰，常用于标记、配置。

```dart
@deprecated
void oldFunc() {}
```

### 15. 反射（dart:mirrors，受限于平台）

可动态获取类型信息，Web/Flutter 不支持。

```dart
// import 'dart:mirrors';
// MirrorSystem mirrors = currentMirrorSystem();
```

## 三、Dart 进阶特性

### 1. 异步编程（Future、async/await、Stream）

Dart 支持异步操作，常用 Future、async/await、Stream。

```dart
Future<int> fetchData() async {
	await Future.delayed(Duration(seconds: 1));
	return 42;
}
void main() async {
	int data = await fetchData();
	print(data);
}
```

### 2. Stream 的广播、转换、订阅管理

Stream 用于处理一系列异步事件，可单订阅或广播。

```dart
Stream<int> countStream() async* {
	for (int i = 0; i < 3; i++) yield i;
}
countStream().listen((v) => print(v));
```

### 3. Future 的链式调用与错误处理

Future 支持 then/catchError/finally 链式调用。

```dart
Future.value(1)
	.then((v) => print(v))
	.catchError((e) => print('error'))
	.whenComplete(() => print('done'));
```

### 4. 异常处理（try-catch-finally、on、rethrow）

用于捕获和处理异常。

```dart
try {
	throw Exception('出错了');
} on Exception catch (e) {
	print(e);
} finally {
	print('结束');
}
```

### 5. isolate 并发模型（SendPort/ReceivePort、spawn、compute）

isolate 是 Dart 的多线程机制，数据通过消息传递。

```dart
import 'dart:isolate';
void entry(SendPort port) => port.send('hello');
void main() async {
	ReceivePort rp = ReceivePort();
	await Isolate.spawn(entry, rp.sendPort);
	print(await rp.first);
}
```

### 6. 库与包管理（import/export、part、pubspec.yaml）

import 导入库，export 导出，part 拆分文件，pubspec.yaml 管理依赖。

```dart
import 'dart:math';
export 'src/util.dart';
part 'src/part_file.dart';
```

pubspec.yaml 示例：

```yaml
dependencies:
	http: ^1.0.0
```

### 7. 发布 Dart 包到 pub.dev

需完善 pubspec.yaml，命令行执行 `dart pub publish`。

### 8. 本地依赖、Git 依赖、路径依赖

pubspec.yaml 支持多种依赖方式：

```yaml
dependencies:
	mylib:
		path: ../mylib
	another:
		git:
			url: git://github.com/xxx/xxx.git
```

## 四、工程与测试

### 1. 单元测试（test 包）

使用 test 包编写和运行单元测试。

```dart
import 'package:test/test.dart';
void main() {
	test('加法测试', () {
		expect(1 + 1, equals(2));
	});
}
```

### 2. mock 测试、集成测试

mock 测试用于模拟依赖，集成测试用于整体流程验证。

```dart
// mockito 示例
// import 'package:mockito/mockito.dart';
// class MockService extends Mock implements Service {}
```

### 3. 代码覆盖率分析

通过 `dart test --coverage=coverage` 生成覆盖率报告。

### 4. 静态分析工具（dart analyze、dartfmt、dart fix）

`dart analyze` 检查代码问题，`dart format` 格式化代码，`dart fix` 自动修复。

### 5. 代码规范与重构

遵循 Dart 官方规范（如 Effective Dart），合理命名、分层、解耦。

### 6. 性能优化（JIT/AOT、内存泄漏排查、调优）

JIT（开发时即时编译）、AOT（发布时预编译），可用 DevTools 进行性能分析和内存泄漏排查。

### 7. 代码混淆与安全加固

发布时可通过 dart2native、Flutter build 等命令开启混淆，提升安全性。

## 五、高级与底层原理

### 1. Dart 内存管理与垃圾回收

Dart 采用自动垃圾回收机制，开发者无需手动释放内存。对象不再被引用时会被自动回收。

### 2. isolate 原理与并发模型

isolate 是 Dart 的并发单元，每个 isolate 有独立内存空间，通过消息传递通信，避免多线程共享内存带来的问题。

### 3. Dart FFI（调用原生 C/C++ 代码）

FFI（Foreign Function Interface）允许 Dart 代码调用本地 C/C++ 库。

```dart
import 'dart:ffi' as ffi;
// 需配合动态库和绑定代码
```

### 4. 源码阅读与贡献

可通过 GitHub 查看 Dart/Flutter 源码，参与社区贡献，了解底层实现。

### 5. JIT/AOT 编译原理

JIT（Just-In-Time）即时编译，适合开发调试；AOT（Ahead-Of-Time）预编译，适合发布上线，提升性能和启动速度。

### 6. Dart VM 与运行时机制

Dart VM 负责执行 Dart 程序，管理内存、垃圾回收、JIT/AOT 编译等。Flutter 运行时也基于 Dart VM。

## 六、生态与应用

### 1. Dart Web（dart:html、dart:js、WebAssembly）

Dart 可编译为 Web 应用，支持操作 DOM（dart:html）、与 JS 互操作（dart:js）、WebAssembly。

```dart
import 'dart:html';
querySelector('#output')?.text = 'Hello, Dart Web!';
```

### 2. 与 Flutter 的集成与开发

Flutter 用 Dart 作为开发语言，可开发移动、桌面、Web 跨平台应用。

```dart
import 'package:flutter/material.dart';
void main() => runApp(const MyApp());
class MyApp extends StatelessWidget {
	const MyApp({super.key});
	@override
	Widget build(BuildContext context) {
		return const MaterialApp(home: Text('Hello Flutter'));
	}
}
```

### 3. Dart 在服务端（shelf、aqueduct、angel、rpc）

Dart 可用于开发服务端应用，常用框架有 shelf、aqueduct、angel、rpc。

```dart
import 'package:shelf/shelf.dart';
import 'package:shelf/shelf_io.dart' as io;
void main() async {
	var handler = const Pipeline().addHandler((req) => Response.ok('Hello'));
	await io.serve(handler, 'localhost', 8080);
}
```

### 4. 常用第三方库（http、json_serializable、provider、dio 等）

http：网络请求；json_serializable：自动生成 JSON 代码；provider：状态管理；dio：强大网络库。

```dart
import 'package:http/http.dart' as http;
void main() async {
	var res = await http.get(Uri.parse('https://dart.dev'));
	print(res.body);
}
```

### 5. 设计模式在 Dart 中的应用

常用设计模式如单例、工厂、观察者、策略等均可用 Dart 实现。

```dart
class Singleton {
	static final Singleton _instance = Singleton._internal();
	factory Singleton() => _instance;
	Singleton._internal();
}
```

### 6. 架构设计与模块化

推荐分层架构（如 MVC、MVVM、Clean Architecture），通过包和库实现模块化，提升可维护性。

### 7. 持续集成与自动化测试

可用 GitHub Actions、GitLab CI、Jenkins 等工具实现自动化测试与持续集成。
示例：.github/workflows/ci.yaml

```yaml
name: Dart CI
on: [push]
jobs:
	build:
		runs-on: ubuntu-latest
		steps:
			- uses: actions/checkout@v2
			- uses: dart-lang/setup-dart@v1
			- run: dart pub get
			- run: dart test
```

### 8. 版本管理与升级

通过 pubspec.yaml 管理依赖版本，使用 `dart pub upgrade` 升级依赖，关注 Dart/Flutter 官方发布的新版本。

## 七、社区与资源

### 1. 官方文档与 API 指南

Dart 官方文档（https://dart.cn/）提供权威语法、库、工具、API 说明，是学习和查阅的首选。

### 2. 社区资源与学习网站

常见社区有 Dart 中文网、Flutter 中文网、Stack Overflow、GitHub、掘金、CSDN 等，便于交流和获取实战经验。

### 3. Dart 各版本新特性追踪

可通过 Dart 官网、官方博客、GitHub Release Note 跟踪新版本特性，及时学习新语法和新能力。

### 4. 未来路线图

Dart 和 Flutter 官方会定期发布路线图，介绍未来发展方向和重点，建议关注官方博客和社区动态。

---

建议：按目录逐步学习，结合官方文档和实际项目练习，遇到新特性及时查阅资料。

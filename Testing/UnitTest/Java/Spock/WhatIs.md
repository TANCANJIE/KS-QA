# What Is Spock?
```md
Spock 由 Gradleware 首席工程师 Peter Niederwieser 于2008年创建。
```
```md
是运用于Java/Groovy语言编写的项目中一种规格表述式的测试框架。

规格化模型来源于一种编程思想，它认为程序在流程阶段上是可描述的：
例如对前置条件的设定描述，对执行流程的描述，对预期结果的描述。
```
```md
Spock之所以能在众多单测开中脱颖而出得益于groovy的漂亮语法与表述性测试用例的编程模式，将执行与预测分离。
它依然利用的是JUnit执行器，可平滑地集成到常见主流的IDE中，无缝接入已有的持续集成服务，
当然它的成功也脱离不了一些优秀测试框架，测试思想，编程语言提供的灵感。
框架的设计思路参考了JUnit，jMock，RSpec，Groovy，Scala，Vulcans……
```
## 特性
```md
测试代码使用基于groovy语言扩展而成的规范说明语言（specification language），而被测代码可以由Java编写。
通过JUnit runner调用测试，兼容绝大部分JUnit的运行场景（ide，构建工具，持续集成等）
内置mock框架以减少引入第三方框架。
可支持自定义测试件名称。
为创建测试代码预定义了行为驱动块（given:、when:、then:、expect:等）。
使用数据表格以减少数据结构的使用需求。
```

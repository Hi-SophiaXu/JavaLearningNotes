JUnit单元测试  

[B站 | Java教程 - Part-8-JUnit单元测试](https://www.bilibili.com/video/BV1u4411T78k/?p=2&spm_id_from=pageDriver&vd_source=c39989b23ea5eec50ec54b8201414961)

[GitHub | JavaLearningmanual]( https://github.com/Ziphtracks/JavaLearningmanual)

# 1.简介

**单元测试** ：
针对最小的功能单元编写测试代码（Java即方法）
测试驱动开发（TDD, Test-Driven Development）

**JUnit设计** ：

* *<u>TestCase</u>* : 一个表示一个测试。
* TestSuite : 一个包含一组TestCase，表示一组测试。
* TestFixture : 一个表示一个测试环境。
* TestResult : 用于收集测试结果。
* TestRunner : 用于运行测试。
* TestListener : 用于监听测试过程，收集测试数据。
* *<u>Assert</u>* : 用于断言测试结果是否正确（注意与Java关键字assert区分）。

# 2. 入门实践

```Java
import org.junit.Assert;
import org.junit.Test;
```

使用Assert断言：
| 常用方法 | 描述 |
| --- | --- |
| assertEquals(100, x)                      | 断言相等|
| assertArrayEquals({1,2,3},  x)         | 断言数组相等|
| assertEquals(3.1416, x, 0.0001)     | 断言浮点数相等，必须指定误差值delta|
| assertNull(x)                                  | 断言为null|
| assertTrue(x > 0);   assertFalse(x < 0)  | 断言为true或者false|
| assertNotEquals();   assertNotNull  |其他|

## 注意

1. 一个TestCase包含一组相关的测试方法；
2. 使用断言Assert测试结果；
3. 每个测试方法必须完全独立，即一个测试方法不能依赖于另一个测试方法，也不能预测JUnit执行方法的顺序；
4. 测试代码必须非常简单，要一眼能看出测试的逻辑；
5. 不能为测试代码再编写测试；
6. 测试需要覆盖各种输入条件，特别是边界条件；

# 3. 使用

## 1）使用Before和After

**场景**：
同一个单元测试内的多个测试方法

* 测试前需要初始化某些对象
* 测试后可能需要清理资源 fileInputStream.close();

**用途**：

* 在@Before方法中初始化测试资源
* 在@After方法中释放测试资源
* 使用@Before和@After可以保证：每个单个@Test方法执行前会创建新的XxxTest实例，且实例变量的状态不会传递给下一个@Test方法

**示例**：

```Java
public class SolutionTest {
    Solution solution;
    
    @Before
    public void setUp() {
        solution = new Solution();
    }
    
    @After
    public void tearDown() {
        solution = null;
    }
}
```

**原理**：

JUnit对于每个@Test方法：
1）实例化XxxxTest类
2）执行@Before方法
3）执行@Test方法
4）执行@After方法

## 2）异常测试

## 3）参数化测试

## 4）超时测试
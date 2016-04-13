---
title: Java8函数式编程学习笔记
---

###### 来源：《Java8函数式编程》--Richard Warburton

## 第2章 Lambda表达式
### 1、函数接口
#### 1.1、Java中重要的函数接口

接口 | 参数 | 返回类型 | 示例
---------|---------|----|-----
Predicate< T >|T|boolean|这张唱片已经发行了吗
Consumer< T,R >|T|void|输出一个值
Function< T,R >|T|R|获得Artist对象的名字
Supplier< T >|None|T|工厂方法
UnaryOperator< T >|T|T|逻辑非(!)
BinaryOperator< T > |(T,T)|T|求两个数的乘积(*)

#### 1.2、要点回顾
  - Lambda表达式是一个匿名方法，将行为像数据一样进行传递。
  - Lambda表达式的常见结构：BinaryOperator<Integer> add = (x,y) -> (x + y)。
  - 函数接口指仅具有单个抽象方法的接口，用来表示Lambda表达式的类型。

## 第3章 流

- 判断一个操作是惰性求值还是及早性求值很简单：只需要看它的返回值。如果返回值是Stream，那么是惰性求值；如果返回值是另一个值或空，那么就是及早求值。

### 3.1常用的流操作

#### 3.1.1、collect(toList())
  collect(toList())方法由Stream里的值生成一个列表，是一个及早求值操作。

#### 3.1.2、map
  如果有一个函数可以将一种类型的值转换成另一种类型，map操作就可以使用该函数，将一个流中的值转换成一个新的流。

#### 3.1.3、filter
  遍历数据并检查其中的元素时，可尝试使用Stream中提供的新方法filter。

#### 3.1.4 flatMap
  flatMap方法可用Stream替换值，然后将多个Stream连接成一个Stream。

  

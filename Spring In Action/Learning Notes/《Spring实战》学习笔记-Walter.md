# Spring 实战 #

----------

### **学习笔记——Walter**

## **主要包括三个方面：** ##
1. 核心的Spring
2. Spring应用程序的核心组件
3. Spring集成

## **主要涵盖：** ##
- Spring之旅
- 装配Bean
- 最小化Spring XML配置
- 面向切面的Spring
- 征服数据库
- 事务管理
- 使用Spring MVC构建Web应用程序
- 使用Spring Web Flow
- 保护Spring应用
- 使用远程服务
- 为Spring添加Rest功能
- Spring消息
- 使用JMX管理Spring Bean
- 其他Spring技巧

> JSR是Java Specification Requests的缩写，意思是Java 规范请求。是指向JCP(Java Community Process)提出新增一个标准化技术规范的正式请求。任何人都可以提交JSR，以向Java平台增添新的API和服务。JSR已成为Java界的一个重要标准。

## 第一部分 Spring的核心 ##
Spring的主要特性仅仅是依赖注入（DI）和面向切面编程（AOP）。
有助于解耦应用对象、使用Spring基于XML的配置，实现应用对象借助依赖注入保持松散耦合。

**第一章 Spring之旅**

**内容：**

- 探索Spring核心模块

- 解耦应用对象

- 使用AOP管理横切关注点

- Spring的Bean容器


JavaBean：

EJB：

POJO：POJO（Plain Ordinary Java Object）简单的Java对象，实际就是普通JavaBeans，是为了避免和EJB混淆所创造的简称。

Spring是一个开源框架，是为了解决企业级应用开发的复杂性而创建的，使用Spring可以让简单的JavaBean实现之前只有EJB才能完成的事情。
Spring的根本使命：简化Java开发。

为降低Java开发的复杂性，Spring采取了以下4中关键策略：

1. 基于POJO的轻量级和最小侵入性编程
2. 通过依赖注入和面向接口实现松耦合
3. 基于切面和惯例进行声明式编程
4. 通过切面和模板减少样板式代码

**依赖注入**(DI,dependency injection)

**耦合具有两面性**(two-headed beast):紧密耦合的代码难以测试，难以复用，难以理解；一定程度的耦合又是必须的。

通过依赖注入（DI），对象的依赖关系将由负责协调系统中各个对象的第三方组件在创建对象时设定。对象无需自行创建或管理它们的依赖关系——依赖关系将被自动注入到需要它们的对象中去。

**依赖注入的方式：**

- 构造注入:通过构造器传参注入

依赖注入最大的好处是松耦合。如果一个对象只通过接口（而不是具体实现或初始化的过程）来表明依赖关系，那么这种依赖就可以在对象毫不知情的情况下，用不同的具体实现进行替换。

——替换依赖最常用的方式：测试的时候使用mock

Mockito：[http://www.oschina.net/translate/mockito-a-great-mock-framework-for-java-development](http://www.oschina.net/translate/mockito-a-great-mock-framework-for-java-development)

**装配：**创建应用组件之间协作的行为。Spring有多重装配Bean的方式，采用XML配置通常是最常见的装配方式。

knights.xml：让BraveKnight接受一个SlayDragonQuest探险任务。

    <?xml version="1.0" encoding="UTF-8"?>
	<beans xmlns="http://www.springframework.org/schema/beans"
		xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
		xsi:schemaLocation="http://www.springframework.org/schema/beans
		http://www.springframework.org/schema/beans/spring-beans-3.0.xsd">
		<!-- Bean declarations go here -->
		<bean id="knight" class="com.springinaction.knights.BraveKnight">
			<constructor-arg ref="quest">
		</bean>
		<bean id="quest" 
			class="com.springinaction.knights.SlaDragonQuest">
		</bean>
	</beans>

----------
**基于切面进行声明式编程**

依赖注入让相互协作的软件组件保持松散耦合，而AOP编程允许你把遍布应用各处的功能分离出来行程可重用的组件。

**横切关注点 ：**







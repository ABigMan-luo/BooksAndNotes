Spring 的两个核心特性：依赖注入（dependency injection,DI),面向切面编程（aspect-orientid  pragramming,AOP)。

Spring的根本使命：简化java开发。

Spring 的4个关键策略：

 + 基于POJO的轻量级和最小侵入性编程；
 + 通过依赖注入和面向接口实现松耦合；
 + 基于切面和惯例进行声明式编程；
 + 通过切面和模板减少样板式代码。

很多框架强迫应用继承它们的类或者实现他们的接口从而导致应用与框架绑死。Spring不一样，最坏的场景是使用Spring注解，但它依然是POJO。Spring的非侵入式编程模型意味着这个类在Spring应用和非Spring应用一样起作用。

//1.1.2依赖注入   -----------------？

//1.1.3应用切面 ---------------------？





####装配Bean

创建应用对象之间协作关系的行为通常称为装配（wiring)，也是依赖注入（DI）的本质。
Spring配置的方法：
 + 在xml显示配置
 + 在JAVA中进行显示配置
 + 隐式的bean发现机制和自动配置

自动装配Bean:
 + 组件扫描（component scanning): Spring会自动发现应用上下文中所创建的Bean;
 + 自动装配（autowiring):Spring自动满足Bean之间的依赖

创建可以被发现的Bean：
 在类上使用@Component注解，表明该类会作为组件类，并告知Spring要为该类创建Bean。但是组件扫描并默认不开启，要显示配置Spring，命令去找@Component的注解，在使用的类上使用@ComponentScan 注解，启用组件扫描。但是只默认扫描与配置类相同的包的。使用XML配置组件扫描，<context:component-scan base-package="packagename"/>。
 注解@ContextConfiguration(classes = CDPlayerConfig.class)告诉需要在CDPlayerConfig类中加载配置，因为他包含了@ConponentScan。

为组件扫描的Bean命名：
 Spring为所有的应用上下文中Bean给一个ID。类名第一个字母变成小写。更改ID,@Component("IDname")。也可以用@Named("IDname")。

设置组件扫描的基础包：
 @ComponentScan("packagename");
 @ComponentScan(basePackages="packageName");
 设置多个包：
  @ComponentScan(basePackages={"name1","name2"});
  @ComponentScan(basePackageClasses={class1.class,class2.class});

通过为Bean添加注解实现自动装配：
 自动装配是让Spring自动满足Bean依赖的一种方法，在Spring应用上下文中寻找匹配某个Bean的其他Bean。要进行自动装配，可以使用@Autowired注解。在构造器上添加@Autowired时，表明Spring在创建该类的Bean时，会通过这个构造器实例化和传入一个特定的Bean类型。还可以用在Setter方法上，也可以用在任何方法上，Spring都是尝试满足方法参数上所声明的依赖。可以用@Inject来替代
 
通过Java代码装配Bean：
 
 





# Design-Pattern

设计模式之禅 记<br>

##1.Single Responsibility Principle,RSP<br>
	接口一定要做到单一职责，类的设计尽量做到只有一个原因引起变化。<br>

##2.Liskov Substitution Principle,LSP<br>
	2.1 如果子类不能完整地实现父类的方法，或者父类的某些方法在子类中已经发生“畸变”，则建议断开父子继承关系，采用依赖、聚集、组合等关系代替继承。<br>
	2.2 所以子类中方法的前置条件必须与超类中被覆写的方法的前置条件相同或者更宽松。<br>

##3.Dependence Inversion Principle,DIP<br>
	3.1 只要做到抽象依赖，即使是多层的依赖传递也无所畏惧！<br>
	3.2 对象的依赖关系有三种方式来传递<br>
		3.2.1 构造函数传递依赖对象<br>
		3.2.2 Setter方法传递依赖对象<br>
		3.2.3 接口声明依赖对象<br>
	3.3 最佳实践<br>
		3.3.1 每个类尽量都有接口或抽象类，或者抽象类和接口两者都具备<br>
		3.3.2 变量的表面类型尽量是接口或者是抽象类<br>
		3.3.3 任何类都不应该从具体类派生<br>
		3.3.4 尽量不要覆写基类的方法<br>
		3.3.5 结合里氏替换原则:使用接口负责定义public属性和方法，并且声明与其他对象的依赖关系，抽象类负责公共构造部分的实现，实现类准确的实现业务逻辑，同时在适当的时候对父类进行细化。<br>

##4.interface-segregation principles，ISP
	保证接口的纯洁性(接口要尽量小、接口要高内聚、 定制服务、接口设计是有限度的)

##5.Law of Demeter，LoD（Least Knowledge Principle，LKP）
	5.1 如果一个方法放在本类中，既不增加类间关系，也对本类不产生负面影响，那就放置在本类中。
	5.2 因为一个系统的成功不仅仅是一个标准或是原则就能够决定的，有非常多的外在因素决定，跳转次数越多，系统越复杂，维护就越困难，所以只要跳转不超过两次都是可以忍受的，这需要具体问题具体分析。

##6.Open-Closed Principle, OCP
	6.1 抽象约束
	6.2 数据（metadata）控制模块行为
		用来描述环境和数据的数据，通俗地说就是配置参数，参数可以从文件中获得，也可以从数据库中获得。通过扩展一个子类，修改配置文件，完成了业务变化，这也是采用框架的好处。
	6.3 制定项目章程 约定优于配置
	6.4 封装变化
		第一，将相同的变化封装到一个接口或抽象类中；第二，将不同的变化封装到不同的接口或抽象类中，不应该有两个不同的变化出现在同一个接口或抽象类中。
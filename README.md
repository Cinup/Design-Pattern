## 简介
设计模式描述了软件开发过程中若干重复出现的问题的解决方案。

这是一个设计模式的Java版本demo。

## 分类

### :star:创建型

[普通工厂](src/simplefactory)

:thinking:**严格来说，普通工并厂不是属于设计模式，因为它不符合开闭原则(在拓展Product时必须修改Factory中的方法)，但是工厂方法是对普通工厂的改进，可以放在一起对比，体会设计模式的开闭原则。**

![simplefactory](/img/simplefactory.png)

[工厂方法](src/factorymethod)

工厂方法模式为每个Product子类创建一个Factory类，这样在拓展Product的时候，只需要再拓展相应的Factory即可，不用对原有代码进行修改。

缺点:容易产生过多的平行的Product和Factory。

![factorymethod](/img/factorymethod.png)

[抽象工厂](src/abstractfactory)

工厂模式只考虑了子类水平方向上的拓展，当父类也在水平方向上扩展时，工厂方法就不再适用，需要使用抽象工厂模式了。

抽象工厂的每一个Factory都包含一组Product的组合，而这些Product都是来自于不同的父类。

缺点:任何子类可以都可以水平拓展，但是父类是无法拓展的。

![abstractfactory](/img/abstractfactory.png)

[生成器](src/builder)

生成器模式负责将对象的创建过程和装配过程分离，传统的创建对象方式是创建对象，同时也需要为其配置属性，一旦对象的属性发生改变时，就需要修改创建对象部分的代码。生成器模式就可以实现对修改的关闭。

缺点:当生成对象的属性数量发生变化时不再适用。

![builder](/img/builder.png)

原型

相当于复制粘贴，快速创建对象。	

缺点:需要考虑深浅拷贝的问题。

:thinking:**原型只要实现Java中的拷贝即可，深浅拷贝试情况而定，就不给出demo了**

[单例](src/singleton)

类的实例对象有且只有一个，可以避免大型对象的重复创建，节省系统资源。

![singleton](/img/singleton.png)

### :star:结构型

[适配器](/src/adapter)

适配器适用于不同接口之间的协作。

:thinking:类适配模式，适用于多继承，或者在Java中一个接口一个类。

![adapter_class](/img/adapter_class.png)

:thinking:对象适配模式，Java没有多继承，所以需要可以使用组合来实现适配。

![adapter_object](/img/adapter_object.png)

[代理](/src/proxy)

代理模式使用代理对象来完成透明间接的访问。

缺点:代理对象的接口要和目标对象接口一致。

代理模式和适配器模式的不同之处在于，适配对象和目标对象的接口不一样，适配器的目的是协调不同接口之间的协作，而代理模式代理对象和被代理对象实现了相同的接口，目的是通过代理对象来间接访问目标对象。

![proxy](/img/proxy.png)

[桥接](/src/bridge)

桥接模式将抽象与实现分离，使它们可以独立变化。它是用组合关系代替继承关系来实现，从而降低了抽象和实现这两个可变维度的耦合度。

![bridge](/img/bridge.png)

[享元](/src/flyweight)

享元模式运用共享技术来有効地支持大量细粒度对象的复用，就是缓存一部分对象，不用重复创建对象，直接返回缓存的对象即可。

缺点:需要考虑缓存对象的

![flyweight](/img/flyweight.png)

[组合](/src/composite)

组合模式一种部分-整体模式，它是一种将对象组合成树状的层次结构的模式，用来表示“部分-整体”的关系，使用户对单个对象和组合对象具有一致的访问性。

![composite](/img/composite.png)

[装饰](/src/decorator)

装饰模式能在不改变现有对象结构的情况下，动态地给该对象增加一些职责。

装饰模式和组成模式很相似，但是侧重点完全不同，组合模式重视对象的结构以及一致的访问性，而装饰模式更重要的是职责的变化。

![decorator](/img/decorator.png)

[外观](/src/facade)

外观模式通过为子系统提供一个访问接口来对子系统进行访问，依次来屏蔽子系统内部的细节，降低耦合度。

缺点:访问接口会膨胀。

![facade](/img/facade.png)

### :star:行为型

[职责链](/src/chainofresponsibility)

当一个消息请求需要被多个接收者处理时，如果为消息指定所有的接收者的方式来编码的话，当需要增加接收者就会违背开闭原则，因此可以使用职责链的模式，将所有的可能接受者以链表的形式连接起来，消息沿着链表传递。

![chainofresponsibility](/img/chainofresponsibility.png)

[命令](/src/command)

命令模式将一个请求封装为一个对象，使发出请求的责任和执行请求的责任分割开。这样两者之间通过命令对象进行沟通，这样方便将命令对象进行储存、传递、调用、增加与管理。

![command](/img/command.png)

解释器

:thinking:解释器类似于语法解析器，具体想不到使用的地方。

迭代器

:thinking:迭代器以统一的方式用于遍历不同的集合对象，详情可阅读Java Collection源码。

[中介者](/src/mediator)

中介者模式定义一个中介对象来封装一系列对象之间的交互，使原有对象之间的耦合松散，且可以独立地改变它们之间的交互。

![mediator](/img/mediator.png)

[备忘录](/sre)

备忘录模式在不破坏封装性的前提下，生成一个对象的内部状态，并在该对象之外保存这个状态，以便以后当需要时能将该对象恢复到原先保存的状态。

![memento](/img/memento.png)

[观察者](/src/observer)

观察者模式和职责链模式相似，都是在处理一对多的关系，当一个对象的状态发生改变时，所有依赖于它的对象都得到通知并被自动更新。

![observer](/img/observer.png)

[状态](/src/state)

对有状态的对象，把复杂的“判断逻辑”提取到不同的状态对象中，允许状态对象在其内部状态发生改变时改变其行为。

![state](/img/state.png)

[策略](/src/strategy)

策略模式定义了一系列算法，并将每个算法封装起来，使它们可以相互替换，且算法的变化不会影响使用算法的客户。

![strategy](/img/strategy.png)

[模板方法](/src/templatemethod)

模板方法定义一个操作中的算法骨架，而将算法的一些步骤延迟到子类中，使得子类可以不改变该算法结构的情况下重定义该算法的某些特定步骤。

[访问者](/src/visitor)

访问者模式将作用于某种数据结构中的各元素的操作分离出来封装成独立的类，使其在不改变数据结构的前提下可以添加作用于这些元素的新的操作，为数据结构中的每个元素提供多种访问方式。

![vistor](/img/vistor.png)

## 总结

:thinking:只从模式的UML图上看。
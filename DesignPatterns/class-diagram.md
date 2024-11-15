# 类图

UML（Unified Modeling Language，统一建模语言）中的类图（Class Diagram）是一种静态结构图，它用于展示系统中的类（class）、接口（interface）、协作（collaboration）以及它们之间的静态结构和关系。

## 画类图的好处

类图是面向对象设计中的重要工具，它的主要优点包括：

1. **提供系统的视觉表示**：类图提供了系统的静态视图，可以清晰地展示系统中的类以及它们之间的关系。这对于理解和解释系统的结构和行为非常有帮助。

2. **促进团队之间的沟通**：类图是一种通用的语言，可以被所有的开发人员理解。通过类图，团队成员可以更好地理解系统的设计，并在设计的基础上进行讨论和改进。

3. **帮助发现设计问题**：通过创建类图，我们可以在早期发现设计上的问题，比如类之间的耦合过度，或者职责分配不清等问题。这可以在实际编码之前就避免这些问题，提高开发效率。

4. **文档化系统**：类图可以作为系统的一部分文档，为未来的维护和开发提供参考。通过查看类图，新的开发人员可以更快地理解系统的结构和行为。

5. **辅助软件开发工具**：许多现代的软件开发工具，如IDE，都支持从类图生成代码，或者从代码生成类图。这可以帮助开发人员更快地进行开发，并保持代码和设计的一致性。

在学习设计模式的过程中，一定要自己画类图，这样可以更好地理解设计模式的实现原理，并且在实际开发中能够更好地应用设计模式。

## 类图三元素

1. **类（Class）**：类是类图的主要元素，通常用一个矩形表示。矩形分为三个部分：上部是类名，中部是属性，下部是方法。

2. **接口（Interface）**：接口在类图中以一个带有《接口名》标签的矩形表示，或者用一个带有接口名的圆柱表示。

3. **关系**：类图中的关系包括关联（Association）、聚合（Aggregation）、组合（Composition）、继承（Inheritance）、实现（Implementation）和依赖（Dependency）。

## 六种关系

### 解释

- **关联（Association）**：关联是类与类之间的一种链接，表示一个类知道另一个类的属性和方法。关联可以是单向的，也可以是双向的。关联在类图中以实线和箭头表示。

- **聚合（Aggregation）**：聚合是一种特殊的关联，表示"整体和部分"的关系，部分可以脱离整体而独立存在。聚合在类图中以空心菱形和实线表示。

- **组合（Composition）**：组合也是一种特殊的关联，表示"整体和部分"的关系，但部分不能脱离整体而独立存在。组合在类图中以实心菱形和实线表示。

- **继承（Inheritance）**：继承表示一个类（子类）继承另一个类（父类）的属性和方法。继承在类图中以空心三角形和实线表示。

- **实现（Implementation）**：实现表示一个类实现一个接口的方法。实现在类图中以空心三角形和虚线表示。

- **依赖（Dependency）**：依赖表示一个类的实例在方法内部使用到另一个类的实例。依赖在类图中以虚线和箭头表示。

### 单个说明

#### **1. 关联（Association）**：

**代码**
   ```cpp
   class Car {
       private Engine engine;
       public void start() {
           engine.start();
       }
   }

   class Engine {
       public void start() {
           // 启动发动机
       }
   }
   ```

**类图**

![](https://s2.loli.net/2024/11/15/26C7GNIktMRlEpj.png)


在这个例子中，`Car`类与`Engine`类之间存在关联关系。`Car`类包含一个`Engine`类型的成员变量`engine`，并且在`start`方法中使用了`engine`的`start`方法。

**注意：** 在这个例子中，`Engine`类是一个独立的类，它与`Car`类没有直接的关联关系。

#### **2. 聚合（Aggregation）**：
**代码**
   ```cpp
   class School {
       private List<Student> students;
       public void addStudent(Student student) {
           students.add(student);
       }
   }

   class Student {
       // 学生的属性和方法
   }
   ```
**类图**

![](https://s2.loli.net/2024/11/15/hH4ce3KJD1AZb2X.png)


在这个例子中，`School`类与`Student`类之间存在聚合关系。`School`类包含一个`List<Student>`类型的成员变量`students`，并且提供了一个`addStudent`方法用于添加学生。

**注意：** 在这个例子中，`Student`类是一个独立的类，它与`School`类没有直接的关联关系。

#### **3. 组合（Composition）**：
**代码**
   ```cpp
   class House {
       private List<Room> rooms;
       public House(List<Room> rooms) {
           this.rooms = rooms;
       }
   }

   class Room {
       // 房间的属性和方法
   }
   ```
**类图**

![](https://s2.loli.net/2024/11/15/RkESXdiHMG9YLcC.png)


在这个例子中，`House`类与`Room`类之间存在组合关系。`House`类包含一个`List<Room>`类型的成员变量`rooms`，并且在构造函数中初始化`rooms`。

**注意：** 在这个例子中，`Room`类是一个独立的类，它与`House`类没有直接的关联关系。

#### **4. 继承（Inheritance）**：
**代码**
   ```cpp
   class Animal {
       public void eat() {
           // 动物吃东西
       }
   }

   class Dog extends Animal {
       public void bark() {
           // 狗叫
       }
   }
   ```
**类图**

![](https://s2.loli.net/2024/11/15/NpsPoOeqjx3hnTF.png)


在这个例子中，`Dog`类继承自`Animal`类，因此`Dog`类具有`Animal`类的`eat`方法。

**注意：** 在这个例子中，`Dog`类继承自`Animal`类，因此`Dog`类具有`Animal`类的`eat`方法。

#### **5. 实现（Implementation）**：
**代码**
   ```cpp
   interface Drawable {
       public void draw();
   }

   class Circle implements Drawable {
       public void draw() {
           // 绘制圆形
       }
   }
   ```
**类图**

![](https://s2.loli.net/2024/11/15/A9I7LaySpr3kzvs.png)


在这个例子中，`Circle`类实现了`Drawable`接口，因此`Circle`类必须实现`draw`方法。

**注意：** 在这个例子中，`Circle`类实现了`Drawable`接口，因此`Circle`类必须实现`draw`方法。

#### **6. 依赖（Dependency）**：
**代码**
   ```cpp
   class Car {
       private Engine engine;
       public void start() {
           engine.start();
       }
   }

   class Engine {
       public void start() {
           // 启动发动机
       }
   }
   ```
   
**类图**

![](https://s2.loli.net/2024/11/15/EpZAXViW6c7CnUJ.png)


在这个例子中，`Car`类与`Engine`类之间存在依赖关系。`Car`类包含一个`Engine`类型的成员变量`engine`，并且在`start`方法中使用了`engine`的`start`方法。

**注意：** 在这个例子中，`Engine`类是一个独立的类，它与`Car`类没有直接的关联关系。

### 汇总说明
#### 代码

**c++**
```cpp
// B.h
class B {
public:
    B() { std::cout << "B created" << std::endl; }
    ~B() { std::cout << "B destroyed" << std::endl; }
    void display() { std::cout << "Displaying B" << std::endl; }
};

// C.h
class C {
public:
    C() { std::cout << "C created" << std::endl; }
    ~C() { std::cout << "C destroyed" << std::endl; }
    void display() { std::cout << "Displaying C" << std::endl; }
};

// D.h
#include "A.h"

class D {
    A* a_;
public:
    D(A* a) : a_(a) { std::cout << "D created" << std::endl; }
    ~D() { std::cout << "D destroyed" << std::endl; }
    void display() { std::cout << "Displaying D" << std::endl; }
};

// E.h
class F {
public:
    virtual void display() { std::cout << "Displaying F" << std::endl; }
};

class E : public F {
public:
    void display() override { std::cout << "Displaying E" << std::endl; }
};

// I.h
class I {
public:
    virtual void method() = 0;
};

// Implementation.h
#include "I.h"

class Implementation : public I {
public:
    void method() override { std::cout << "Implementation of method" << std::endl; }
};

// A.h
#include "B.h"
#include "C.h"
#include "D.h"

class A {
private:
    B* bPtr; // 关联：A不拥有B
    C* cPtr; // 聚合：A拥有C
    D* dPtr; // 组合：A拥有D

public:
    A() : dPtr(new D(this)) {
        cPtr = new C(); // A创建C，显示A拥有C
        bPtr = new B(); // A创建B，但A不拥有B
    }
    ~A() {
        delete cPtr; // A销毁时，销毁C，因为A拥有C
        delete dPtr; // A销毁时，销毁D，因为A拥有D
        // 不销毁bPtr，因为A不拥有B
    }

    void display() {
        std::cout << "Displaying A" << std::endl;
        bPtr->display(); // 使用关联对象B
        cPtr->display(); // 使用聚合对象C
        dPtr->display(); // 使用组合对象D
    }
};

// main.cpp
#include "A.h"

int main() {
    A a;
    a.display();
    return 0;
}
```
**c#**
```csharp
// B.cs
public class B {
    public B() { Console.WriteLine("B created"); }
    public ~B() { Console.WriteLine("B destroyed"); }
    public void Display() { Console.WriteLine("Displaying B"); }
}

// C.cs
public class C {
    public C() { Console.WriteLine("C created"); }
    public ~C() { Console.WriteLine("C destroyed"); }
    public void Display() { Console.WriteLine("Displaying C"); }
}

// D.cs
public class D {
    private A a_;
    public D(A a) {
        a_ = a;
        Console.WriteLine("D created");
    }
    public ~D() { Console.WriteLine("D destroyed"); }
    public void Display() { Console.WriteLine("Displaying D"); }
}

// E.cs
public class F {
    public virtual void Display() { Console.WriteLine("Displaying F"); }
}

public class E : F {
    public override void Display() { Console.WriteLine("Displaying E"); }
}

// I.cs
public interface I {
    void Method();
}

// Implementation.cs
public class Implementation : I {
    public void Method() { Console.WriteLine("Implementation of method"); }
}

// A.cs
public class A {
    private B bPtr; // 关联：A不拥有B
    private C cPtr; // 聚合：A拥有C
    private D dPtr; // 组合：A拥有D

    public A() {
        dPtr = new D(this);
        cPtr = new C();
        bPtr = new B();
    }

    ~A() {
        cPtr = null;
        dPtr = null;
        // 不销毁bPtr，因为A不拥有B
    }

    public void Display() {
        Console.WriteLine("Displaying A");
        bPtr.Display(); // 使用关联对象B
        cPtr.Display(); // 使用聚合对象C
        dPtr.Display(); // 使用组合对象D
    }
}

// Program.cs
using System;

class Program {
    static void Main() {
        A a = new A();
        a.Display();
    }
}
```

#### 类图

![](https://files.mdnice.com/user/76367/b8d337df-b6a1-4a81-be24-89ffca073aeb.png)

在上面的示例中：

-   `A` 类与 `B` 类之间有一个使用关系（uses），表示 `A` 类使用了 `B` 类的对象。
-   `A` 类与 `C` 类之间有一个聚合关系（aggregates），表示 `A` 类聚合了 `C` 类的对象，但 `C` 类的对象可以独立于 `A` 类存在。
-   `A` 类与 `D` 类之间有一个组合关系（composes），表示 `A` 类组合了 `D` 类的对象，`D` 类的对象的生命周期依赖于 `A` 类。
-   `A` 类与 `E` 类之间有一个使用关系（uses），表示 `A` 类使用了 `E` 类的对象。
-   `E` 类继承自 `F` 类（extends），表示 `E` 类继承了 `F` 类的属性和方法。
-   `Implementation` 类实现了 `I` 接口（implements），表示 `Implementation` 类实现了 `I` 接口中定义的方法。


## 画类图工具推荐

### 其一：在线工具([processon](https://www.processon.com/))

网址：`https://www.processon.com/`

登陆软件后自己创建文件即可开始画图，非会员创建文件有数量限制，但对于类图绘制来说，一个文件就可以，效果如下：

![](https://s2.loli.net/2024/11/15/weHkZT4U9JMqrvF.png)


### 其二：markdown画图

在支持mermaid的markdown编辑器中即可实现类图的绘制，代码及效果如下：


```cpp
classDiagram
    Factory --|> ProductA: createProduct("A")
    Factory --|> ProductB: createProduct("B")
    class Factory{
        +createProduct(type: String): Product
    }
    class ProductA{
        +operation(): void
    }
    class ProductB{
        +operation(): void
    }
    ProductA --|> Product
    ProductB --|> Product
    class Product{
        +operation(): void
    }

```

![](https://s2.loli.net/2024/11/15/u8z9HpI1wTAfUrE.png)


# **ArrayList、LinkedList、Vector的区别**

## 概述

ArrayList、LinkedList、Vector都实现了List的接口。 

List，正如它的名字，表明其是有顺序的。当讨论List的时候，最好拿它跟Set作比较，Set中的元素是无序且唯一；List是有序的Collection，使用此接口能够精确的控制每个元素插入的位置。用户能够使用索引（元素在List中的位置，类似于数组下标）来访问List中的元素，这类似于Java的数组。

### ArrayList概述

```java
public class ArrayList extends AbstractList implements List, RandomAccess, Cloneable, Serializable
```



1. ArrayList实现了List接口，即ArrayList实现了可变大小的数组。它允许所有元素，包括null。
2. ArrayList是为可变数组实现的，当更多的元素添加到ArrayList的时候，它的大小会动态增大。它的元素可以通过get/set方法直接访问，因为ArrayList本质上是一个数组。
3. 每个ArrayList实例都有一个容量（Capacity），即用于存储元素的数组的大小。这个容量可随着不断添加新元素而自动增加，但是增长算法并没有定义。当需要插入大量元素时，在插入前可以调用ensureCapacity方法来增加ArrayList的容量以提高插入效率。
4. 注意ArrayList没有同步方法。如果多个线程同时访问一个List，则必须自己实现访问同步。一种解决方法是在创建List时构造一个同步的List：

### LinkedList概述

```java
public class LinkedList extends AbstractSequentialList implements List, Deque, Cloneable, Serializable
```



1. List 接口的链接列表实现。实现所有可选的列表操作，并且允许所有元素（包括 null）。LinkedList是为双向链表实现的，添加、删除元素的性能比ArrayList好，但是get/set元素的性能较差。
2. 除了实现 List 接口外，LinkedList 类还为在列表的开头及结尾 get、remove 和 insert 元素提供了统一的命名方法。这些操作允许将链接列表用作堆栈、队列或双端队列。此类实现 Deque 接口，为 add、poll 提供先进先出队列操作，以及其他堆栈和双端队列操作。
3. 所有操作都是按照双重链接列表的需要执行的。在列表中编索引的操作将从开头或结尾遍历列表（从靠近指定索引的一端）。
4. 注意LinkedList没有同步方法。如果多个线程同时访问一个List，则必须自己实现访问同步。一种解决方法是在创建List时构造一个同步的List：

### Vector概述

​	

```java
public class Vector extends AbstractList implements List, RandomAccess, Cloneable, Serializable
```



1. Vector和ArrayList几乎是一样的，区别在于Vector是线程安全的，因为这个原因，它的性能较ArrayList差。通常情况下，大部分程序员都使用ArrayList，而不是Vector，因为他们可以自己做出明确的同步操作。
2. Vector 类可以实现可增长的对象数组。与数组一样，它包含可以使用整数索引进行访问的组件。但是，Vector 的大小可以根据需要增大或缩小，以适应创建 Vector 后进行添加或移除项的操作。
3. 每个向量会试图通过维护 capacity 和 capacityIncrement 来优化存储管理。capacity 始终至少应与向量的大小相等；这个值通常比后者大些，因为随着将组件添加到向量中，其存储将按 capacityIncrement 的大小增加存储块。应用程序可以在插入大量组件前增加向量的容量；这样就减少了增加的重分配的量。


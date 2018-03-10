# Map、Set、List、Queue、Stack的特点与用法

### Collection接口

Collection 有两个子接口 List 和 Set。

**List**有三个实现类：LinkedList、ArrayList、Vector。

- ArrayList 是线程不安全的， Vector 是线程安全的，这两个类底层都是由数组实现的。
- LinkedList 是非线程安全的，底层是由链表实现的
- Stack类：继承自Vector，实现一个后进先出的栈。提供了几个基本方法，push、pop、peek、empty、search等。

**Set**有两个实现类：HashSet、TreeSet，其中HashSet又包含LinkedHashMap。

List允许有重复值，可通过下标索引来取值。

Set不允许重复值，通过游标来取值。

对于List，关心的是顺序，它保证维护元素特定的顺序，使用此接口能够精确的控制每个元素插入的位置。用户能够使用索引来访问List中的元素。

对于Set，只关心某元素是否属于Set，而不关心它的顺序。



### Map接口

Map接口有三个实现类：Hashtable、HashMap、TreeMap。

LinkedHashMap和WeakHashMap继承自HashMap，IdentifyHashMap继承自TreeMap。

- 对于Map，最大的特点是键值映射，且为一一映射，键不能重复，值可以，所以是用键来索引值。
- HashTable是线程安全的，不能存储null值，HashMap不是线程安全的，可以存储null值，但最多允许一个key为null
- Queue接口：提供了几个基本方法，offer、poll、peek等。已知实现类有LinkedList、PriorityQueue等。
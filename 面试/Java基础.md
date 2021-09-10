#### Java 8种数据类型

byte、char、short、int、double、float、long、boolean

### 集合

#### 1. List


​	有序、可重复的集合

- ##### ArrayList

   基于数组实现，初始容量：10

   - ###### 扩容机制

     计算出新的扩容数组的大小并实例化，将原有数组内容复制到新数组中去。默认情况下新数组的大小是原数组的1.5倍

     在调用 add() 方法时，首先判断是否可以容纳，如果可以直接添加到末尾，如果不可以先进行扩容再添加到末尾。

- ##### LinkedList

   双向链表，线程不安全

- ##### Vector

   基于数组实现，线程安全

- ##### Stack
   基于数组实现，是栈（FILO 先进后出），继承于Vector

#### 2. Set

无序、不重复的集合，最多有一个null元素。虽然无序但元素在Set集合中的位置是由HashCode决定的（从另一种意义上是固定的）

- ##### HashSet

  通过HashMap实现，不保证元素顺序（元素插入的顺序与输出的顺序不一致），允许使用null元素（仅能存放一个null元素）。

  通过HashMap存放元素，将元素存放在HashMap的Key中，Value统一使用一个Object对象。

- ##### LinkedHashSet

  继承HashSet，通过LinkedHashMap实现。有序、线程不安全。

  根据元素的HashCode决定元素的位置，但同时使用链表维护元素的顺序。

- ##### TreeSet

  通过TreeMap实现。有序、不重复、线程不安全的集合。红黑树（自平衡的排序二叉树）

  支持两种排序：自然排序（默认排序）和定制排序。

  通过compare或compareTo函数判断元素是否相等。compare通过判断两个对象id是否相等，如果相等则不会被加入到元素中。

#### 3. Queue

#### 4. Map

由键值对组成的集合。不能存在相同的key值。

- ##### HashMap

  JDK1.8之前由数组和链表组成。数组是HashMap的主体，链表主要是为了解决哈希冲突而存在的。

  JDK1.8之后，链表长度大于阈值（默认为8），将链表转化为红黑树（转化前先判断当前数组长度是否小于64，如果小于先进行数组扩容，而不是转化为红黑树）

  [HashMap源码分析-田小波](http://www.tianxiaobo.com/2018/01/18/HashMap-%E6%BA%90%E7%A0%81%E8%AF%A6%E7%BB%86%E5%88%86%E6%9E%90-JDK1-8/)

  初始容量initialCapacity：16，负载因子loadFactor：0.75，阈值threshold：容量*负载因子

  - 查找：即先定位键值对所在的桶的位置，然后再对链表或红黑树进行查找
  - 

- ##### LinkedHashMap

  继承自HashMap，在HashMap实现的基础上增加了一条双向链表，使得上面的结构可以保持键值对的插入顺序。同时通过对链表进行相应的操作，实现了访问顺序相关逻辑。

#### 5. 集合问题

- ##### ArrayList和LinkedList区别

  - 都是线程不安全的

  - 底层实现不一样

    ArrayList底层使用数组实现、LinkedList底层使用链表实现

  - 插入和删除的时间复杂度不一样

    - ArrayList使用数组存储，所以插入和删除元素的时间复杂度受元素位置的影响。在列表尾部插入时间复杂度是**O(1)**，在列表其他位置插入时间复杂度是**O(n-i)**。
    - LinkedList使用链表存储，所以时间复杂度都是近似**O(1)**

  - ArrayList支持快速随机访问，LinkedList不支持

    ArrayList实现了RandmoAccess接口，所以支持

  - 内存空间占用不一样

- ##### HashMap和HashTable区别

  - HashTable是线程安全，HashMap是线程不安全的
  - HashTable不允许插入空值，HashMap允许插入空值

- ##### 线程安全的集合

  HashTable、ConcurrentHashMap、Vector、Stack

- ##### 线程不安全的集合

  HashMap、ArrayList、LinkedList、HashSet、TreeSet、TreeMap

### IO流

- 字节流读取文件
  - 使用FileInputStream读取文件
  - 使用InputStreamReader将字节流转为字符流
  - 使用BufferReader从缓冲区内将字符流信息打印出来
  - 调用BufferReader的close方法关闭
- 字符流读取文件
  - 使用FileReader将文件读取到缓冲区
  - 使用BufferReader从缓冲区内将字符流信息打印出来
  - 调用BufferReader的close方法关闭

- ##### 多线程
  
  - 继承Thread类
    - 创建Thread类的子类，重写run方法
    - 创建子类的实例，调用用start方法启用该线程
  - 实现Runnable接口
    - 创建Runnable接口的实现类，重写run方法
    - 创建实现类的实例，将该实例作为Thread类的target来创建Thread类对象
    - 调用Thread类的start方法
  
- ##### 异常

- ##### 反射

- ##### 三大特性

- ##### Java1.8 新特性
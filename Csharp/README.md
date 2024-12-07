# Csharp

## 数据结构

### 顺序存储和链式存储

> 常用数据结构 : **数组**，**栈**，**队列**，**链表**，**树**，**图**，**堆**，**散列表**

```c#
    线性表:一个线性表是n个具有相同特性的数据元素的有限序列
    1.线性表中的元素是同类型的，并且数量可以为零。
    2.元素之间存在一对一的关系。
    3.线性表是一个有序表，即其中的数据元素具有先后次序。

    顺序存储和链式存储增删改查的优缺点
    1.增:链式存储 计算上优于顺序存储(可以在任意位置高效的插入操作,只需改变指针,无需移动其他元素);
    2.删:链式存储 计算上优于顺序存储(可以高效地删除任意位置的节点,只需改变相关指针,无需移动其他元素);
    3.查:顺序存储 计算上优于链式存储(数组可以通过下标获取，链表需要遍历);
    3.改:顺序存储 计算上优于链式存储(数组可以通过下标获取，链表需要遍历);

    顺序存储:用一组地址连续的存储单元依次存储线性表的各个数据元素

    链式存储:用一组任意的存储单元存储线性表的各个数据元素
    //单向链表
    //遍历单向链表
    LindedList<int> link =new LindedList<int>();
    link.Add(1); link.Add(2); link.Add(3);
    LinkedNode<int> node = link.head;
    while(node!=null){
        Console.WriteLine(node.value);
        node = node.nextNode;
    }
    //单向链表节点
    class LinkedNode<T>{
        public T value;
        public LinkedNode<T> nextNode;//钩子,存储下一个元素

        public LinkdeNode(T value){
            this.value=value;
        }
    }
    //单向链表类 管理 节点 添加...
    class LindedList<T>{
        public LinkedNode<T> head;//头部节点
        public LinkedNode<T> last;//尾部节点
        ///添加节点
        public void Add(T value){
            LinkedNode<T> node =new LinkedNode<T>(value);
            if(head==null){
                head.node;
                last.node;
            }else{
                last.nextNode=node;
                last=node;
            }
        }
        public void Remove(T value){
            if(head==null){return;}
            if(head.value.Equals(value)){
                head=head.nextNode;
                //如果头节点被移除变空证明只有一个节点，那尾部也要清空
                if(head==null){last=null;}
            }
            LinkNode<T> node = head;
            while(node.nextNode!=null){
                if(node.nextNode.vlaue.Equals(value)){
                    //让当前找到这个元素的上个节点指向下一个节点
                    node.nextNode=node.nextNode.nextNode;
                    break;
                }
                node = node.nextNode;
            }
        }
    }

```

### 装箱和拆箱

- **装箱**：值类型转为引用类型(栈转堆)

- **拆箱**：引用类型转为值类型(堆转栈)

```c#
   class Porgram{
    static void Main(){
        int number = 15;
        //装箱
        object objNumber = number;
        //拆箱
        int boxNumber = (int)objNumber;
    }
   }
```

### ArrayList

```c#
 ArrayList a = new ArrayList(5);
        for (int i = 0; i < 10; i++)
        {
            a.Add(i);
             //运行结果0 1 2 3 4 5 6 7 8 9
            Console.Write(a[i]+" ");
        }

 ///遍历

    //先声明内存，防止每次都要增加内存
    //长度
    Console.WriteLine(a.Count);
    //扩容
    Console.WriteLine(a.Capacity);

    for(int i=0 ; i<a.Count ; i++){
        Console.WriteLine(a[i]);
    }

    //迭代器遍历
    foreach(object item in a){
        Console.WriteLine(item);
    }

 ///增删改查

 ///增
    a.add(10);
    a.add("123");
    a.add(true);
    ///插入某个位置 例如4是位置,"5"是想要插入的元素
    a.Insert(4,"5");

    ArrayList b =new ArrayList();
    b.add(1)
    //范围增加
    a.AddRange(b);

///删
    //移除指定元素
    a.Remove(1);
    //移除指定位置元素
    a.RemoveAt(2);
    //清除
    a.Clear();

///改
    ///先查指定位置修改
    int index =a.IndexOf(1);
    Console.WriteLine(index);

    //修改
    a[index]="1";
    Console.WriteLine(a[index]);



///查
    ///查看元素是否存在
    if(a.Contains("123")){
        Console.WriteLine("存在");
    }
    ///正向查找
    ///找到返回值是位置,找不到返回值是-1
    int index =a.IndexOf(1);
    Console.WriteLine(index);

    Console.WriteLine(a.IndexOf(false));

    ///反向查找
    index = a.LastIndexOf(true);

```

### Stack 栈

- **Stack**是栈存储器,是先进后出的数据结构,本身也是 object[]数组
- 先存入后获取，后存入的数据先获取

```c#
    //引用命名空间  System.Collections
    Stack stack = new Stack();

//遍历(不能for循环遍历)
    //长度
    Console.WriteLine(stack.Count);
    //foreach遍历,栈顶到栈底
    foreach(object item in stack){
        Console.WriteLine(item);
    }
    //将栈转换为object数组,栈顶到栈底
    object[] array = stack.ToArray();
    for(int i =0; i < array.length ; i++){
        Console.WriteLine(array[i]);
    }
    //循环弹栈
    while( stack.Count>0 ){
        object b = stack.Pop();
        Console.WriteLine(b);
    }

//增删改查

//增
    //压栈
    stack.Push(1);
    stack.Push("111");
    stack.Push(true);
    stack.Push(1.5f);

//取(栈没有删除概念，只有取)
    //弹栈
    object a = stack.Pop();
    //打印1.5
    Console.WriteLine(a);

// 改
    //栈无法改变其中元素 只能压(存)和弹(取)
    //只有清空
    stack.Clear();

//查
    //无法查看指定位置的元素，只能看栈顶内容
    a = stack.Peek();
    Console.WriteLine(a);
    //查看是否存在栈中
    if(stack.Contains("111")){
        Console.WriteLine("存在");
    }
```

### Queue 队列

- **Queue**是队列存储容器，是先进先出的数据结构
- 先存入先获取，先存入的数据先获取

```c#
    //引用命名空间  System.Collections
    Queue queue = new Queue();
//遍历(不能for循环遍历)
    //长度
    Console.WriteLine(queue.Count);
    //foreach遍历
    foreach(object item in queue){
        Console.WriteLine(item);
    }
    //将队列转换为object数组
    object[] array = queue.ToArray();
    for(int i = 0; i < array.length ; i++){
        Console.WriteLine(array[i]);
    }
    //循环出列
    while( queue.Count >0 ){
        object b = queue.Dequeue();
        Console.WriteLine(b);
    }

//增删改查

//增
    queue.Enqueue(1);
    queue.Enqueue("111");
    queue.Enqueue(true);
    queue.Enqueue(1.5f);

//取(队列没有删除概念，只有取)
    object a = queue.Dequeue();
    //打印1,先进先出
    Console.WriteLine(a);

// 改
    //队列无法改变其中元素 只能进出
    //只有清空
    queue.Clear();

//查
    //只能看队列头部内容但不会移除
    a = queue.Peek();
    Console.WriteLine(a);
    //查看是否存在队列中
    if(queue.Contains("111")){
        Console.WriteLine("存在");
    }
```

### Hashtable 哈希表

- Hashtable(散列表)是基于哈希代码组织的键值对
- 不是线程安全的，多线程使用要自己实现同步机制
- 主要功能是提高数据查询效率，键来访问集合中的元素(都是通过键找值)

```c#
    //引用命名空间  System.Collections
    Hashtable hashtable= new Hashtable();

//遍历(不能for循环遍历)
    //得到键值对,不能遍历
    Console.WriteLine(hashtable.Count);

    //遍历所有键
    foreach(object item in hashtable.Keys){
        //键
        Console.WriteLine(item);
        //值
        Console.WriteLine(hashtable[item]);
    }

    //遍历所有值(不能找到键)
    foreach(object item in hashtable.Values){
        //值
        Console.WriteLine(item);
    }

    //键值对一起遍历
      foreach(DictionaryEntry item in hashtable){
        Console.WriteLine("键:" + item.Key + "值:" + item.Value);
    }

    //迭代器遍历
    IDictionaryEnumerator myEnumerator = hashtable.GetEnumerator();
    bool flag = myEnumerator.MoveNext();
    while(flag){
        Console.WriteLine("键:" + item.Key + "值:" + item.Value);
        flag = myEnumerator.MoveNext();
    }

//增删改查

//增(不能增加重复的键)
    hashtable.Add(1,"1");
    hashtable.Add("2",2);
    hashtable.Add(true,false);

//删
    hashtable.Remove(true);
    //清空
    hashtable.Clear();
//改
    //先查找位置，然后直接改(只能改对应值,无法修改键)
    hashtable[3] = 15;

//查
    //通过键查看值，找不到返回空
    Console.WriteLine(hashtable[1]);
    //打印null
    Console.WriteLine(hashtable[15]);

    //查看是否存在
    //根据键两种方法一样
    if(hashtable.Contains("2")){
        Console.WriteLine("存在");
    }
    if(hashtable.ContainsKey("2")){
        Console.WriteLine("存在");
    }

    //根据值检测是否存在
     if(hashtable.ContainsValue("1")){
        Console.WriteLine("存在");
    }
```

## 泛型

- **泛型**相当于类型占位符，当真正使用类或方法时再具体指定类型
- 优点：**类型安全**(编译时检查类型安全)，**代码复用**(类型参数化，达到代码复用)，**性能提高**(避免运行时类型转化)

```c#
    //泛型类
    class Test<T>
    //占位字符可以有多个，用逗号
    //class Test2<T1,T2,T3>
    {
        public T Value { get; set; }
        //public T1 Value { get; set; }
        //public T2 Value { get; set; }
        //public T3 Value { get; set; }
    }
    class Program
    {
        static void Main(string[] args)
        {
            Test<int> t = new Test<int>();
            //多种占位
            //Test2<Test<int>,string,bool> t = new Test2<Test<int>,string,bool>();
        }
    }

    //泛型接口
    interface Itf<T>{
        T ValueValue { get; set; }
    }
    //继承占位符必须写类型
    class Test :Itf<int>{
        public int Value { get; set; }
    }

    //普通类
    class Test2
    {
        public void TestFun<T>( T value)
        {
            //这里面可以用泛型做逻辑处理
            //值不能为空，default可以得到默认值
            T t =default(T);
            //还可以这样return default(T);
        }
    }

    //泛型类
    //函数名后面加尖括号才是泛型函数
    class Test2<T>
    {
        public T Value;
        public void Itf<K>(K k){
            Console.WriteLine(k);
        }
    }
```

### 泛型约束

- 增加代码的灵活性和重用性,类型安全
- 六种泛型约束,where 泛型字母 : (约束条件):

1. 结构(struct)约束,值类型: where 泛型字母 : struct
2. 类(class)约束,引用类型: where 泛型字母 : class
3. 构造函数(new())约束,存在无参公共构造函数: where 泛型字母 : new()
4. 基类约束,某个类本身或者其派生类:where 泛型字母 : 类名
5. 接口约束,某个接口的派生类型:where 泛型字母 : 接口名
6. 无托管类型(unmanaged)约束,另一个泛型类型本身或派生类型:where 泛型字母 : 另一个泛型字母

```c#
    //约束组合使用,如:
    class Test<T> where T:class,new(){
        Console.WriteLine("既是类也是构造函数约束");
    }
    //多个泛型约束,如:
     class Test<T,K> where T:class,new() where K:struct{
        Console.WriteLine("T泛型约束where T:class,new();K泛型约束 where K:struct");
    }

```

### List 泛型数组

```c#
    //声明
    //using System.Collections.Generic;
    List<int> list = new List<int>();
    List<string> list1 = new List<string>();
    List<float> list2 = new List<float>();

//遍历
    Console.WriteLine(list.Count);
    //表示列表内部数组能够容纳的最大元素数量，无需再次调整大小
    Console.WriteLine(list.Capacity);
    for(int i=0; i<list.Count; i++){
        Console.WriteLine(list[i]);
    }

    //foreach遍历
    foreach(int item is list){
        Console.WriteLine(item);
    }

//增删改查

//增
    list.Add(1);
    list1.Add("2");
    list2.Add(0.15f);

    //可以一次性将一个列表的所有元素添加到另一个列表中
    list2.AddRange(list);
    //插入
    list.Insert(要插入元素的位置, 要插入的元素);

//删
    //根据值删除
    list.Remove(1);
    // 根据索引删除
    list1.RemoveAt(0);
    // 清空列表
    list2.Clear();
// 改
    //先查找位置，然后直接改
    list[1]=2;
    //或
    if (list1.Count > 2)
    {
        list1[1] = "1"; // 修改索引为0的元素
    }
//查
    // 检查是否存在某个元素
    if (list.Contains(1))
    {
        Console.WriteLine("存在元素1");
    }
    //正向查找
    int index = list.IndexOf(1);
    Console.WriteLine(index != -1 ? $"{index}" : "找不到位置");  //找到返回位置
    //反向查找
    int index = list1.LastIndexOf(2);
    Console.WriteLine(index);
```

### Dictionary 泛型字典

- Dictionary 泛型字典相当于 Hashtable 的泛型

```c#
    //声明
    Dictionary<int,string> dictionary=new Dictionary<int,string>();
    //遍历
    //遍历所有键
    foreach(int item in dictionary.Keys){
        Console.WriteLine(item);
        Console.WriteLine(dictionary[item]);
    }
    //遍历所有值
    foreach(string item in dictionary.Values){
        Console.WriteLine(item);
    }
    //遍历键值对
    foreach(KeyValuePair<int,string> item in dictionary){
        Console.WriteLine("键:" + item.Key + "值:" + item.Value);
    }
///增删改查
    //增(不能增加相同的键)
    dictionary.Add(1,"1");
    dictionary.Add(2,"2");
    dictionary.Add(3,"3");

    //删(只能通过键删除)
    dictionary.Remove(1,"1");
    //清空
    dictionary.Clear();

    //改
    //先查然后直接改
    dictionary[键值] = 改的值;

    //查
    //通过键查看
    dictionary[键值];

    //查看是否存在
    //‌Dictionary.TryGetValue()方法,用于尝试获取字典中指定键的值
    //如果字典中存在该键，则将值赋给out参数，并返回bool值true；如果不存在，则返回false
    if (dictionary.TryGetValue(keyToFind, out value)){
        // 处理找到的值
    }else{
        // 处理未找到的情况
    }

    //键查找
    if(dictionary.ContainsKey(键)){
        Console.WriteLine("存在键");
    }

    //值查找
     if(dictionary.ContainsValue(值)){
        Console.WriteLine("存在值");
    }

```

### linkedList

## lambad 表达式

```c#
    //lambad 表达式
    ///(参数列表)=>
    //{
        //函数体
    //}；

    //无参无返回值lambad 表达式
    Action a=()=>{
        Console.writeLine("无参无返回值lambad 表达式");
    }
    //有参
     Action<int> a1=(int value)=>{Console.writeLine("有参{0}",value);}
     //a1(15);
```

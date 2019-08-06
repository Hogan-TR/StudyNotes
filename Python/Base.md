1. **str**与**bytes**之间的转换

   ```python
   # bytes object
   b = b"example"
   
   # str object
   s = "example"
   
   # str to bytes
   bytes(s, encoding = "utf8")
   
   # bytes to str
   str(b, encoding = "utf-8")
   
   # an alternative method
   # str to bytes
   str.encode(s)
   
   # bytes to str
   bytes.decode(b)
   ```

2. 内置函数

   - **super()** 函数是用于调用父类(超类)的一个方法

     > super 是用来解决多重继承问题的，直接用类名调用父类方法在使用单继承的时候没问题，但是如果使用多继承，会涉及到查找顺序（MRO）、重复调用（钻石继承）等种种问题。
     >
     > MRO 就是类的方法解析顺序表, 其实也就是继承父类方法时的顺序表。
     
     - 使用 super() 可以很好地**避免**构造函数被调用两次 
     - 它会**查找**所有的**超类**，以及超类的超类，直到找到所需的特性为止。
     
     ```python
     class A():
         def __init__(self):
             print('enter A')
             print('leave A')
     
     class B(A):
         def __init__(self):
             print('enter B')
             super().__init__()
             print('leave B')
     
     class C(A):
         def __init__(self):
             print('enter C')
             super().__init__()
             print('leave C')
     
     class D(B, C):
         def __init__(self):
             print('enter D')
             super().__init__()
             print('leave D')
     
     
     d = D()
     ```
     
     ```python
     执行结果：
     enter D
     enter B
     enter C
     enter A
     leave A
     leave C
     leave B
     leave D
     ```
     
     ```
     示意图：
          ---> B ---
     A --|          |--> D
          ---> C ---
     ```
   
3. Loading...
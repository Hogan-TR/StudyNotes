**v 1.0**

```python
import time

def display_time(func):
    def wrapper():
        t1 = time.time()
        func()
        t2 = time.time()
        print(t2-t1)
    return wrapper


def is_prime(num):
    if num < 2:
        return False
    elif num == 2:
        return True
    else:
        for i in range(2,num):
            if num % i == 0:
                return False
        return True


@display_time
def prime_nums():
    for i in range(2,10000):
        if is_prime(i):
            print(i)

prime_nums()
```

**v 1.1**

```python
import time
  
def display_time(func):
    def wrapper():
        t1 = time.time()
        result = func()
        t2 = time.time()
        print("Total time: {:.4} s".format(t2 - t1))
        return result
    return wrapper


def is_prime(num):
    if num < 2:
        return False
    elif num == 2:
        return True
    else:
        for i in range(2,num):
            if num % i == 0:
                return False
        return True


@display_time
def count_prime_nums():
    count = 0
    for i in range(2,10000):
        if is_prime(i):
            count += 1
    return count

count = count_prime_nums()
print(count) 
```



**v 1.2**

```python
import time
  
def display_time(func):
    def wrapper(*args):
        t1 = time.time()
        result = func(*args)
        t2 = time.time()
        print("Total time: {:.4} s".format(t2 - t1))
        return result
    return wrapper


def is_prime(num):
    if num < 2:
        return False
    elif num == 2:
        return True
    else:
        for i in range(2,num):
            if num % i == 0:
                return False
        return True


@display_time
def count_prime_nums(maxnum):
    count = 0
    for i in range(2,maxnum):
        if is_prime(i):
            count += 1
    return count

count = count_prime_nums(10000)
print(count) 

# Python 与 Python3 运行时差很多...
```
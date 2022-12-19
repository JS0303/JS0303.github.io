---
layout: single
title: "[Python] self"
categories: Python
tag: [Python]
toc: true
author_profile: false
search: true
---

#### **self**

- python의 method는 항상 첫번쨰 인자로 self를 전달
- **self는 현재 해당 method가 호출되는 객체 자신을 가리킴**
- C++/C#, Java의 this에 해당
- 이 역시 이름이 self일 필요는 없으나, 위치는 항상 맨 처음의 parameter이며 관례적으로 self 사용

```
class Person:
	def __init__(self, name, age):
    	print('self: ', self)
    	self.name = name
        self.age = age

a = Person('Aaron', 20)
b = Person('Bob', 30)

print(a)
print(b)
```

```
self: <__main__.Person object at 0x10787af98>
self: <__main__.Person object at 0x10787aac8>
<__main__.Person object at 0x10787af98>
<__main__.Person object at 0x10787aac8>
```

self는 해당 method가 호출되는 객체 자신을 가리킴

```
class Person:
	def __init__(self, name, age):
    	print('self: ', self)
    	self.name = name
        self.age = age

	def sleep(self):
        print('self: ', self)
    	print(self.name, '은 잠을 잡니다.')

a = Person('Aaron', 20)
b = Person('Bob', 30)

print(a)
print(b)

a.sleep()
b.sleep()
```

```
self: <__main__.Person object at 0x10787af98>
self: <__main__.Person object at 0x10787aac8>
<__main__.Person object at 0x10787af98>
<__main__.Person object at 0x10787aac8>
self: <__main__.Person object at 0x10787af98>
Aaron 은 잠을 잡니다.
self: <__main__.Person object at 0x10787aac8>
Bob 은 잠을 잡니다.
```

멤버함수(method)에서 속성에 접근할 수 있음

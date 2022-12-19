---
layout: single
title: "[Python] 생성자(__init__)"
categories: Python
tag: [Python]
toc: true
author_profile: false
search: true
---

#### **\_\_init\_\_(self)**

- 생성자, class instance가 생성될 때 호출됨
- self 인자는 항상 첫 번째에 오며 자기 자신을 가리킴
- 이름이 꼭 self일 필요는 없지만, 관례적으로 self 사용
- 생성자에서는 해당 class가 다루는 데이터를 정의
  - 이 데이터를 멤버 변수(member variable) 또는 속성(attribute)라고 함

```
class Person:
	def __init__(self):
    	print(self, 'is generated')

 p1 = Person()
 p2 = Person()
```

```
<__main__.Person object at 0x10787a9e8> is generated
<__main__.Person object at 0x10787a400> is generated
```

각각 다른 메모리에 두 변수가 생성되어있음

```
class Person:
	def __init__(self):
    	print(self, 'is generated')
        self.name = 'Kate'
        self.age = 10

 p1 = Person()
 p2 = Person()

 p1.name, p1.age
```

```
('Kate', 10)
```

p1이라는 객체의 속성을 정의해주고 접근할 수 있음

```
class Person:
	def __init__(self):
    	print(self, 'is generated')
        self.name = 'Kate'
        self.age = 10

 p1 = Person()
 p2 = Person()

 p1.name = 'aaron'
 p1.age = 20

 print(p1.name, p1.age)
```

```
<__main__.Person object at 0x107889400> is generated
<__main__.Person object at 0x107889390> is generated
arron 20
```

추가해준 속성을 바꿔줄 수 있음

```
class Person:
	def __init__(self, name, age):
    	print(self, 'is generated')
        self.name = name
        self.age = age

p1 = Person('Bob', 30)
p2 = Person('Kate', 20

print(p1.name, p1.age)
print(p2.name, p2.age)
```

```
<__main__.Person object at 0x107889530> is generated
<__main__.Person object at 0x1078895c0> is generated
Bob 30
Kate 20
```

또한 객체를 생성함과 동시에 속성을 정의해줄 수도 있음(동적)

```
class Person:
	def __init__(self, name, age=10):
    	# print(self, 'is generated')
        self.name = name
        self.age = age

p1 = Person('Bob', 30)
p2 = Person('Kate', 20
p3 = Person('Aaron')

print(p1.name, p1.age)
print(p2.name, p2.age)
print(p3.name, p3.age)
```

```
Bob 30
Kate 20
Aaron 10
```

\_\_init\_\_ 함수에서도 마찬가지로 기본값을 지정할 수 있음

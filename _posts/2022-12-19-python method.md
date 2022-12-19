---
layout: single
title: "[Python] method"
categories: Python
tag: [Python]
toc: true
author_profile: false
search: true
---

#### **mothod 정의**

- 멤버 함수라고도 하며, 해당 class의 object에서만 호출 가능
- method는 객체 레벨에서 호출되며, 해당 객체의 속성에 대한 연산을 행함
- {obj}.{method}() 형태로 호출됨

```
class Counter:
	def __init__(self, num):
    	self.num = 0
    def print_current_value(self):
    	print('현재값은: ', self.num)

c1 = Counter()
c1.print_current_value()

c2 = Counter()
c2.print_current_value()
```

```
현재값은: 0
현재값은: 0
```

기능 추가

```
# 1. 숫자를 하나 증가
# 2. 숫자를 0으로 초기화
class Counter:
	def __init__(self, num):
    	self.num = 0

    def increment(self):
    	self.num += 1

    def reset(self):
    	self.num = 0

    def print_current_value(self):
    	print('현재값은: ', self.num)

c1 = Counter()
c1.print_current_value()
c1.incerment()
c1.incerment()
c1.incerment()
c1.print_current_value()

c1.reset()

c1.print_current_value()

c2 = Counter()
c2.increment()
c2.print_current_value()
```

```
현재값은: 0
현재값은: 3
현재값은: 0
현재값은: 1
```

**method type**

- instance method - 객체로 호출
  - method는 객체 레벨로 호출되기 때문에, 해당 method를 호출한 객체에만 영향을 미침
- class method(static method) - class로 호출
  - class method의 경우, class 레벨로 호출되기 때문에 class 멤버 변수만 변경 가능

```
class Math:
	@staticmethod
	def add(self, a, b):
    	return a + b

	@staticmethod
	def multiply(self, a, b)
    	return a * b

Math.add(10, 20)
Math.multiply(10, 20)
```

속성이 없이(self가 할 일이 없이) 내부의 데이터를 유지하지 않는 class의 경우 instance level의 method를 생성할 필요가 없음 ->  
전달된 데이터에 대해서 처리만 해서 반환하는 경우 @staticmethod와 같이 데코레이터를 달아주고 static 하게 class 이름으로 함수를 불러올 수 있음

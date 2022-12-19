---
layout: single
title: "[Python] Class Inheritance (상속)"
categories: Python
tag: [Python]
toc: true
author_profile: false
search: true
---

#### **class inheritance (상속)**

- 기존에 정의해둔 class의 기능을 그대로 물려받음
- 기존 class에 기능을 추가하거나 변경하여 새로운 class를 정의
- 코드의 재사용이 가능해짐
- 기존 class를 Parent, Super, Base class라고 부름
- 상속을 받는 새로운 class는 Child, Sub, Derived class라고 부름
- 의미적으로 is-a 관계를 가짐

```
class Person:
	def __init__(self, name, age):
    	self.name = name
        self.age = age

	def eat(self, food):
    	print('{}은 {}를 먹습니다.'.format(self.name, food)

    def sleep(self, minute):
    	print('{}은 {}분동안 잡니다.'.format(self.name, minute)

    def work(self, minute):
    	print('{}은 {}분동안 일합니다.'.format(self.name, minute)

class Student:

class Employee:


bob = Person('Bob', 25)
bob.eat('BBQ')
bob.sleep(30)
bob.work(60)
```

```
Bob은 BBQ를 먹습니다.
Bob은 30분동안 잡니다.
Bob은 60분동안 일합니다.
```

Student와 Employee에 Person을 상속받는다

```
class Person:
	def __init__(self, name, age):
    	self.name = name
        self.age = age

	def eat(self, food):
    	print('{}은 {}를 먹습니다.'.format(self.name, food)

    def sleep(self, minute):
    	print('{}은 {}분동안 잡니다.'.format(self.name, minute)

    def work(self, minute):
    	print('{}은 {}분동안 일합니다.'.format(self.name, minute)

class Student(Person):
	def __init__(self, name, age):
    	self.name = name
        self.age = age

class Employee:
	def __init__(self, name, age):
    	self.name = name
        self.age = age

bob = Person('Bob', 25)
bob.eat('BBQ')
bob.sleep(30)
bob.work(60)
```

bob = Person() 부분을 bob = Student() 혹은 bob = Employee() 로 바꾸어도 잘 동작한다(부모 class의 기능을 그대로 이용할 수 있음)

**method override**

- 부모 class의 method를 재정의(override)
- 하위 class(자식 class)의 instance로 호출 시 재정의된 method가 호출됨

```
class Person:
	def __init__(self, name, age):
    	self.name = name
        self.age = age

	def eat(self, food):
    	print('{}은 {}를 먹습니다.'.format(self.name, food)

    def sleep(self, minute):
    	print('{}은 {}분동안 잡니다.'.format(self.name, minute)

    def work(self, minute):
    	print('{}은 {}분동안 일합니다.'.format(self.name, minute)

class Student(Person):
	def __init__(self, name, age):
    	self.name = name
        self.age = age

    def work(self, minute):
    	print('{}은 {}분동안 공부합니다.'.format(self.name, minute)

class Employee:
	def __init__(self, name, age):
    	self.name = name
        self.age = age

bob = Student('Bob', 25)
bob.eat('BBQ')
bob.sleep(30)
bob.work(60)
```

```
Bob은 BBQ를 먹습니다.
Bob은 30분동안 잡니다.
Bob은 60분동안 공부합니다.
```

work라는 함수를 Student class에서 재정의하여 실행하면 결과가 바뀜

**super**

- 하위 class(자식 class)에서 부모 class의 method를 호출할 때 사용

```
class Person:
	def __init__(self, name, age):
    	self.name = name
        self.age = age

	def eat(self, food):
    	print('{}은 {}를 먹습니다.'.format(self.name, food)

    def sleep(self, minute):
    	print('{}은 {}분동안 잡니다.'.format(self.name, minute)

    def work(self, minute):
    	print('{}은 {}분동안 준비합니다.'.format(self.name, minute)

class Student(Person):
	def __init__(self, name, age):
    	self.name = name
        self.age = age

    def work(self, minute):
    	print('{}은 {}분동안 공부합니다.'.format(self.name, minute)

class Employee:
	def __init__(self, name, age):
    	self.name = name
        self.age = age

    def work(self, minute):
    	super.work(minute)
    	print('{}은 {}분동안 업무를 합니다.'.format(self.name, minute)

bob = Employee('Bob', 25)
bob.eat('BBQ')
bob.sleep(30)
bob.work(60)
```

```
Bob은 BBQ를 먹습니다.
Bob은 30분동안 잡니다.
Bob은 60분동안 준비합니다.
Bob은 60분동안 업무를 합니다.
```

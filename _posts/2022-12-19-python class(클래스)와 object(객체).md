---
layout: single
title: "[Python] class(클래스)와 object(객체)"
categories: Python
tag: [Python]
toc: true
author_profile: false
search: true
---

**'인간' 이라는 타입(class)**

속성(attribute) - 이름, 국적, 나이 ...

행동(method) - 먹다, 자다, 일어나다 ...

**홍길동, 임꺽정 등 실제로 존재하는 객체(object)**

---

**'List' 라는 타입(class)**

속성(attribute) - Items

행동(method) - append, extend ...

\[1,2,3\]

\['Hello', 'World'\]

**실제로 존재하는 객체(object)**

---

#### **class 란?**

- 실세계의 것을 모델링하여 속성(attribute)와 동작(method)를 갖는 데이터 타입
- python에서의 string, int, list, dict... 모두가 다 class로 존재
- 예로 학생이라는 class를 만들면 학생이 나타내는 속성과 행동을 함께 정의
- 따라서 다루고자 하는 데이터(변수)와 데이터를 다루는 연산(함수)를 하나로 캡슐화(encapsulation)하여 class로 표현
- 모델링에서 중요시 하는 속성에 따라 클래스의 속성과 행동이 각각 달라짐

```
a = [1,2,3,4]
a.append(5)
print(a)
```

```
[1,2,3,4,5]
```

list는 내부적으로 item을 관리함

a.append()를 하면 자신의 속성에 append라는 method를 통해서 item을 추가시킴

**class 선언하기**

- 객체 생성을 위해 객체의 모체가 되는 class를 미리 선언

```
class Person:
	pass # 빈 class를 구현하기 위해서는 pass라는 keyword를 사용한다
```

```
bob = Person()
cathy = Person()

a = list()
b = list()

print(type(bob), type(cathy))
print(type(a), type(b))
```

```
<class '__main__.Person'> <class '__main__.Person'>
<class 'list'> <class 'list'>
```

#### **object 란?**

- class로 생서되어 구체화된 객체(instance)
- python의 모든 것(int, str, list... etc)은 객체(instance)
- 실제로 class가 instance화 되어 memory에 상주하는 상태를 의미
- class가 빵틀이라면, object는 실제로 찍어낸 빵이라고 비유 가능

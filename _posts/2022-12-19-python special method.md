---
layout: single
title: "[Python] special method"
categories: Python
tag: [Python]
toc: true
author_profile: false
search: true
---

#### **special method**

- \_\_로 시작 \_\_로 끝나는 특수 함수
- 해당 method들을 구현하면, 커스텀 객체에 여러가지 python 내장 함수나 연산자를 적용 가능
- overriding 가능한 함수 목록은 아래 링크 참조
  - [https://docs.python.org/3/reference/datamodel/html](https://docs.python.org/3/reference/datamodel/html)
  - [https://docs.python.org/3/reference/datamodel.html#object.\_\_add\_\_](https://docs.python.org/3/reference/datamodel.html#object.__add__)

[3\. Data model

Objects, values and types: Objects are Python’s abstraction for data. All data in a Python program is represented by objects or by relations between objects. (In a sense, and in conformance to Von ...

docs.python.org](https://docs.python.org/3/reference/datamodel.html#object.__add__)

```
# Point
# 2차원 좌표평면 각 점(x, y)
# 연산
# 두 점의 덧셈, 뺄셈 (1, 2) + (3, 4) = (4, 6)
# 한 점과 숫자의 곱셈 (1, 2) * 3 = (3, 6)
# 그 점의 길이 (0,0) 부터의 거리
# x, y 값 가져오기
# 출력하기

class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __add__(self, pt):
    	new_x = self.x + pt.x
        new_y = self.y + pt.y
        return Point(new_x, new_y)

    def __sub__(self, pt):
    	new_x = self.x - pt.x
        new_y = self.y - pt.y
        return Point(new_x, new_y)

    def __mul__(self, factor):
    	return Point(self.x * factor, self,y * factor)

    def __getitem__(self, index):
    	if index == 0:
        	return self.x
        elif index == 1:
        	return self.y
        else:
        	return -1

    def __len__(self):
    	return self.x ** 2 + self.y ** 2

    def __str__(self):
    	return '({}, {})'.format(self.x, self,y)

p1 = Point(3, 4)
p2 = Point(2, 7)

a = 1 + 2
p3 = p1 + p2
p4 = p1 - p2

# p5 = p1.multiply(3)
p5 = p1 * 3

print(len(p1))

# p1[0] -> x
# p1[1] -> y
print(p1[0])
print[p1[1])
print(p1)
print(p2)
print(p3)
print(p4)
print(p5)
```

```
25
3
4
(3, 4)
(2, 7)
(5, 11)
```

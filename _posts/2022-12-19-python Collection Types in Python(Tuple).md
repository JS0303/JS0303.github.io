---
layout: single
title: "[Python] Collection Types in Python(Tuple)"
categories: Python
tag: [Python]
toc: true
author_profile: false
search: true
---

#### Tuple

-   리스트와 같이 복수개의 원소를 가지는 collection type
-   생성 후 변경 불가

```
a = [1,2,3]
b = (1,2,3)

print(type(a))
print(type(b))
```

```
<class 'list'>
<class 'tuple'>
```

```
a[0] = 100
print(a)

b[0] = 100
print(b)
```

```
[100,2,3]
TypeError: 'tuple' object does not support item assignment
```

tuple은 불변성을 가지므로 값을 갱신할 수 없다.

그럼 tuple을 왜 쓰는가??(크기가 적은 절대 변하지 않는 값을 추적할 것이 아니라면 거의 사용할 일이 없다.)

\-> 문법적으로 편의성을 제공하기 때문에 사용한다.

#### Tuple Unpacking

-   튜플 값을 차례대로 변수에 대입

```
a = (100, 200)
type(a)
```

```
tuple
```

괄호를 생략해도 성립

```
a = 100, 200
type(a)
```

```
tuple
```

두 개의 변수에 각각 값을 대입할 때 사용

```
a, b = 100, 200

print(a, b)
```

```
100 200
```

**타 언어의 경우 함수는 기본적으로 한개의 값을 반환할 수 있지만 Python에서는 tuple을 통해 여러 개의 값을 반환할 수 있음**

(그 값이 정말 multiple은 아니고 단순히 tuple을 반환하는 것)

타 언어의 경우 임의의 두 변수의 값을 서로 바꾸려면 임시적인 변수가 하나 더 필요하지만 Python에서는 tuple로 간편하게 할 수 있음

```
a, b = 4, 5

print(a, b)

# logic
# temp = a
# a = b
# b = temp

a, b = b, a

print(a, b)
```

```
4 5
5 4
```
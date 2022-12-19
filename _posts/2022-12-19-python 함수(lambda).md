---
layout: single
title: "[Python] 함수(lambda)"
categories: Python
tag: [Python]
toc: true
author_profile: false
search: true
---

#### lambda 함수란?

일반적인 함수와 다를 게 없으나 굉장히 간단한 함수의 경우 def를 통해 정의하는 것이 아닌 한 줄로 정의하는 문법적인 기능

- 단일 문으로 표현되는 익명 함수(이름이 없이 구현체만 존재)
- 코드 상에서 한 번만 사용되는 기능을 굳이 함수로 만들기보다 1회성으로 사용

```
square = lambda x:x**2
type(square)
```

```
function
```

: 을 사이에 두고 입력과 출력을 정의 (return을 사용하지 않음)

```
square = lambda x:x**2
square(5)
```

```
25
```

이는 아래와 같음

```
def square2(x):
	return x**2

square2(5)
```

```
25
```

```
# 일반 함수
def add(x,y):
	return x + y
# lambda 함수
add2 = lambda x,y:x+y
add2(10, 20)
```

```
30
```

예)

```
strings = ['bob', 'charles', 'alexander3', 'teddy']
strings.sort()

print(strings)
```

```
['alexander3', 'bob'. 'charles', 'teddy']
```

이를 문자열의 길이가 짧은 순으로 출력해보려 함

```
def str_len(s):
	return len(s)
```

```
strings = ['bob', 'charles', 'alexander3', 'teddy']
strings.sort(key=str_len)

print(strings)
```

```
['bob', 'teddy', 'charles', 'alexander3']
```

여기에 lambda 함수를 적용

```
strings = ['bob', 'charles', 'alexander3', 'teddy']
#strings.sort(key=str_len)
strings.sort(key=lambda s:len(s))

print(strings)
```

위에서 def를 통해 정의한 기능을 짧게 한번 쓰고 더 이상 사용하지 않음(lambda 함수를 통해 코드를 조금 더 python 답게 쓸 수 있음)

**Filter, Map, Reduce**

- lambda가 유용하게 사용되는 대표적인 3가지 함수
- filter : 특정 조건을 만족하는 요소만 남기고 필터링
- map : 각 원소를 주어진 수식에 따라 변형하여 새로운 리스트를 반환
- reduce : 차례대로 앞 2개의 원소를 가지고 연산. 연산의 결과가 다시 다음 연산의 입력으로 진행됨. 따라서 마지막까지 진행되면 최종 출력은 한 개의 값만 남게 됨

- **filter**

```
filter(함수, 리스트)
```

```
nums = [1,2,3,6,8,9]

filter(함수, nums)
```

```
def even(n):
	return n % 2 == 0

even(3)
```

```
False
```

```
nums = [1,2,3,6,8,9]

filter(even, nums)
```

```
<fliter at 0x111946898>
```

위와 같이 filter를 적용하면 단순 객체가 반환되므로 list로 casting 해줌

```
nums = [1,2,3,6,8,9]

list(filter(even, nums))
```

```
[2,6,8]
```

이를 even 함수를 외부에 정의하지 않고 lambda 함수로 표현하면

```
nums = [1,2,3,6,8,9]

list(filter(lambda n:n%2==0, nums))
```

```
[2,6,8]
```

- **map**

```
# map
# 주어진 리스트, 리스트의 제곱을 한 숫자로 새로운 리스트
nums = [1,2,3,6,8,9,10,11,13]
# map(함수, nums)
list(map(lambda n:n**2, nums))
```

```
[1,4,9,36,64,81,100,121,169]
```

위에서 정의한 even을 적용해보면

```
list(map(even, nums))
```

```
[False, True, False, True, True, False, True, False, False]
```

이를 다시 lambda 함수로 적용해보면

```
list(map(lambda n:n%2==0, nums))
```

```
[False, True, False, True, True, False, True, False, False]
```

- **reduce**

```
import functools

functools.reduce(함수, 리스트)
```

```
<function _functools.reduce>
```

```
import functools

a = [1,3,5,8]
# 리스트 안의 모든 숫자의 합
functools.reduce(lambda x,y:x+y, a)
```

```
17
```

```
import functools

a = [1,3,5,8]
# 리스트 안의 모든 숫자의 곱
functools.reduce(lambda x,y:x*y, a)
```

```
120
```

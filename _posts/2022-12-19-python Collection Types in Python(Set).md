---
layout: single
title: "[Python] Collection Types in Python(Set)"
categories: Python
tag: [Python]
toc: true
author_profile: false
search: true
---

#### Set

- dictionary에서 key만 활용하는 데이터 구조로 이해
- 수학에서의 집합과 동일한 개념

```
a = {1,1,2,3,3,4,1,5}
print(a)
```

```
{1,2,3,4,5}
```

중복을 허용하지 않으며, index가 없어 index로 접근하려고 하면 error 발생(순서가 없다)

- set()을 통해 선언

```
a = set()
type(a)
```

```
set
```

리스트 a를 선언한 뒤 이를 set으로 변환 -> b

```
a = [1,1,2,3,3,4,1,5]
print(a)

b = set(a)
print(b)
```

```
[1,1,2,3,3,4,1,5]
{1,2,3,4,5}
```

#### Set Operations

- 수학 연산과 동일
- 교집합, 차집합, 합집합 등 지원

```
a = {1,2,3}
b = {2,3,4}

print(a.union(b)) # 합집합
print(a.intersection(b)) # 교집합
print(a.difference(b)) # 차집합
```

```
{1,2,3,4}
{2,3}
{1}
```

```
# 부분집한인지 아닌지
print(a.subset(b)
```

```
False
```

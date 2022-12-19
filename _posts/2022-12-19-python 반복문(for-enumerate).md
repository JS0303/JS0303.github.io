---
layout: single
title: "[Python] 반복문(for-enumerate)"
categories: Python
tag: [Python]
toc: true
author_profile: false
search: true
---

#### Enumerate 함수

python에서 for문을 사용하다 보면 인덱스와 해당 값이 전부 필요한 경우 아래와 같이 enumerate 함수를 활용할 수 있다.

```
a = [1,2,3,4,5]
for index, num in enumerate(a):
	print(index, num)
```

```
0 1
1 2
2 3
3 4
4 5
```

---
layout: single
title: "[Python] Collection Types in Python(List - member function)"
categories: Python
tag: [Python]
toc: true
author_profile: false
search: true
---

- append()
  - 리스트의 끝에 항목을 추가함

```
a = [1,2,3,4,5]
a.append(10)

print(a)
```

```
[1,2,3,4,5,10]
```

- extend()
  - 리스트를 연장
  - += 로도 가능함

```
a = [1,2,3,4,5]
b = [6,7,8,9,10]

a.extend(b)
```

```
# or
a += b
```

```
print(a)
```

```
[1,2,3,4,5,6,7,8,9,10]
```

- insert()
  - 리스트의 원하는 위치에 항목 추가
  - 첫 번째 원소는 인덱스, 두 번째 원소는 추가할 항목

```
a = [1,3,4,5,6]
a.insert(1, 40)

print(a)
```

```
[1,40,3,4,5,6]
```

- remove()
  - 괄호안의 값을 삭제

```
a = [1,2,30,4,5]
a.remove(30)

print(a)
```

```
[1,2,4,5]
```

- pop()
  - 괄호 안의 인덱스에 해당하는 값을 지움(지울 값을 반환 후 삭제)
  - 괄호를 비워둘 경우 가장 마지막 인덱스에 해당하는 값이 지워짐

```
a = [1,2,3,4,5]
a.pop()
d = a.pop()

print(a)
print(d)
```

```
[1,2,3,4]
5
```

- index()
  - 괄호 안의 값의 인덱스를 반환

```
a = [1,2,3,4,5]

a.index(2)
```

```
1
```

- in 키워드
  - 리스트 안에 해당 값이 존재하는지 확인
  - value in \[list\]
  - True or False 형태로 반환

```
a = [1,2,3,4,5,10]
b = 7

c = b in a

print(c)
```

```
False
```

- list 정렬
  - sort() -> 리스트 안 요소들을 정렬
  - sorted() -> 정렬된 리스트의 복사본을 반환

```
a = [2,3,1,5,7,4,6]
a.sort()

print(a)
```

```
[1,2,3,4,5,6,7]
```

```
a = [2,3,1,5,7,4,6]
a.sort(reverse=True)

print(a)
```

```
[7,6,5,4,3,2,1]
```

```
a = [2,3,1,5,7,4,6]
b = a.sorted()

print(a)
print(b)
```

```
[2,3,1,5,7,4,6]
[1,2,3,4,5,6,7]
```

---

주로 쓰이는 함수는 위와 같으며 이외에 더 자세한 내용을 참고하려면 [여기](https://docs.python.org/ko/3.11/tutorial/datastructures.html#more-on-lists)를 참고하면 된다.

다음 포스팅에서 계속..

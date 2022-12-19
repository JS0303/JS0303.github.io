---
layout: single
title: "[Python] Collection Types in Python(Dictionary)"
categories: Python
tag: [Python]
toc: true
author_profile: false
search: true
---

#### Dictionary

- key와 value의 데이터 구조
- 매우 자주 쓰임
- key는 내부적으로 hash값으로 저장됨
- 인덱스를 고려하지 않음

List와 비교

```
a = [0,1,2,3,4]

print(a[0])
print(a[4])
```

```
0
4
```

List - 찾고자 하는 원소의 인덱스를 알고 있다면 리스트의 길이와 상관없이 그 원소에 접근하는 시간은 거의 0 임.

(하지만 인덱스를 모른다면 값을 하나하나 비교해야 하므로 오래 걸림)

위에서 언급한 List의 특징처럼 Dictionary에서 key를 알고 있다면 그 원소에 접근하는 시간은 거의 0 임.

```
a = {'Korea': 'Seoul', 'Canada': 'Ottawa', 'USA': 'Wasington D.C'}

print(a)
```

```
{'Korea': 'Seoul', 'Canada': 'Ottawa', 'USA': 'Wasington D.C'}
```

순서가 있는 것처럼 보이지만 사실은 순서가 없음(인덱스로 접근 불가).

```
print(a['Korea'])
```

```
Seoul
```

아래와 같이 dictionary를 초기화할 수 있으나 이는 인덱스의 접근이 아님(key를 통한 접근-대괄호 안의 값이 인덱스가 아니라 key)

```
b = {0:1, 1:6, 7:9, 8:10}

print(b[0])
```

```
1
```

- 항목 추가 및 변경
  - 기존에 key가 존재하면 새로운 value로 업데이트
  - 기존에 key가 존재하지 않으면 새로운 key, value 생성

```
a = {'Korea': 'Seoul', 'Canada': 'Ottawa', 'USA': 'Wasington D.C'}

a['Japen'] = 'Tokyo'
a['China'] = 'Beijing'

print(a)
```

```
{'Korea': 'Seoul', 'Canada': 'Ottawa', 'USA': 'Wasington D.C', 'Japen': 'Tokyo', 'China': 'Beijing'}
```

**동일한 key가 존재할 수 없음**

(동일한 키의 값이 들어오면 overwrite 해버림)

```
a = {'Korea': 'Seoul', 'Canada': 'Ottawa', 'USA': 'Wasington D.C'}

a['Japen'] = 'Tokyo'
a['Japen'] = 'Kyoto'
a['China'] = 'Beijing'

print(a)
```

```
{'Korea': 'Seoul', 'Canada': 'Ottawa', 'USA': 'Wasington D.C', 'Japen': 'Kyoto', 'China': 'Beijing'}
```

**동일한 value는 존재할 수 있음**

```
a = {'Korea': 'Seoul', 'Canada': 'Ottawa', 'USA': 'Wasington D.C'}

a['Japen'] = 'Tokyo'
a['Japen'] = 'Kyoto'
a['Japen2'] = 'Kyoto'
a['China'] = 'Beijing'

print(a)
```

```
{'Korea': 'Seoul', 'Canada': 'Ottawa', 'USA': 'Wasington D.C', 'Japen': 'Kyoto', 'Japen2': 'Kyoto', 'China': 'Beijing'}
```

- update()
  - 두 딕셔너리를 병합
  - 겹치는 key가 있다면 parameter로 전달되는 key 값이 overwrite 됨

```
a = {'a': 1, 'b': 2, 'c': 3}
b = {'a': 2, 'd': 4, 'e': 5}

a.update(b)

print(a)
```

```
{'a': 2, 'b': 2, 'c': 3, 'd': 4, 'e': 5}
```

- key 삭제
  - del 키워드 사용(del 키워드는 정의된 변수를 아예 지우는 데에도 사용할 수 있음)
  - pop 함수 이용

```
a = {'a': 1, 'b', 2, 'c': 3}
print(a)

del a['b']
print(a)
```

```
{'a': 1, 'b', 2, 'c': 3}
{'a': 1, 'c': 3}
```

```
a = {'a': 1, 'b', 2, 'c': 3}
print(a)

del a['b']
print(a)
```

```
{'a': 1, 'b', 2, 'c': 3}
{'a': 1, 'c': 3}
```

- clear()
  - 딕셔너리의 모든 값을 초기화

```
print(a)
a.clear()
print(a)
```

```
{'a': 1, 'c': 3}
{}
```

- in
  - key값 존재 확인
  - O(1) 연산 - 딕셔너리의 크기와 상관없이 연산속도가 항상 일정하다는 뜻

```
a = {'a': 1, 'b', 2, 'c': 3}
print(a)

'b' in a
```

```
{'a': 1, 'b', 2, 'c': 3}
True
```

**in 키워드는 기능상으로는 List에서의 in과 같지만 성능상으로는 훨씬 좋음.**

(List에서의 in은 값을 하나하나 비교해야 하지만 Dictionary에서의 in은 key를 통한 즉시 접근이 가능)

- value access
  - dict\[key\]로 접근, key가 없을 경우 에러 발생
  - .get() 함수로 접근, key가 없는 경우 None 반환

```
print(a['d'])
```

```
KeyError: 'd'
```

```
print(a.get('d'))
```

```
None
```

#### 모든 keys, values 접근

- keys() - key만 반환
- values() - value만 반환
- items() - key, value의 튜블을 반환

```
print(a)
print(a.keys())
print(a.values())
```

```
{'a': 1, 'b', 2, 'c': 3}
dict_keys(['a', 'b', 'c'])
dict_values([1,2,3])
```

이는 list로 변환할 수 있음

```
print(a)
print(list(a.keys()))
print(list(a.values()))
```

```
{'a': 1, 'b', 2, 'c': 3}
['a', 'b', 'c']
[1,2,3]
```

key, value 형태의 tuple 반환

```
list(a.items())
```

```
[('a', 1), ('b', 2), ('c', 3)]
```

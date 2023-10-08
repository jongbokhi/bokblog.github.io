---
layout: single
title:  "[핵심4] 파이썬(Python) - 딕셔너리(dictionary)"
typora-root-url: ../
categories: python
tag: [python, 파이썬, coding, 코딩]
toc: true
author_profile: False

---

## 딕셔너리(dictionary)

## 1.딕셔너리(dictionary)란?

딕셔너리(Dictionary)는 파이썬에서 매우 유용한 자료형 중 하나로, 키(key)와 값(value)을 연결하는 방식으로 데이터를 저장합니다. 각 키는 유일해야 하며, 키를 사용하여 해당 키에 연결된 값을 검색할 수 있습니다. 딕셔너리는 중괄호 {}를 사용하여 생성하며, 콜론(:)으로 키와 값을 구분합니다. 

우리가 사전을 통해서 단어를 찾는 걸 상상해보시면, 딕셔너리 자료형에 대해 쉽게 이해하실 수 있을 겁니다. 

## 2.특징

파이썬에서 딕셔너리(Dictionary)는 키(key)와 값(value)을 대응시켜 저장하는 데이터 구조입니다. 딕셔너리는 중괄호 `{}`를 사용하여 생성하며, 각 키와 값은 콜론 `:`으로 연결됩니다. 

딕셔너리는 다음과 같은 특징을 가지고 있습니다:

1. 키(key)-값(value) 쌍: 딕셔너리는 키(key)와 그에 대응하는 값(value)으로 이루어진 항목들을 저장합니다.

2. 중복된 키(key) 허용하지 않음(immutable): 각 키는 유일해야 하며, 중복된 키를 사용하면 마지막 키(key)-값(value) 쌍이 이전 값을 대체합니다.

3. 순서가 없음: 딕셔너리는 키(key)-값(value) 쌍을 저장할 때 순서를 유지하지 않습니다. 파이썬 3.7+부터는 삽입 순서가 유지되지만, 이전 버전에서는 순서가 보장되지 않습니다.

## 3. 예제 코드

딕셔너리를 생성하고 사용하는 간단한 예제를 보겠습니다:

```python
# 딕셔너리 생성
student = {
    "이름": "홍길동",
    "성별": "여성",
    "학년": 3,
    "성적": 95.5,
    "과목": ["수학", "과학", "영어"]  #값(value)에 리스트 자료형 사용 가능
}

# 딕셔너리의 특정 키(key)를 사용하여 값(value)에 접근: student[키] 또는 student.get(키)

print(student["이름"])  # 출력: "홍길동"
print(student.get("이름")) # 출력: "홍길동"

print(student["성적"])  # 출력: 95.5
print(student.get("성적")) # 출력: 95.5

# 존재하지 않는 키를 사용하면 KeyError가 발생
# print(student["나이"])  # KeyError 발생


# 키(key)- 값(value) 삭제

del student["성별"] # key가 "성별"인 쌍 삭제. 즉, {"성별": "여성"} 삭제

# 새로운 키(key)-값(value)쌍 추가
student["성별"] = "남자"  #{"성별 : "남자"} 쌍 추가


# 기존 키(key)에 대한 값(value) 변경
student["학년"] = 4   #{"학년": 4}로 변경

# 딕셔너리의 키(key) 목록 출력: .keys()
keys = student.keys()
print(keys)  # 출력: dict_keys(['이름', '학년', '성적', '과목', '성별'])

# 딕셔너리의 값(value) 목록 출력: .values()
values = student.values()
print(values)  # 출력: dict_values(['홍길동', 4, 95.5, ['수학', '과학', '영어'], '남자'])
```

## 4. dict_keys, dict_values, dict_items

1. dict_keys, dict_values, dict_items 객체는 리스트와 유사하지만 몇 가지 차이점이 있습니다.
2. 이 객체들은 리스트처럼 인덱싱으로 요소에 접근할 수 없으며, 수정할 수 없습니다.
3. 만약 리스트처럼 사용하려면 명시적으로 리스트로 변환해야 합니다. list()

```python
# 딕셔너리 생성
student = {
    'name': 'Alice',
    'age': 20,
    'major': 'Computer Science',
    'grade': 'A'
}

# keys() 메서드: 딕셔너리의 모든 키를 반환
keys = student.keys()
print(keys)  # 출력: 키: dict_keys(['name', 'age', 'major', 'grade'])

#딕셔너리의 모든 키를 리스트(list)로 변환
print(list(student.keys())) #출력: ['name', 'age', 'major', 'grade']

# values() 메서드: 딕셔너리의 모든 값(value)을 반환
values = student.values()
print(values)  # 출력: 값: dict_values(['Alice', 20, 'Computer Science', 'A'])

#딕셔너리의 모든 값(value)을 리스트(list)로 변환
print(list(student.values())) #출력: ['Alice', 20, 'Computer Science', 'A']

# items() 메서드: 딕셔너리의 모든 항목(key-value 쌍)을 반환
items = student.items()
print(items)
# 출력: 항목: dict_items([('name', 'Alice'), ('age', 20), ('major', 'Computer Science'), ('grade', 'A')])

#딕셔너리의 모든 항목(key-value 쌍)을 리스트로 변환
list(student.items())
# 출력:[('name', 'Alice'), ('age', 20), ('major', 'Computer Science'), ('grade', 'A')]
```

딕셔너리는 키-값 쌍을 사용하여 데이터를 구조화하고 쉽게 검색하고 업데이트할 수 있는 매우 유용한 자료형입니다.
---
layout: default
title: 스택
nav_order: 1
parent: 자료구조
permalink: docs/problemsolving/datastructure/stack
---

# 스택 
{: .no_toc }

## 목차
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 스택 (Stack)
**스택(Stack)**은 데이터를 일시적으로 저장하기 위해 사용하는 자료구조입니다. 스택의 데이터 입력과 출력의 순서는 **LIFO(Last In First Out)**, 후입선출입니다. 가장 먼저 들어간 것이 가장 나중에 나오는 형태로, 바구니에 물건을 담을 때를 생각하면 됩니다.

<p align="center">
  <img src="/docs/images/Stack.png" alt="스택의 구조"/><br/>
  스택의 구조
</p>

스택의 가장 위 요소는 가장 나중에 들어간 데이터입니다. 주로 **top**이라고 표현하며, 반대로 가장 아래 요소는 가장 먼저 들어간 데이터로 **bottom**이라고 합니다. 스택에 데이터를 입력하는 것을 "**push**한다."고 하며, 데이터를 추출하는 것은 "**pop**한다."라고 합니다. 스택에 들어있는 데이터들을 모두 조회할 순 있지만 **top에 있는 데이터만 접근 가능한**, 제한적인 자료구조입니다. 데이터를 추가할 때도 top 위에, 삭제할 때도 top에 있는 것을 삭제합니다. 커다란 바구니에서 위에 있는 것들을 만지지 않고 바구니 가장 아래에 있는 것만 꺼낼 수 없는 것과 같은 이치입니다.

Java에서는 기본 라이브러리로 Stack 클래스를 제공합니다.

```java
public class Stack<E> extends Vector<E>
```

**Stack의 주요 메소드**
* push - 스택에 데이터를 추가합니다.
* pop - 스택에서 데이터를 추출합니다.
* peek - top에 있는 데이터를 확인합니다.
* empty - 스택이 비어있는지 확인합니다.
* search - 선형 탐색을 통해 스택에서 데이터를 찾습니다.

그러나 Java에서 제공하는 Stack은 치명적인 단점이 있습니다. 바로 Vector 클래스를 상속하는 바람에 LIFO 구조가 보장되지 않는다는 것입니다. 이는 초창기 Java 개발자들에 의한 설계 과정에서의 실수로 우리의 의도와는 다르게 Stack 클래스를 통해 생성된 스택은 데이터들을 어디서든지 추가하고 삭제할 수 있습니다.

Java API 문서에서는 이런 문제의 해결법으로 Stack 클래스 대신 Deque 인터페이스를 통해 스택을 구현할 것을 추천하고 있습니다.

```java
Deque<Integer> stack = new ArrayDeque<Integer>();
```

이렇게 하면 LIFO 구조가 보장되며 Stack 클래스보다 더 빠른 스택을 사용할 수 있습니다. 물론 메소드들도 사용 가능합니다.
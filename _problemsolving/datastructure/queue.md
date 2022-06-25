---
layout: default
title: 큐
nav_order: 2
parent: 자료구조
permalink: docs/problemsolving/datastructure/queue
---

# 큐   
{: .no_toc }

## 목차
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 큐 (Queue)
**큐(Queue)**는 스택과 마찬가지로 데이터를 일시적으로 저장하기 위해 사용하는 자료구조입니다. 큐의 데이터 입력과 출력의 순서는 **FIFO(First in First Out)**, 선입선출입니다. 가장 먼저 들어간 것이 가장 먼저 나오는 형태로, 줄을 서거나 도로 교통을 생각하면 됩니다.

<p align="center">
  <img src="/docs/images/Queue.png" alt="큐의 구조"/><br/>
  큐의 구조
</p>

큐의 가장 앞 요소는 가장 먼저 들어간 데이터입니다. 주로 **front**라고 하며, 가장 뒤에 있는 요소는 제일 나중에 들어간 데이터로 **rear**라고 합니다. 큐에 데이터를 입력하는 것을 "**enqueue**한다.", 데이터를 추출하는 것은 "**dequeue**한다."라고 합니다. 큐는 선입선출 구조이기 때문에 배열 등을 이용해 구현할 때 데이터 추출 시 큐 안의 모든 요소를 이동해야합니다. 이 작업은 시간 복잡도가 $O(n)이나 되기 때문에 큐의 크기가 커질 수록 비효율적입니다. 따라서 보통 큐를 구현할 때는 **Ring Buffer** 자료구조를 이용해 구현합니다. Ring Buffer는 배열의 앞과 끝이 연결되어있다고 보는 자료구조로, 실제 물리적 구조가 원형은 아니지만 배열의 크기에 구애받지 않고 계속해서 값을 추가할 수 있습니다.

Java에서는 기본 라이브러리로 Queue 인터페이스를 제공합니다. 주로 LinkedList를 통해 구체화합니다.

```java
public interface Queue<E> extends Collection<E>
Queue<E> queue = new LinkedList<>();
```

**Queue의 주요 메소드**
Queue 인터페이스는 같은 기능을 담당하는 메소드가 두 가지 형태로 존재합니다. 한 형태는 연산 실패시 예외 발생, 다른 한 형태는 특정 값을 반환합니다.

* 예외 발생
    * add - 큐에 데이터를 추가합니다.
    * remove - 큐에서 데이터를 제거합니다.
    * element - 큐의 head에 있는 데이터를 확인합니다.
* 특정 값 반환
    * offer - 큐에 데이터를 추가합니다. 용량 제한적 큐에 선호됩니다.
    * poll - 큐에서 데이터를 제거합니다. 비어있을 경우 null을 반환합니다.
    * peek - 큐의 head에 있는 데이터를 확인합니다. 비어있을 경우 null을 반환합니다.

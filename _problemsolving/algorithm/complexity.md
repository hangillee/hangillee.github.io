---
layout: default
title: 복잡도
nav_order: 1
parent: 알고리즘
permalink: docs/problemsolving/algorithm/complexity
---

# 복잡도   
{: .no_toc }

## 목차
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 복잡도
복잡도(Complexity)는 컴퓨터 프로그램의 성능을 파악할 수 있는 척도로 사용됩니다. 복잡도에는 **시간 복잡도(Time Complexity)**와 **공간 복잡도(Space Complexity)**가 있습니다. 일반적으로 **빅 오 표기법(Big-O Notation)**을 통해 표현합니다. 복잡도를 신경쓰지 않는다면 컴퓨터의 자원을 과도하게 사용해, 사용자로 하여금 프로그램을 사용할 때 불편함을 느끼게 할 수 있습니다. 대표적으로, 시간 복잡도를 전혀 신경쓰지 않고 프로그램을 작성하게 되면 같은 작업을 수행하는 프로그램이라도 작업양에 따라 걸리는 시간이 급격하게 증가합니다. 같은 작업인데 어느 프로그램은 1초만에, 어느 프로그램은 10초가 걸린다면 당연히 더 빠른 프로그램을 사용할 것입니다. 따라서 프로그래머에게 복잡도 계산은 구체적으로는 아니더라도 꼭 해야하는 절차입니다.

## 시간 복잡도
먼저 복잡도 중 **시간 복잡도(Time Complexity)**에 대해 알아보겠습니다. 대표적인 시간 복잡도는 다음과 같습니다.

<table>
    <tr>
        <th colspan="4">시간 복잡도</th>
    </tr>
    <tr>
        <th>이름</th>
        <th>표기</th>
        <th>시간 (1000 기준)</th>
        <th>예시</th>
    </tr>
    <tr>
        <td>상수 시간</td>
        <td><em>O(1)</em></td>
        <td>1</td>
        <td>정렬된 숫자 배열에서 중위값 찾기, 짝수 홀수 판정하기</td>
    </tr>
    <tr>
        <td>로그 시간</td>
        <td><em>O(log n)</em></td>
        <td>9.97</td>
        <td>이분 탐색</td>
    </tr>
</table>
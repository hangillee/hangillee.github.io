---
layout: default
title: 재귀 알고리즘
nav_order: 4
parent: DS & Algorithm
permalink: docs/dsalgorithm/recursive
---

# 재귀 알고리즘   
{: .no_toc }

## 목차
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 재귀 알고리즘이란?
어떤 사건이 자기 자신을 **포함**하고 다시 자기 자신을 사용하여 정의될 때 **재귀적**(Recursive)이라 합니다. 이런 성질을 이용해 작성한 알고리즘이 **재귀 알고리즘**입니다. 재귀 알고리즘은 병합 정렬, 퀵 정렬, 이진탐색트리와 같은 여러 알고리즘과 자료구조에서 사용합니다.

## 팩토리얼 구하기
재귀 알고리즘을 사용하는 가장 대표적인 문제인 "팩토리얼 구하기"를 통해 재귀 알고리즘을 설명하겠습니다. 팩토리얼(Factorial) 혹은 계승(階乘)은 1부터 주어진 수까지의 모든 자연수를 곱하는 것을 의미합니다. 팩토리얼을 재귀적으로 정의하면 다음과 같습니다.

>1. 0! = 1 (팩토리얼의 정의입니다.)
>2. n! = n * (n-1)! (팩토리얼은 n까지의 모든 자연수를 곱하는 것입니다.)


```java
import java.util.Scanner;

public class Factorial {
    public static void main(String[] args) {
        Scanner myScan = new Scanner(System.in);
        int num = myScan.nextInt();

        System.out.println(num + "! = " + getFactorial(num));
        myScan.close();
    }

    static int getFactorial(int num) {
        if(num > 0) {
            return num * getFactorial(num - 1); //n! = n * (n-1)!
        }
        else { //팩토리얼의 정의에 따라 0은 1
            return 1;
        }
    }
}
```

재귀적 정의를 통해 팩토리얼을 구할 수 있는 아주 간단한 알고리즘을 작성했습니다. getFactorial 함수는 주어진 수가 0보다 클 때, 자기 자신인 getFactorial 함수를 호출하며 연산한 값을 반환합니다. 이를 **재귀 호출**(Recursive Call)이라고 합니다. getFactorial 함수의 처리 과정은 다음과 같습니다.

<p align="center">
  <img src="/docs/images/Factorial.png" alt="팩토리얼 알고리즘"/><br/>
  재귀 알고리즘을 이용한 팩토리얼 구하기
</p>

재귀 알고리즘의 핵심은 재귀 호출을 만났을 경우 호출된 함수의 내부로 들어간다는 것입니다. 계속 함수의 내부의 내부로 타고 들어가다 종료 조건(팩토리얼 구하기에서는 if문의 조건입니다.)을 만나면 값을 반환하고, 연산하고 다시 반환하는 과정을 거쳐 최종 결과 값을 도출해냅니다. getFactorial(num-1) 호출을 통해 최종적으로 num값이 0이 되었을 경우 1을 반환하며 getFactorial 함수의 return을 차례로 수행합니다.

이처럼 재귀 알고리즘은 시작(Top)에서 끝(Bottom)까지 쭉 재귀 호출 후, 종료 조건을 만나면 단계적으로 값을 반환해 시작으로 돌아갑니다. 이러한 재귀 알고리즘의 흐름을 이용해 재귀 알고리즘을 분석하는 두 가지 방법이 있습니다.

## 재귀 알고리즘 분석하기
---
layout: default
title: 탐색 알고리즘
nav_order: 2
parent: 알고리즘
has_children: true
permalink: docs/problemsolving/algorithm/search
---

# 탐색 알고리즘
{: .no_toc }

## 목차
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 탐색 알고리즘이란?
**"탐색 알고리즘"(Search Algorithm)**은 데이터 집합에서 원하는 값을 가진 요소를 찾아내는 알고리즘입니다. 주로 **key**라고 불리는 특정 항목을 통해 값을 찾아내며, key는 대부분 데이터의 일부입니다. 즉, 데이터의 일부를 key로 지정해 원하는 값을 찾아내는 것입니다. key는 찾고자 하는 값, 범위 혹은 유사한 항목 등이 될 수 있습니다. 탐색 알고리즘에는 크게 3가지가 있습니다.

>1. 선형 탐색 (Linear Search)
>2. 이진 탐색 (Binary Search)
>3. 해시 탐색 (Hash Search)

지금은 상대적으로 간단한 선형 탐색과 이진 탐색만 알아보도록 하겠습니다.

---

## 선형 탐색

선형 탐색은 매우 간단하고 직관적인 탐색 알고리즘입니다. 무작위로 나열되어 있는 배열의 **첫 번째 요소부터 마지막 요소까지 순서대로 전부 확인**해 key와 일치하는 요소를 찾습니다. 이는 배열의 크기가 작을 때나 찾고자 하는 값이 배열의 앞 부분에 있을 때는 크게 상관 없지만, 배열의 크기가 커지고 배열의 뒤로 갈수록 걸리는 시간이 늘어납니다. **선형 탐색의 종료 조건**을 정리하면 다음과 같습니다.

>1. 배열 끝까지 탐색했지만 찾는 값이 없습니다. (검색 실패)
>2. 배열 탐색 중 key와 일치하는 값이 있습니다. (검색 성공)

선형 탐색 알고리즘을 코드로 작성하면 다음과 같습니다.

```java
import java.util.Scanner;

public class linearSearch {
    static int search(int[] numArr, int key) {
        //선형 탐색
        for(int j = 0; j < 10; j++) {
            //탐색 성공
            if(key == numArr[j]) {
                return j;
            }
        }
        return -1;
    }
    
    public static void main(String[] args) {
        Scanner numScan = new Scanner(System.in);
        int[] numArr = new int[10];
        int result = 0; //탐색 결과 변수
        int key = 0; //Key 변수

        //무작위로 10개의 변수를 입력하고
        for(int i = 0; i < 10; i++) {
            numArr[i] = numScan.nextInt();
        }

        //찾으려는 Key값을 입력하고
        System.out.print("Key값을 입력해주세요 : ");
        key = numScan.nextInt();

        //탐색 결과를 받아오고
        result = search(numArr, key);

        //탐색 결과 출력
        if(result == -1) {
            System.out.println("일치하는 값이 없습니다.");
        }
        else {
            System.out.println("일치하는 값 : " + numArr[result]);
        }
    }
}
```

>p.s. 선형 탐색은 배열 자료구조에서 순서대로 검색하는 유일한 방법입니다.

---

## 이진 탐색

이진 탐색은 절대적인 전제 조건이 있습니다. 예외 없이 모든 데이터가 **"정렬"**되어 있어야합니다. 정렬 방식은 크게 상관 없으며, 오름차순이든 내림차순이든 정렬만 되어 있다면 언제든 사용 가능합니다. 이진 탐색은 선형 탐색보다 훨씬 빠른 속도를 가지고 있습니다. 따라서 정렬하는 과정이 추가되더라도 정렬 후 이진 탐색을 수행하는 것이 더 나은 경우가 있습니다.

이진 탐색은 간단하게 **"필요 없는 부분은 버린다."**라고 생각하면 쉽습니다. 데이터의 중앙값을 탐색한 후, 그 값이 찾고자하는 Key 값보다 작거나 크다면 중앙값보다 작거나 큰 부분에는 무조건 Key와 일치하는 부분이 존재하지 않을 것이기 때문에 과감하게 탐색 범위에서 제외합니다.

예를 들어, 크기가 10인 정수형 배열에 1부터 10까지 순서대로 들어가 있을 때, 7이라는 숫자를 찾는다면 중앙값인 5를 기준으로 7이 5보다 크기 때문에 5 이하의 숫자들은 탐색할 필요가 없습니다. 따라서 탐색의 시작점을 6으로 잡고 다시 탐색합니다. 선형 탐색과 다르게 시작부터 탐색의 범위가 절반으로 줄어듭니다. 매번 절반 씩 줄어들다보니 소요되는 시간도 매우 짧아집니다.

그러나 배열이 정렬되어 있지 않다면 이진 탐색은 아무것도 찾아내지 못합니다. 무작위로 배열에 저장되어 있는 수에서 찾고자 하는 값이 중앙값보다 작거나 크다고 확신할 수 없기 때문에 이진 탐색을 위해선 정렬이 선행되어야 하는 것입니다.

이진 탐색 알고리즘을 코드로 작성하면 다음과 같습니다.

```java
import java.util.Scanner;

public class binSearch {
    static int search(int[] numArr, int mid, int key) {
        int first = 0; //탐색 시작 위치
        int last = 9; //탐색 끝 위치
        //이진 탐색
        do {
            //중앙값의 위치는 시작 위치와 끝 위치의 중간으로
            mid = (last + first) / 2;
            //만약 중앙값이 Key보다 작으면
            if(numArr[mid] < key) {
                //탐색 시작 위치를 중앙값 위치의 다음으로
                first = mid + 1;
            }
            //만약 중앙값이 Key보다 크면
            else if(numArr[mid] > key) {
                //탐색 끝 위치를 중앙값 위치의 이전으로
                last = mid - 1;
            }
            //만약 중앙값과 Key가 일치하면
            else if (numArr[mid] == key){
                //중앙값의 위치 반환
                return mid;
            }
        } while (first <= last);
        return -1;
    }

    public static void main(String[] args) {
        Scanner numScan = new Scanner(System.in);
        int[] numArr = new int[10];
        int key = 0;
        int mid = 0;
        int result = 0;

        for(int i = 0; i < 10; i++) {
            numArr[i] = i;
        }

        //중앙값을 배열 크기의 절반으로 초기화
        mid = numArr.length / 2;
        //Key 값 입력 받기
        key = numScan.nextInt();

        result = search(numArr, mid, key);

        if(result == -1) {
            System.out.println("값이 없습니다.");
        }
        else {
            System.out.println("찾고자 하는 값은 : " + result + "에 있습니다.");
        }
    }
}
```
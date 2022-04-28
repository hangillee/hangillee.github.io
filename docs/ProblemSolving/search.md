---
layout: default
title: 탐색 알고리즘
nav_order: 1
parent: ProblemSolving
permalink: docs/problemsolving/search
---

# 탐색 알고리즘   

{: .no_toc }

**"탐색 알고리즘"(Search Algorithm)**은 데이터 집합에서 원하는 값을 가진 요소를 찾아내는 알고리즘입니다. 주로 **key**라고 불리는 특정 항목을 통해 값을 찾아내며, key는 대부분 데이터의 일부입니다. 즉, 데이터의 일부를 key로 지정해 원하는 값을 찾아내는 것입니다. key는 찾고자 하는 값, 범위 혹은 유사한 항목 등이 될 수 있습니다. 탐색 알고리즘에는 크게 3가지가 있습니다.

>1. 선형 탐색 (Linear Search)
>2. 이진 탐색 (Binary Search)
>3. 해시 탐색 (Hash Search)

---

**1. 선형 탐색**

선형 탐색은 매우 간단하고 직관적인 탐색 알고리즘입니다. 무작위로 나열되어 있는 배열의 **첫 번째 요소부터 마지막 요소까지 순서대로 전부 확인**해 key와 일치하는 요소를 찾습니다. 이는 배열의 크기가 작을 때나 찾고자 하는 값이 배열의 앞 부분에 있을 때는 크게 상관 없지만, 배열의 크기가 커지고 배열의 뒤로 갈수록 걸리는 시간이 늘어납니다. **선형 탐색의 종료 조건**을 정리하면 다음과 같습니다.

>1. 배열 끝까지 탐색했지만 찾는 값이 없습니다. (검색 실패)
>2. 배열 탐색 중 key와 일치하는 값이 있습니다. (검색 성공)

선형 탐색 알고리즘을 코드로 작성하면 다음과 같습니다.

```java
import java.util.Scanner;

public class linearSearch {
    static int search(int[] num, int key) {
        //선형 탐색
        for(int j = 0; j < 10; j++) {
            //탐색 성공
            if(key == num[j]) {
                return j;
            }
        }
        return -1;
    }
    
    public static void main(String[] args) {
        Scanner numScan = new Scanner(System.in);
        int[] num = new int[10];
        int result = 0; //탐색 결과 변수
        int key = 0; //Key 변수

        //무작위로 10개의 변수를 입력하고
        for(int i = 0; i < 10; i++) {
            num[i] = numScan.nextInt();
        }

        //찾으려는 Key값을 입력하고
        System.out.print("Key값을 입력해주세요 : ");
        key = numScan.nextInt();

        //탐색 결과를 받아오고
        result = search(num, key);

        //탐색 결과 출력
        if(result == -1) {
            System.out.println("일치하는 값이 없습니다.");
        }
        else {
            System.out.println("일치하는 값 : " + num[result]);
        }
    }
}
```

>p.s. 선형 탐색은 배열 자료구조에서 순서대로 검색하는 유일한 방법입니다.

---

**2. 이진 탐색**

이진 탐색은 절대적인 전제 조건이 있습니다. 이진 탐색을 사용하기 위해선 예외 없이 모든 데이터가 **"정렬"**되어 있어야합니다.

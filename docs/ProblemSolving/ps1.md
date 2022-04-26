---
layout: default
title: 기본 알고리즘
nav_order: 1
parent: ProblemSolving
permalink: docs/problemsolving/ps1
---

# 기본 알고리즘

"알고리즘"은 다음과 같이 정의할 수 있습니다.

> 문제를 해결하기 위한 것으로, 명확하게 정의되고 순서가 있는 유한 개의 규칙으로 이루어진 집합

간단하게는 문제 풀이에 필요한 계산 절차, 처리 과정의 순서를 뜻합니다. 알고리즘은 언제나 명확하게 정의되어야 하기 때문에 대입되는 변수들에 따라 항상 옳은 값이 도출되지 않고 결과가 달라진다면 알고리즘이라 할 수 없습니다.

---

### 1. 알고리즘이란?
   
앞서 알고리즘의 정의를 살펴보면서 알고리즘의 기본 조건을 알 수 있었습니다. 알고리즘은 항상 옳은 답을 내야하며, 알고리즘을 작성한 사람이 의도하지 않은 답이 나올 경우 알고리즘이라 할 수 없습니다. 간단한 예시를 통해 프로그래밍에서의 알고리즘을 알아보겠습니다. 
   
**세 값의 최댓값 구하기**   
<pre>
<code>
import java.util.Scanner;

public class getMaxValue {
    public static void main(String[] args) {
        Scanner numScan = new Scanner(System.in);
        int[] numArr = new int[3];
        int maxValue = 0;

        for(int i = 0; i < 3; i++) {
            numArr[i] = numScan.nextInt();
        }

        maxValue = numArr[0];

        if(maxValue < numArr[1]) {
            if(numArr[1] < numArr[2]) {
                maxValue = numArr[2];
            }
            else {
                maxValue = numArr[1];
            }
        }
        else if(maxValue < numArr[2]) {
            maxValue = numArr[2];
        }

        System.out.println("최댓값은 : " + maxValue);
        numScan.close();
    }
}
</code>
</pre>
   
위 프로그램은 **Java** 로 작성되었습니다. **반복문** 을 통해 사용자로부터 받아온 3개의 변수를 **배열 자료구조** 에 저장했고, **조건문** 으로 원하는 결과를 도출하기 위한 프로그램을 작성했습니다. 입력된 3개의 변수의 순서와 상관 없이 항상 최댓값을 출력하므로 이 프로그램은 알고리즘이라 할 수 있습니다. 이 짧은 프로그램에서 우리는 알고리즘을 작성할 때 자주 사용하게 되는 여러 요소들을 확인해볼 수 있습니다.

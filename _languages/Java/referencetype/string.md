---
layout: default
title: String
parent: 참조 자료형
grand_parent: Java
permalink: docs/languages/java/04/String
---

# String
{: .no_toc }

## 목차
{: .no_toc }

1. TOC
{:toc}

---

## 문자열(String)이란?
문자열(String)은 문자가 나열된 것, "문장"을 뜻하는 말이다. Java에서는 문자열을 저장할 때는 String 자료형을 사용한다. 문자열을 저장하는 방법은 두 가지가 있다. 문자열은 원시 자료형의 문자 자료형인 `char`와 다르게 **""(이중 인용부호, 큰 따옴표)**를 사용해야한다.

```java
String helloLiteral = "안녕하세요!";
String helloNew = new String("안녕하세요!");
```

첫 번째는 **리터럴(Literal) 표기법**을 통해 **안녕하세요!**라는 문자열 객체의 주소를 **String 자료형**으로 선언된 **helloLiteral 변수**에 저장하는 방법이다. 리터럴은 '정확한'이란 뜻으로, 프로그래밍에선 **고정된 값**을 뜻한다. "안녕하세요!"라는 문자열은 정확하고 고정된 값으로, 이렇게 프로그래머가 직접 값을 작성하는 방식을 리터럴 표기법이라 한다.

두 번째는 `new` 키워드를 통해 String 객체를 생성하는 방법이다. 저장하는 방식은 둘 모두 같다. 두 방법 모두 문자열 객체를 생성하지만, 주로 첫 번째 방법이 사용된다. 가독성과 컴파일 최적화에 있어 이점이 있기 때문이다. 또한 같은 문자열 "안녕하세요!"를 대입한 것처럼 보이지만 동일한 객체는 아니다. 리터럴 표기법으로 생성된 문자열 객체는 **공유**되기 때문이다. 만약 새로 만든 변수에 똑같이 "안녕하세요!"라는 문자열을 대입하면 기존에 생성되었던 "안녕하세요!"라는 문자열이 대입된다.

이것이 가능한 이유는 **String interning**에 있다. JVM에서는 클래스가 생성될 때, 문자열 객체를 관리하는 풀(Pool)을 생성한다. 이때, 리터럴로 작성된 문자열 객체를 풀에 저장하고 있다가 같은 문자열을 리터럴 표기법으로 다시 사용하려하면 이미 저장되어 있는 문자열을 반환해준다. 즉, 새로운 문자열 객체가 생성되는 것이 아니다.

반면, `new` 키워드를 통해 생성한 문자열 객체는 같은 문자열이라 하더라도 몇 번이고 새로운 객체가 생성된다. 따라서 메모리를 고려해서라도 첫 번째 방법인 리터럴 표기법이 문자열 객체를 생성할 때 더 효율적이다.

---

## 내장 메소드
참조 자료형답게 String 자료형으로 선언된 변수는 메소드를 직접 호출 할 수 있다.
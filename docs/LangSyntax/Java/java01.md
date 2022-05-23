---
layout: default
title: Java란 무엇인가?
nav_order: 1
parent: Java
permalink: docs/langsyntax/java/01
---

# Java란 무엇인가? 
{: .no_toc }

{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Java!
**Java**는 1995년, 미국의 Sun Microsystems의 소프트웨어 개발자 제임스 고슬링이 개발한 **객체 지향 프로그래밍 언어**다. Java는 현재 다양한 분야에서 활용되는 언어로 Python과 더불어 세계에서 가장 인기 있는 프로그래밍 언어 중 하나다.

## Java의 특징
2010년 Sun Microsystems를 인수한 후, Java를 관리하고 있는 Oracle에서는 Java의 디자인 목표를 소개하고 있다. 이 디자인 목표들은 곧 Java의 특징이기도 하다.

1. Simple, Object Oriented, and Familiar
    - 간단하고, 객체 지향적이고, 친숙하게. Java는 High-level 언어들에 있는 여러 요소들 중 반드시 필요하지 않다고 생각되는 것들은 과감히 제외해 간단하면서도 친숙하다. 또한 객체 지향적 언어로 설계되어 숫자나 논리값을 제외하면 거의 모든 것이 객체로 구성되어 있다.
2. Robust and Secure
    - 강력하고 안전하게. Java는 Pointer 연산을 지원하지 않는다. 프로그래머가 잘못된 주소를 가르키지 않도록 사전에 제한한 것으로 시스템 붕괴의 우려가 없다. 또한 가비지 콜렉터(GC)를 통해 자동으로 사용이 종료된 요소는 메모리에서 삭제해 메모리 누수에 대한 고민도 필요 없다. 거기다 자료형 체크에 매우 민감해 잘못된 코드를 적지 않게끔 도와준다. 이는 안전하면서도 유연성이 떨어지기도 한다.
3. Architecture Neutral and Portable
    - 아키텍처 중립적이고 휴대 가능하게. Java는 Java Virtual Machine(JVM) 덕분에 어떤 플랫폼에서든 컴파일되고 사용 가능하다. 기존의 프로그래밍 언어들은 OS의 영향을 받아 Windows에서 개발한 프로그램은 Linux나 MacOS에서 사용이 불가능했다. 그러나 Java로 개발된 프로그램은 JVM만 설치 가능하다면 어디에서든 구동된다.
4. High Performance
    - 고성능. Java는 항상 성능을 고려한다. Java는 Runtime 환경을 확인하지 않고도 인터프리터가 최대 속도로 실행될 수 있는 체계를 채택해 최고 성능에 도달 할 수 있도록 했다.
5. Interpreted, Threaded, and Dynamic
    - 인터프리터, 쓰레드, 그리고 동적. Java는 엄밀히 따지면 컴파일 언어이자 인터프리터 언어이다. Java로 작성한 프로그램은 두 가지 과정을 거쳐 실행되는데, 먼저 컴파일을 통해 class 파일을 만들고 Java Runtime이 class 파일을 인터프리팅하며 실행한다. 또한 멀티 쓰레딩을 지원해 동시에 여러 일을 처리할 수 있는 높은 효율을 가졌고, 인터페이스 기능을 이용하면 코드를 모듈화해 수정이 필요할 때 모든 코드를 갱신할 필요가 없다.

## Hello, world! in Java
Java의 간략한 역사와 특징들을 알아봤으니 이제 Java 코드는 어떻게 생겼는지 알아보자.

```Java
public class HelloJava {
    public static void main(String[] args) {
        System.out.println("Hello, world!");
    }
}
```

사실 이 간단한 코드의 모든 구성 요소를 막힘 없이 설명할 수 있으면 Java의 기초는 숙지했다고 할 수 있다. **접근제어자**, **클래스**, **static**, **메소드** 등, Java의 중요한 기본기들을 대부분 포함하고 있는 좋은 예제이다. 기능은 *Hello, world!*라는 문자열을 출력하는게 전부이지만, Java를 알아가는데는 너무 중요한 코드다. 난 내가 정리한 Java 문법을 모두 공부하고 돌아왔을 때 이 코드를 완벽히 설명할 수 있을 때까지 복습할 것이다.
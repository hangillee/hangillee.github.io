---
layout: default
title: 임시
nav_order: 1
parent: Spring Boot & JPA
permalink: docs/techstack/springbootjpa/01
---

# 임시 정리   
{: .no_toc }

## 목차
{: .no_toc .text-delta }

1. TOC
{:toc}

---

**본 문서는 인프런에서 수강할 수 있는 [실전! 스프링 부트와 JPA 활용1 - 웹 애플리케이션 개발](https://www.inflearn.com/course/스프링부트-JPA-활용-1/dashboard)을 수강한 후, 공부한 내용을 정리한 문서입니다. 본 문서의 모든 저작권은 해당 강의의 저자이신 [김영한](https://inflearn.com/users/@yh) 우아한형제들 기술이사님께 있습니다.**

공부 중 임시로 정리해두는 페이지입니다. 추후 다시 제대로 정리해서 포스팅 할 예정입니다.

## 개발 과정
도메인 분석 설계(엔티티 개발) - 애플리케이션 구현 준비 - 도메인 세부 개발 (회원, 상품, 주문) - 웹 계층 개발

## 그외 메모...
JPA, DB 설정 application.yml

개발 요구사항을 파악하고 구현해야하는 기능들을 정리...

도메인 모델과 DB 테이블 설계(도메인 간의 관계 설정), 각 엔티티 분석 후 필요한 구현 내역 정리(DB 컬럼 == Enitity meber variable)

연관관계 매핑 분석 (1:N, N:1, N:N). 외래 키(Foreign Key)가 있는 곳을 연관관계의 주인으로. (JoinColumn의 위치)

Lombok을 통해 Getter Setter 자동 생성. Getter는 열어두고 Setter는 가급적 닫아둬야 함. (side effect 방지)

@Entity 스프링 빈을 엔티티화

@Setter 제거하고 @Embeddable 붙여서 객체 생성 이후에 추가 변경이 없어야 한다.

Primary Key는 @Id @GeneratedValue @Column(name = "") 사용해서 지정

@OneToMany @ManyToOne @ManyToMany 연관관계 어노테이션 다대다는 사실 쓸일 없음..

cascade, fetch 좀 더 공부해볼 것

연관관계 주인 @JoinColumn(조인 할 대상 컬럼), 연관관계 대상 @연관관계(mappedBy = "주인 컬럼")

@Inheritance(strategy = InheritanceType.SINGLE_TABLE) 상속 관계 전략 설정. 한 테이블로 모든 컬럼 합침(싱글 테이블)
@DiscriminatorColumn(name = "dtype") 합쳐진 상속 관계 테이블들을 구분할 구분자 컬럼
@Discriminator("A") 그 컬럼에 들어갈 구분자

연관 관계는 지연 로딩으로 설정해야함. fetch = FetchType.LAZY)

컬렉션에선 NullPointerException 피하고 side effect 회피를 위해 컬렉션은 선언 즉시 바로 초기화하자.

하이버네이트에선 필드명을 카멜 케이스는 언더스코어(_)로 .(도트)도 언더스코어 바꾼다. 대문자는 모두 소문자가 된다. (Java 코드로 짤 때부터 소문자로 쓰자)

컬럼, 테이블명 명시 안하면 내부에서 논리적으로 생성됨. (위의 규칙들)

계층형 구조 사용할 것. controller, web(웹) -> service(비즈니스 로직) -> repository(JPA 직접 사용할 계층, 엔티티 매니저 사용됨)
엔티티가 모여있는 계층 domain(모든 계층에서 참조)

@Service @Repository 있다.
@Transactional 트랜잭션, 영속성 컨텍스트
@Autowired 생성자 주입에서 사용됨

검증 로직이 있어도 멀티 쓰레드(동시에 다중 사용자)를 고려해 DB 테이블에 회원명 컬럼을 유니크 제약 조건을 걸어두자

스프링 필드 주입 X, 생성자 주입 O
Spring Data JPA를 사용하면 EntityManager도 주입 가능

테스트 코드 작성 생활화

JPQL 냅다 String으로 적으면 너무 복잡해짐
그렇다고 Java 표준 JPA Criteria는 실제 쿼리가 무엇이 쓰이는지 알 방법이 없음
해결법 QueryDSL
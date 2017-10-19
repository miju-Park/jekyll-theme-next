---
title: 1장. 좋은 소프트웨어 만들기
categories:
 - Javascript Pattern & Test
tags:
---
책 자바스크립트 패턴과 테스트의 내용

********
**1. 바르게 시작하는 코드 작성하기**

* 자바스크립트에서의 함수 오버로딩

자바스크립트 자체에서 함수 오버로딩을 지원하는 것은 아님. 함수의 arguments를 보고 여기에 맞추는 행위

* Duck Typing (덕 타이핑)

동적 타이핑의 한 종류. 객체의 변수 및 메소드의 집합이 객체의 타입을 결정<br>
객체의 타입보다 객체가 사용되는 양상이 더 중요.

* this

this가 있는 곳의 함수를 호출하는 ‘점(.) 앞의 객체(object before the dot)’<br>
this는 함수를 호출한 객체를 참조

* SOLID 원칙

다섯 가지 객체 지향 설계 원칙<br>
**S**ingle Responsibility Principle (단일 책임 원칙)<br>
> 모든 클래스 (함수) 는 반드시 한 가지 변경 사유가 있어야 한다. <br>

**O**pen/Closed Principle (개방/폐쇄 원칙)<br>
> 모든 소프트웨어 개체는 확장 가능성은 열어두되 수정 가능성은 닫아야 한다.<br>

**L**iskov Substitution Principle (리스코프 치환 원칙)<br>
> 어떤 타입에서 파생된 타입의 객체가 있다면 이 타입을 사용하는 코드는 변경하지 말아야 한다.<br>

**I**nterface Segregation Principle (인터페이스 분리 원칙)<br>
> 기능이 많은 인터페이스는 더 작게 응축시킨 조각으로 나누어야 한다는 발상<br>

**D**ependency Inversion Principle (의존성 역전 원칙)<br>
> 상위 수준 모듈은 하위 수준 모듈에 의존해서는 안되며 이 둘은 추상화에 의존해야 한다.<br>


* DRY 원칙 (Don't Repeat Yourself)


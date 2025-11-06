# JAVA
## 11월 6일

## 패키지 개념과 필요성
- 여러명이 분담해 작업할 경우 동명의 클래스가 존재할 수 있음(오류가능성 존재)
- 개발자가 서로 다른 디렉터리 코드로 관리하면 해결

## 자바의 패키지와 모듈이란?
* 패키지
  * 서로 관련된 클래스와 인터페이스를 컴파일한 클래스를 묶어놓은 디렉토리
  * 하나의 응용프로그램은 한개 이상의 패키지로 작성
  * 패키지는 jar 파일로 압축 가능
* 모듈
  * 여러 패키지와 이미지 등의 자원을 모아놓은 컨테이너
  * 하나의 모듈을 하나의 .jmod파일에 저장
* JAVA 9부터 모듈화 도임
  * 플랫폼의 모듈화: JAVA 9부터 자바API의 모든 클래스들을 패키지기반에서 모듈들로 완전히 재구성함
  * 응용프로그램의 모듈화: 클래스들은 패키지로 만들고 다시 패키지 모듈로 만듦
* 모듈화의 목적
  * Java 9부터 자바API를 99개 모듈로 분할: Java 8까지는 rt.jar의 한 파일에 모는 API저장 (현재는 70개)
* 자바 JDK에 제공되는 모듈 파일(jmod확장자 모든파일 모듈은 ZIP파일)

![tech](https://private-user-images.githubusercontent.com/200943901/510788032-e8ce840f-f103-42b9-8c2d-42b3509cea78.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NjI0MzY0MjcsIm5iZiI6MTc2MjQzNjEyNywicGF0aCI6Ii8yMDA5NDM5MDEvNTEwNzg4MDMyLWU4Y2U4NDBmLWYxMDMtNDJiOS04YzJkLTQyYjM1MDljZWE3OC5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUxMTA2JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MTEwNlQxMzM1MjdaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1hMjMzZDdmN2U2MDEyN2E5MDNhZmM0NmNjYTE2NTA2ZWFmYzc3MDA5OTE2OWIyZjMwZTcxMmMwOTAwNjU3ZTQwJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.2MMrsJsg_tRAWWHX4ceOKao8R8oFUQXAPvjnKDdcUNc)

## 10월 31일


## 인터페이스의 구성 요소들의 특징 * **상수** :
- public만 허용,

- public static final 생략

추상 메소드 :

- public abstract 생략 가능

default 메소드 :

- 인터페이스에 코드가 작성된 메소드

- 인터페이스를 구현하는 클래스에 자동 상속

- public 접근 지점만 허용. 생략 가능

private 메소드 :

- 인터페이스 내에 메소드 코드가 작성되어야 함

- 인터페이스 내에 있는 다른 메소드에 의해서만 호출 가능

static 메소드 : public, private 모두 지정 가능. 생략하면 public

자바 인터페이스 특징
인터페이스의 객체 생성 불가
인터페이스 타입의 레퍼런스 변수 선언 가능
인터페이스 상속
인터페이스 간에 상속 가능 :

- 인터페이스를 상속하여 확장된 인터페이스 작성 가능

- extends 키워드로 상속 선언

인터페이스 다중 상속 허용 (* 일반 상속에서는 허용하지 않음)

인터페이스 구현
인터페이스의 추상 메소드를 모두 구현한 클래스 작성
implements 키워드 사용
여러 개의 인터페이스 동시 구현 가능
인터페이스 구현 사례
PhoneInterface 인터페이스를 구현한 SamsungPhone 클래스
추상 클래스
추상 메소드(abstract method)

:abstract로 선언된 메소드, 메소드의 코드는 없고 원형만 선언

abstract public String getName();
abstract public String fail() { return "Good Bye".} // 추상 메소드 아님. 컴파일 오류
추상 클래스(abstract class)

- 추상 메소드를 가지며, abstract로 선언된 클래스

- 추상 메소드 없이, abstract로 선언한 클래스

// 추상 메소드를 가진 추상 클래스
abstract class Shape {
public Shape() {...}
public void edit() {...}

    abstract public void draw(); // 추상 메소드
}
// 추상 메소드 없는 추상 클래스
abstract class JComponent {
String name;
public void load(String name) {
this.name = name;
}
}
추상 클래스의 인스턴스 생성 불가
추상 클래스는 온전한 클래스가 아니기 때문에 인스턴스를 생성할 수 없음
JComponent p; // 오류 없음. 추상 클래스의 레퍼런스 선언
p = new JComponent(); // 컴파일 오류. 추상 클래스의 인스턴스 생성 불가
Shape obj = new Shape(); // 컴파일 오류. 추상 클래스의 인스턴스 생성 불가
추상 클래스의 상속과 구현
추상 클래스 상속
추상 클래스를 상속받으면 추상 클래스가 됨
서브 클래스도 abstract로 선언해야 함
abstract class A { // 추상 클래스
abstract public int add(int x, int y); // 추상 메소드
}
abstract class B extends A { // 추상 클래스
public void show() { System.out.println("B");}
}
A a = new A(); // 컴파일 오류. 추상 클래스의 인스턴스 생성 불가
B b = new B(); // 컴파일 오류. 추상 클래스의 인스턴스 생성 불가
추상 클래스 구현
서브 클래스에서 슈퍼 클래스의 추상 메소드 구현 (오버라이딩)
추상 클래스를 구현한 서브 클래스는 추상 클래스 아님
class C extends A { // 추상 클래스 구현. C는 정상 클래스
public int add(int x, int y) { return x+y } // 추상 메소드 구현. 오버라이딩
public void show() { System.out.println("C"); }
}
...
C c = new C(); // 정상
추상 클래스의 목적
추상 클래스의 목적

- 상속을 위한 슈퍼 클래스로 활용하는 것

- 서브 클래스에서 추상 메소드 구현

- 다형성 실현

super 키워드로 슈퍼 클래스에 접근
슈퍼 클래스의 멤버에 접근시 사용하는 레퍼런스
super.슈퍼클래스의 맴버
서브 클래스에서만 사용
슈퍼 클래스의 필드 접근
슈퍼 클래스의 메소드 호출시 super로 이루어지는 메소드 호출 : 정적 바인딩
메소드 오버라이딩(Method Overriding)의 개념
서브 클래스에서 슈퍼 클래스의 메소드 중복 작성

슈퍼 클래스의 메소드 무력화, 항상 서브 클래스에 오버라이딩한 메소드가 실행되도록 보장됨

메소드 무시하기로 번역되기도 함

오버라이딩 조건

슈퍼 클래스 메소드의 원형(메소드 이름, 인자 타입 및 개수, 리턴 타입) 동일하게 작성

서브 클래스 객체와 오버라이딩된 메소드 호출
오버라이딩 한 메소드가 실행됨을 보장
clas A {
void f() {
System.out.println("A의 f() 호출");
}
}
class B extends A {
void f() {
System.out.println("B의 f() 호출");
}
}
오버라이딩의 목적, 다형성 실현
오버라이딩으로 다형성 실현
하나의 인터페이스(다른 이름)에 서로 다른 구현
슈퍼 클래스의 메소드를 서브 클래스에서 각각 목적에 맞게 다르게 구현
사례 : shape의 draw() 메소드를 Line, Rect Circle에서 오버라이딩하여 다르게 구현
instanceof 연산자 사용
레퍼런스가 가리키는 객체의 타입 식별 : 연산의 결과는 true/false의 불린 값으로 반환
객체레퍼런스 instanccof 클래스 타입

Person p = new Professor();

if(p instanceof Person) // true
if(p instanceof Student) // false, Student를 상속받지 않음
if(p instanceof Researcher) // true
if(p instanceof Professor) // true
if("java" instanceof String) // true


## 10월 30일

# final
#### 한번 값을 할당하면 변경 불가한 상수
# 메소드의 제약 조건
- static메소드는 static멤버에서만 사용 가능
- static메소드는 제한 없이 사용가능하기에 non-static멤버는 사용 불가
# 상속의 필요성
### 상속이 없는경우 중복된 4개의 클래스
# 클래스 상속
- 상속 선언: extend
- 부모클래스를 물려받아 자식클래스 확장
- 부모클래스 -> 슈퍼클래스(super class)
- 자식클래스 -> 서브클래스(sub class)
- colorpoint는 상속이다
# 업캐스팅
- 하위 클래스의 레퍼런스는 상위 클래스를 가리킬 수 없지만, 상위 클래스의 레퍼런스는 하위 클래스를 가리킬 수 있다는 설명
- 생물이 들어가는 박스에 사람이나 코끼리를 넣어도 무방
- 사람이나 코끼리 모두 생물을 상속받았기 때문
## 업캐스팅이란?
- 서브 클래스의 레퍼런스를 슈퍼 클래스 레퍼런스에 대입
- 슈퍼 클래스 레퍼런스로 서브 클래스 객체를 가리키게 되는 현상
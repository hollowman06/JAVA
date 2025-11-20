# JAVA

## 11월 20일

## 

(11월 13일 강의)
컨테이너와 컴포넌트
컨테이너

-다른 컴포넌트를 포함할 수 있는 GUI 컴포넌트 : java.awt.Container를 상속받음

-다른 컨테이너에 포함될 수 있음

-AWT 컨테이너 : Panel, Frame, Applet, Dialog, Window

-Swing 컨테이너 : JPanel, JFream, JApplet, JDialon, JWindow

컴포넌트

-컨테이너에 포함되어야 화면에 출력될 수 있는 GUI 객체

-다른 컴포넌트를 포함할 수 없는 순수 컴포넌트

-모든 GUI 컴포넌트가 상속받는 클래스 : java.awt.Component

-스윙 컴포넌트가 상속받는 클래스 : javax.swing.Jcomponent

최상위 컨테이너

-다른 컨테이너에 포함되지 않고도 화면에 출력되며, 독립적으로 존재 가능한 컨테이너

-스스로 화면에 자신을 출력하는 컨테이너 : JFrame, JDialog, JApplet

Swing 프레임
스윙 프레임 : 모든 스윙 컴포넌트를 담는 최상위 컨테이너

-JFrame을 상속받아 구현

-컴포넌트들은 화면에 보이려면 스윙 프레임에 부착되어야 함

-프레임을 닫으면 프레임에 부착된 모든 컴포넌트가 보이지 않게 됨

스윙 프레임(JFrame) 기본 구성

-프레임 : 스윙 프로그램의 기본 틀

-메뉴바 : 메뉴들이 부착되는 공간

-컨텐트팬 : GUI 컴포넌트들이 부착되는 공간

img.png

프레임 만들기, JFrame 클래스 상속
스윙 프레임

-JFrame 클래스를 상속받은 클래스 작성

-프레임의 크기 반드시 지정 : setSize() 호출

-프레임을 화면에 출력하는 코드 반드시 필요 : setVisible(true) 호출

프레임에 컴포넌트 붙이기
타이틀 달기

-super()나 setTitle() 이용

MyFrame() {
super("타이틀문자열");
}
컨텐트팬에 컴포넌트 달기

-컨텐트팬이란? 스윙 컴포넌트들이 부착되는 공간

-컨텐트팬 알아내기 : 스윙 프레임에 붙은 디폴트 컨텐트팬 알아내기

public class myFrame extends JFrame {
MyFrame() {
Cotainer contentPane = getContentPane();
}
}
-컨텐트팬에 컴포넌트 붙이기

-컨텐트팬 변경
Tip. 컨텐트팬에 대한 JDK 1.5 이후의 추가 사항
JDK 1.5 이전

-프레임의 컨텐트팬을 알아내어, 반드시 컨텐트팬에 컴포넌트 부착

Container c = frame.getContentPane();
c.add(new JButton("Click")); // 컨텐트팬에 직접 컴포넌트 부착
JDK 1.5 이후 추가된 사항 -프레임에 컴포넌트를 부착하면 프레임이 대신 컨텐트팬에 부착
frame.add(new JButton("Click"));
// 프레임이 버튼 컴포넌트를 컨텐트팬에 대신 부착
저자의 결론

-JDK1.5 이전처럼 직접 컨텐트팬에 컴포넌트를 부착하는 것이 바람직함

-컨텐트팬 다루기 능력 필요하기 때문

-컴포넌트의 부모가 프레임이 아닌, 컨텐트팬임을 알고 명확히 사용할 필요

자바의 GUI(Graphical User Interface)
GUI : 사용자가 편리하게 입출력 할 수 있도록 그래픽으로 화면을 구성하고, 마우스나

키보드로 입력 받을 수 있도록 지원하는 사용자 인터페이스

자바 언어에서 GUi 응용프로그램 작성 : AWT와 Swing 패키지에 강력한 GUI 컴포넌트 제공

[AWT(Abstract Windowing Toolkit) 패키지]

자바가 처음 나왔을 때부터 배포된 GUI 패키지, 최근에는 거의 사용하지 않음
AWT 컴포넌트는 중량 컴포넌트(heavy weight component)
AWT 컴포넌트의 그리기는 운영체제에 의해 이루어지며, 운영체제에 의 자원을 많이 소모하고 부담을 줌
운영체제가 직접 그리기 때문에 속도는 빠름
[Swing 패키지]

AWT 기술을 기반으로 작성된 자바 라이브러리

모든 AWT 기능 + 추가된 풍부하고 화려한 고급 컴포넌트

AWT 컴포넌트를 모두 스윙으로 재작성

AWT 컴포넌트를 모두 스윙으로 재작성

AWT 컴포넌트 이름 앞에 J자를 덧붙임

순수 자바 언어로 구현

스윙 컴포넌트는 경량 컴포넌트(light weight component)

스윙 컴포넌트는 운영체제의 도움을 받지 않고, 직접 그리기 때문에 운영체제에 부담주지 않음

현재 자바의 GUI 표준으로 사용됨

toString() 메소드, 객체를 문자열로 변환
각 클래스는 toString()을 오버라이딩하여 자신만의 문자열로 리턴 가능

-객체를 문자열로 반환

-원형 : public String toString();

컴파일러에 의한 toString() 자동 변환

-'객체 + 문자열'->'객체.toString() + 문자열'로 자동 변환

-객체를 단독으로 사용하는 경우 -> 객체.toString()으로 자동변환

객체 비교(==)와 equals() 메소드
== 연산자 : 객체 레퍼런스 비교
Point a = new Point(2,3) ;
Point b = new Point(2,3) ;
Point c = new Point(3,4) ;
if(a == b) System.out.println("a==b");
if(a.equals(b)) {
System.out.println("a is equal to b");
}
if(a.equals(c)) {
System.out.println("a is equal to c");
}
boolean equals(Object obj)
두 객체의 내용물 비교
객체의 내용물을 비교하기 위해 클래스의 맴버로 작성
Wrapper 클래스
Wrapper 클래스 : 자바의 기본 타입을 클래스화 한 8개 클래스를 통칭

기본 타입 ... |byte|short|int....|long char float double boolean

Wrapper 클래스|Byte|Short|Integer|Long Character Float Double Boolean

용도 : 객체만 사용할 수 있는 컬렉션 등에 기본 타입의 값을 사용하기 위해 Wrapper 객체로 만들어 사용

Wrapper 객체 생성
기본 타입의 값으로 Wrapper 객체 생성

문자열로 Wrapper 객체 생성

Float 객체는 double 타입의 값으로 생성 가능

Wrapper 활용
Wrapper 객체로부터 기본 타입 값 알아내기
Integer i = Integer.valueOf(10);         Double f = DoublevalueOf(3.14);
int ii = i.intValue(); /* ii = 10*/      double dd = d.doubleValue(); // dd = 3.14

Character c = CharactervalueOf('c');     Boolean b = BooleanvalueOf(true);
char cc = c.charValue(); /* cc = 'c'*/   boolean bb = b.booleanValue(); // bb = true
문자열을 기본 데이터 타입으로 변환
int i = integerparselnt("123");             // i = 123
boolean b = BooleanparseBoolean("true");    // b = true
double f = DoubleparseDouble("3.14");       // d = 3.14
기본 타입을 문자열로 변환
String s1 = IntegertoString(123);     //정수 123을 문자열 "123"으로 변환
String s2 = IntegertoHexString(123);  //정수 123을 16진수의 문자열 "7b"로 변환
String s3 = DoubletoString(3.14);     //실수 3.14를 문자열 "3.14"로 변환
String s4 = CharactertoString('a');   //문자 'a'를 문자열 "a"로 변환
String s5 = BooleantoString(true);    //불린 값 true를 문자열 "true"로 변환
박싱과 언박싱
박싱(boxing) : 기본 타입의 값을 Wrapper 객체로 변환하는 것

언박싱(unboxing) : Wrapper 객체에 들어 있는 기본 타입의 값을 빼내는 것. 박싱의 반대

자동 박싱과 자동 언박싱 : JDK 1.5부터 박싱과 언박싱은 자동으로 이루어지도록 컴파일됨

String의 생성과 특징
String 클래스는 문자열을 나타냄

스트링 리터럴(문자열 리터럴)은 String 객체로 처리됨

스트링 객체의 생성 사례

String str1 = "abcd";

char data[] = {'a', 'b', 'c', 'd'};
String str2 = new String(data);
String str3 = new String("abcd"); // str2와 str3은 모두 "abcd" 스트링
스트링 리터럴과 new String()
스트링 리터럴

-자바 가상 기계 내부에서 리터럴 테이블에 저장되고 관리됨

-응용프로그램에서 공유됨

-스트링 리터럴 사례) String s = "Hello";

new String()으로 생성된 스트링

-스트링 객체는 힙에 생성

-스트링은 공유되지 않음

스트링 객체의 주요 특징
스트링 객체는 수정 불가능

-리터럴 스트링이든 new String()을 생성했든 객체의 문자열 수정 불가능

스트링 비교 : 두 스트링을 비교할 때 반드시 equals()를 사용하여야 함

->equals()는 내용을 비교하기 때문

String 활용
스트링 비교, equals()와 compareTo()

->스트링 비교에 == 연산자 절대 사용 금지

-equals() : 스트링이 같으면 true, 아니면 false 리턴

String java= "Java";
if(java.equals("Java")) // true
int compareTo(String anotherString)

-문자열이 같으면 0 리턴

-이 문자열이 anotherString 보다 먼저 나오면 음수 리턴

-이 문자열이 anotherString 보다 나중에 나오면 양수 리턴

String java = "Java";
String cpp = "C++";
int res = java.compareTo(cpp);
if(res == 0) System.out.println("the same");
else if (res < 0) System.out.println(java + " < " + cpp);
else System.out.println(java + " > " + cpp);

## 11월 6일

## 패키지 개념과 필요성
* 3명이 분담하여 자바 응용프로그램을 개발하는 경우, 동일한 이름의 클래스가 존재할 가능성 있음

-> 합칠 때 오류 발생 가능성

-> 개발자가 서로 다른 디렉터리로 코드 관리하여 해결

## 자바 패키지와 모듈이란?
* **패키지(package)**

  -서로 관련된 클래스와 인터페이스를 컴파일한 클래스 파일들으 묶어 놓은 디렉터리

  -하나의 응용프로그램은 한 개 이상의 패키지로 작성

  -패키지는 jar 파일로 압축할 수 있음


* **모듈(module)**

  -여러 패키지와 이미지 등의 자원을 모아 놓은 컨테이너

  -하나의 모듈을 하나의 .jmod 파일에 저장


* **java 9부터 모듈화 도입**

  -플랫폼의 모듈화 : java 9부터 자바 API의 모든 클래스들(자바 실행 환경)을 패키지 기반에서 모듈들로 완전히 재구성

  -응용프로그램의 모듈화 : 클래스들은 패키지로 만들고, 다시 패키지를 모듈로 만듦

## 패키지 만들기
* **클래스 파이(.class)이 저장되는 위치는?**

  -클래스나 인터페이스가 컴파일 되면 클래스 파일 생성

  -클래스 파일은 패키지로 선언된 디렉터리에 저장


* **패키지 선언**

  -소스 파일의 맨 앞에 컴파일 후 저장될 패키지 지정 -> package 패키지명;



## 자바 API의 모듈 파일들


* **자바가 설치된 jmods 디렉터리에 모듈 파일 존재**
    * .jmod 확장자를 가진 파일
      모듈은 수십 개 존재하며, ZIP 포맷으로 압축된 파일
      → 포맷이 zip이며, 확장자는 .jmod 입니다.

* **모듈 파일에는 자바 API의 패키지와 클래스들이 들어 있음**

* **jmod 명령을 이용하여 모듈 파일에 들어 있는 패키지를 풀어낼 수 있음**


## 패키지 사용하기, import문

### **다른 패키지에 작성된 클래스 사용**

-import를 이용하지 않는 경우

     -> 소스에 클래스 이름의 완전 경로면 사용
* **필요한 클래스만 import**

  -소스 시작 부분에 클래스의 경로명 import

  -import 패키지.클래스

  -소스에는 클래스 명만 명시하면 됨

* **패키지 전체를 import**

  -소스 시작 부분에 패키지의 경로명. *import

  -import 패키지

  -소스에는 클래스 명만 명시하면 됨

  -import java.util.*;

  ->java.util 패키지 내의 모든 클래스만을 지정, 하위 패키지의 클래스는 포함X

## VS Code에서 Java Package 생성하기
* **Elipse 보다도 간단히 만들 수 있음**


* **교재의 예제에서는 app과 lib package를 만들었지만,
  일반적으로 package는 com.foo.test와 같이 도메인의 역순으로 만드는 것이 일반적**


## JDK의 주요 패키지
* **java.lang**

  -스트링, 수학 함수, 입출력 등 자바 프로그래밍에 필요한 기본적인 클래스와 인터페이스

  -자동으로 import 됨
* **java.util**

  -날짜, 시간, 백터, 헤시맵 등과 같은 다양한 유틸리티 클래스와 인터페이스 제공

* **java.io**

  -키보드, 모니터, 프린터, 디스크 등에 입출력을 할 수 있는 클래스와 인터페이스 제공

* **java.awt**

  -GUI 크로그램을 작성하기 위함 AWT 패키지

* **javax.swing**

  -GUI 프로그래밍을 작성하기 위한 스윙 패키지

## 객체 속성
* **object 크래스는 객체의 속성을 나타내는 메소드 제공**


* **hashCode() 메소드**

  -객체의 해시코드 값을 리턴하며, 객체마다 다름


* **getClass() 메소드**

  -객체의 클래스 정보를 담은 Class 객체 리턴

  -Class 객체의 getName() 메소드는 객체의 클래스 이름 리턴


* toString() 메소드

  -객체를 문자열로 리턴

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
#### 1. 시작하기

Java로 프로그램을 짜면? --> `___.java` 라는 확장자가 생김

---> jdk(Java 컴파일러)로 컴파일해서 --> 기계어 코드가 나옴.(기계어코드를 컴퓨터가 해석)

즉 소스코드가, 컴파일러를 통해 클래스 언어로.

Hello.java --> Hello.class



자바 퍼진 이유?

한 번 작성하면 시스템, 운영체제 상관없이 어디서나 돌아가기 때문.



C?

윈도우에서 짜고, 리눅스에 돌렸을 때 100퍼센트 호환X

but Java는 손 볼 것 없이 바로 어디서나 사용 가능.



JVM(java virtual machine)이 차이가 생길 수 있는 부분을 잡아주기 때문에 시스템에 차이가 있어도 OK

--> 그래서 은행등에서 많이 쓴다고 함..



Hello.class --> 얘를 한 줄 한 줄 읽어들이면서 컴퓨터가 실행하는데 이걸 ==인터프리트==라고 함 

파이썬? --> 컴파일 과정없음. 바로바로 인터프리터과정을 

C ? --> 인터프리터 X 컴파일만하면 바로 OK

자바? --> 컴파일, 인터프리트 모두!



자바 규칙

- 반드시 지켜야할 규칙
- convention - java 프로그래머들끼리 약속한 규칙, 관습



프로젝트를 만들면 src폴더가 생기고, 그 밑에 package를 만든다.

내가 패키지를 안만들고 바로 파일만들면 자동으로 프로젝트 이름이랑 같은 패키지가 디폴트로 생성해줌.



C는 main() 으로시작, struct

struct (어쩌구저쩌구)... --> 얘가 class로 바뀐 것

int main ()

```java
package hello; // 항상 첫줄
// 파일명이 Hello.java면 항상 클래스 Hello가 있어야함 (파일명은 대문자)
public class Hello {
    public static void main(String[] args)
    {
        System.out.println("Hello world");
    }
}
```





#### 2. 변수와 자료형

- 하나의 파일에 하나의 클래스 작성하는 경우 (main 메소드 포함)
- 파일명 : Hello.java (반드시 클래스명이 파일명이어야 함)
  - 클래스명은 반드시 대문자로 시작(소문자 에러는 X) - 자바컨벤션

```java
import hellotest; // 프로젝트명이 패키지명이 될 수 있음

class Hello {       // main 함수 대신 main '메소드'라고 말함
    public static void main(String[] args) { 
        int data;
       // 변수 선언
       // Data type 자료형 8개
       // identifier 식별자 변수명
       // Data type 들어갈 공간을 하나 만들어서 이름을 변수명으로 해라
        float score;
        
        // if, for, while 구문 등
        // 짧은주석
        /* 긴주석 */
        System.out.println("..."); // 표준 출력문 (모니터 출력)
    }
}
```



- 하나의 파일에 클래스를 두 개 이상 작성할 때

  - public이 단 하나만 붙거나, 모두 붙지 않아야함
  - main 메소드가 있다면 정확히 하나의 class에만 있어야 함

- 파일명

  - public 이 붙는 클래스가 있다면, 반드시 public 이 붙은 class가 파일명
  - public이 모두 안 붙는다면, 어느 클래스나 파일명으로 OK

  

```java
class A {
    
}

public class B {
    // 이럴 경우 반드시 파일명은 B.java
}

class C {
    
}
```



#### 변수 (variables)

> 변수 : 단 하나의 값을 저장할 수 있는 공간 (값이 변할 수 있는)

```java
// 변수 선언
int a; // 쓰레기 값을 가지고있는 상태
int b;
int x=0; // 깨끗하게 초기화가 된 상태
int y=0;

int a, b;
int x=0, y=0;

int a,b, x=0, y=0;
```



- 식별자 명명 규칙 (identifier) (변수명, 메서드명, 클래스 명 등)
  - 대소문자 구분되며, 길이에 제한X
  - 예약어는 사용하지않음(int, for 처럼 이미 의미가 있는)
  - 사용 가능 문자들 : `영문자`, `숫자`, `_` , `$`
  - ==숫자로 시작X==
  - `int a15; int a_15$; int $5` 등 모두가능

- 기타 권장 규칙
  - ==클래스의 첫글자==는 항상 대문자
  - ==패키지 이름== 항상 소문자
  - 여러 단어로 이루어진 이름은 단어의 첫글자를 대문자로 ==numberOfPerson== 
  - number_of_person(파이썬 권장) / numberOfPerson(자바 권장) - camalcase
  - 상수의 이름(값을 변경x)은 대문자와 _를 이용 ==PI, MAX_NUMBER==)



- 변수는 필요할 때 언제든지 만들어 사용할 수 있다.
- 변수는 생성한 블록에서만 사용할 수 있다.



- 초기화되지 않은 변수는 사용할 수 없음!!

```java
calss VarExample1 {
    public static void main(String args[]) {
        int num;
        System.out.println(num);
        // 윗 줄은 오류.
        // local variable num may not have been initialized
        // 해당 변수는 초기화되지 않았다! 고로 사용 불가!
    }
}
```



- 선언한 자료형에 맞는 자료를 저장해야함!!

```java
calss VarExample2 {
    public static void main(String args[]) {
        int num;
        num = 17.5;
        System.out.println(num);
        // 윗 줄은 오류.
        // Type mismatch; int를 선언했는데 double 넣을 수 없음
    }
}
```



> 기본 자료형 ( primitive data type) : 자료의 값을 저장

- 문자 char - default ascii 0 / 크기(byte) 2 (유니코드)
  - 기계어는 이진법? 숫자야 이진법으로 저장하면되지만.. 
  - 문자는 각문자에 숫자를 하나붙임! (인코딩)
  - 영어 - ascii code [A는 65 B66 a97 b98...]
  - 전세계 언어 - 유니코드
- 정수 (기본적으로 int)
  - byte - default 0 / 크기(byte) 1
  - short - default 0  / 크기(byte) 2
  - int - default 0 / 크기(byte) 4
  - long - default0 / 크기(byte) 8
- 실수 (기본적으로 double)
  - float - default 0.0 / 크기(byte) 4
  - double - default 0.0 / 크기(byte) 8
- boolean (논리형, true&false) - default false
  - python에서는 True, False인데 Java는 ==true, false== 임을 주의

`변수 하나 == 수식이든, 숫자든 결국 하나의값`

```java
b1 = (5 == 3)  // false가 저장
b2 = (5 > 3) // true 가 저장
```

`char 변수에는 반드시 하나의 문자만 입력`

````java
// 옳은 예
char letter = 'A';
char letter = ' ';
// 틀린 예
char letter = 'A '; // 스페이스 포함 2문자 error
char letter = ''; // 아무것도 안들어가서 error
````

`캐스트`

```java
char data = 'A';
int code = (int)data;
System.out.println(data); // A
System.out.println(code); // 65 -- 아스키코드값
```

`char형 증가`

```java
ch = 97
ch = ch+1 // error --> char + int 라서 문제!
ch++ // 가능
```

- space 의 아스키코드 32, 대문자A 65, 소문자a 97 (소문자-대문자 차이도 32)
- tab - `\t` 
- new line - `\n`
- \ - `\\`
- 따옴표 - `\"`



`정수형`

```java
byte a = 1;
short b = 2;
int c = 3;
long d = 100000000L; // 끝에 반드시 대문자 L 또는 소문자 l 붙이기

int data1 = 20; // 20
int data2 = 020; // 16 / 숫자 0 붙이면 8진수
int data3 = 0x20 // 32 / 0x 혹은 0X 붙이면 16진수
```



- byte 자료형의 오버플로우 (overflow)
  - [부호|1|1|1|1|1|1|1] --> 가장 큰 수(127)
  - 바이트 수의 범위 `-128~127` 그 외의 수는 short, int, long..

```java
byte a = 128;  // type mismatch. 바이트에는 들어갈 수 없는 수

byte b = 127;
b++; // error는 아님   -128
b += 1; // error는 아님    -128 (2의 보수)  --> overflow생겨서 거꾸로..
b = b + 1; // compile error

byte c = -128
c-- // error는 아니지만 127. 
```



- short, int의 자료형의 overflow
  - short `-32768 ~ 32767`
  - int `-2147483648 ~ 2147483647`

```java
short a = 32767;
a += 10;
System.out.println(a); // -32759
```



- long 자료형 주의점

```java
long a = 100;
long b = 2147483647; // int 범위내에서는 OK
long c = 2147483648L; // int 범위를 벗어나는 값은 반드시 L 붙이기
```



- double 실수의 대표값, float를 만들 땐 반드시 F나 f 를 붙여줘야함

```java
float f = 1.2345F; // long 과 다르게 무조건 "필수"

float a = 12.5; // error. double로 인식함.

// float는 소수점 7번째 짜리까지만 출력해줌.
```



큰 변수 = 작은 변수 넣는거 OK 

```java
long x = 12345L;
float y;
y = x; // 가능. 왜? float이 long 보다 크다고 간주되니까.
	  //실제 byte랑 조금 다름
```

- 단, short랑 char는 완전히 다른 타입이라서, short에 char넣거나 char에 short넣는 거 불가능.

![형변환](images\image-20220602214254501.png)



> 참조 자료형 (reference data types) : 자료의 주소를 저장

- 배열, 문자열(String), 객체 ...



```java
calss VarExample3 {
    public static void main(String args[]) {
        short num1 = 12; // int로 간주
        double num2 = 12.75; // double로 간주
        char ch = 'A';
        System.out.println(num1)
        System.out.println(num2)
        System.out.println(ch)
        // 모두 OK
    }
}
```



```java
int a = 10, b = 20;
System.out.println(a);
System.out.print(a);
System.out.println("a:" + a + ", b:" + b); // 자바가 추구하는 스타일!
System.out.printf("a: %d\n", a); // 자바하는 사람들 잘 안씀.
```





####  표준 입력 받기

> 파이썬의 input, C언어의 scanf

```java
import java.util.Scanner;
// 기본적으로 제공되는 패키지
// 자바는 이것을 자바 API라고 부름
// 스캐너 클래스가 소속된 패키지가 java.util

public class StdInputTest
{
    public static void main(String args[])
    {
        Scanner scin = new Scanner(System.in);
        // Scanner --> 클래스. (대문자로 시작하는건 클래스)
        // System.in == 키보드
        System.out.print("Enter i Value: ");
        int i = scin.nextInt();
        // scin.nextInt(); --> 여기서 커서 깜빡
        System.out.print("Enter j Value: ");
        int j = scin.nextInt();
        
        if(i > j) System.out.println(i+" is greater than "+j);
        esle System.out.println(j+" is greater than" +i);
    }
}
```


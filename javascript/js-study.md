# 모던 자바스크립트(ES6) 입문 정리
[모던 자바스크립트 입문](http://www.kyobobook.co.kr/product/detailViewKor.laf?ejkGb=KOR&mallGb=KOR&barcode=9791160504439&orderClick=LAG&Kc=, "link") 으로 공부중입니다.

## 2장 프로그램의 작성법과 실행법
### 2.4 프로그램 작성법
### 2.4.1 문자코드
- 유니코드 문자로 작성

### 2.4.2 대문자와 소문자
- 알파벳과 소문자를 구별함

### 2.4.3 토큰과 공백문자
- 토큰 : 프로그램을 구성하는 최소 단위
- 공백문자 : 토큰과 토큰 사이에 공백문자를 입력하여 구분. 공백문자 여러 개 입력 시 하나만 입력한 것으로 간주함

### 2.4.4 문장
- 문장 끝에는 반드시 세미콜론붙이기 (특별한 경우 제외)
- 복합문
: 문장 여러 개를 중괄호({})로 감싼 코드

### 2.4.5 주석

* * *

## 3장 변수와 값
### 3.1 변수
### 3.1.1 변수
- 변수 : 컴퓨터의 메모리에 일정한 크기의 영역으로 생성

### 3.1.2 변수 선언
ex) var sum; (선언자 변수이름;)
- ES6부터는 let, const 선언자 추가

### 3.1.3 변수 선언 생략
- var문으로 선언하지 않은 변수 값을 읽으려고 시도하면 참조오류 발생

### 3.1.4 변수 끌어올림과 변수 중복 선언
ex) console.log(x);
    var x;
    변수 선언의 끌어올림(hoisting)
- 단, 선언과 동시에 대입하는 코드는 끌어올리지 않음

### 3.1.5 변수의 명명 규칙
- 식별자 : 변수, 함수, 라벨 이름 등 사용자가 정의하는 이름
- 명명 규칙
: 알파벳, 숫자(0~9), 밑줄(_), 달러기호($) 사용 가능함. 첫글자로 숫자 사용 X. 예약어를 식별자로 사용할 수 없음.

### 3.1.6 예약어
- 자바스크립트 문법을 규정짓기 위해 자바스크립트 언어 사양에서 사용하는 특수한 키워드
- ES6의 예약어
| break | case | catch | class | const | continue |
| debugger | default | delete | do | else | export |
| extends | false | finally | for | function | if |
| import | in | intanceof | new | null | return |
| super | switch | this | throw | true | try |
| typeof | var | void | while | with | yield |
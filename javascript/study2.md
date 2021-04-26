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
- ES6의 예약어 (break, case, catch, class, const, continue, debugger...)

### 3.2 데이터 타입
### 3.2.1 데이터 타입과 변수의 동적 타이핑
- 데이터 타입 : 숫자나 문자열처럼 변수에 저장하는 데이터종류(정적타입언어, 동적타입언어)

### 3.2.2 데이터 타입의 분류
- 원시타입 : 숫자, 문자열, 논리값, 특수한 값, 심벌
- 객체타입 : 원시타입에 속하지 않는 값

### 3.2.3 숫자
- 리터럴 : 프로그램에 직접 작성할 수 있는 상수 값 (정수 리터럴, 부동소수점 리터럴) 

### 3.2.4 문자열
- 문자열 리터럴은 작은따옴표(')나 큰따옴표(")를 문자열 앞뒤에 붙여서 표현함
- 자바스크립트를 html요소에 끼워 넣을 때는 자바스크립트 프로그램을 문자열로 작성 > html코드에서는 큰따옴표를 사용하고 자바스크립트 코드에는 작은따옴표를 사용하여 구분
- 줄바꿈 문자, 탭문자는 문자열에 그대로 추가X > 이스케이프 시퀀스로 표현해야 함 

### 3.2.5 논리값
- 논리값 : 참인지 거짓인지 표현하기 위해 사용하는 값 (true, false)

### 3.2.6 특수한 값
- null, undefined(값이 없음을 표현함)

### 3.3 ES6부터 추가된 데이터타입
### 3.3.1 심벌
- 심벌 : 자기 자신을 제외한 그 어떤 값과도 다른 유일무이한 값
- 심벌의 생성
```
var sym1 = Symbol(); // Symbol()을 사용해서 생성함
var sym2 = Symbol() // 호출할 때마다 새로운 값을 만듬
console.log(sym1 == sym2); // false
```

```
var HEART = Symbol("하트");
console.log(HEART.toString()); // Symbol(하트)
```
- 심벌과 문자열 연결하기
Symbol.for()를 활용하면 문자열과 연결된 심벌을 생성할 수 있음.
```
var sym1 = Symbol.for("club");
var sym2 = Symbol.for("club");
console.log(sym1 == sym2); // true
```
```
var sym1 = Symbol.for("club");
var sym2 = Symbol("club");
console.log(Symbol.keyFor(sym1)); // club
console.log(Symbol.keyFor(sym2)); // undefined
```

### 3.3.2 템플릿 리터럴
- 템플릿 : 일부만 변경해서 반복하거나 재사용할 수 있는 틀
- 템플릿 리터럴 사용 시 표현식의 값을 문자열에 추가하거나 여러 줄의 문자열을 표현할 수 있음
- 사용법
역따옴표(`)로 묶은 문자열
```
var t = `Man errs as long
he strives.`; // 일반적인 줄바꿈 문자 사용가능(이스케이프 시퀀스도 사용가능)
```
이스케이프 시퀀스 문자를 그대로 출력하려면 템플릿 리터럴 앞에 String.raw(태그함수)를 붙임
```
var t = String.raw`Man errs as long as\nhe strives.`;
```
- 보간표현식
템플릿 리터럴 안에는 플레이스 홀더를 넣을 수 있음. 플레이스 홀더는 ${...}로 표기함
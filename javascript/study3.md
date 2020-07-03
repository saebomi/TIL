## 4장 객체와 배열, 함수의 기초
### 4.1 객체의 기초 (객체 리터럴)
### 4.1.1 객체
- 객체 : 데이터 여러개를 하나로 모은 복합 데이터
- 프로퍼티 : 객체에 포함된 데이터 하나(이름과 값의 쌍)를 가리킴

### 4.1.2 객체 리터럴로 객체 생성하기
```
var card = {suit: "하트", rank: "A"}; // {...} 부분이 객체 리터럴
```
- 프로퍼티 값에는 모든 데이터 타입의 값과 표현식을 대입할 수 있음
- 변수에 대입된 객체 안의 프로퍼티 값을 읽거나 쓸 때는 마침표(.)연산자 또는 대괄호([]) 연산자를 사용함.
```
card.suit    // 하트
card["rank"] // A
```

### 4.1.3 프로퍼티 추가와 삭제
- 없는 프로퍼티 이름에 값을 대입하면 새로운 프로퍼티 추가
```
card.value = 14;
console.log(card);
```
- delete 연산자 사용시 프로퍼티 삭제
```
delete card.rank;
console.log(card);
```

### 4.1.4 in 연산자로 프로퍼티가 있는지 확인하기
- in(연산자) : 객체에 특정 프로퍼티가 있는지 확인할 수 있음
```
var card = {suit: "하트", rank: "A"};
console.log("suit" in card); // true
console.log("color" in card); // false
```

### 4.1.5 객체 리터럴 예제
### 4.1.6 메서드

### 4.1.7 객체는 참조 타입
- 객체 타입의 값을 변수에 대입하면 그 변수에는 객체의 참조가 저장됨
```
var a = card;
console.log(a.suit); // 하트
a.suit = "스페이드";
console.log(a.suit); // 스페이드
console.log(card.suit); // 스페이드
```

### 4.2 함수의 기초
### 4.2.1 함수
- 함수 : 일련의 처리를 하나로 모아 언제든 호출할 수 있도록 만들어 둔 것
- 인수 : 함수의 입력 값
- 반환값 : 함수의 출력 값

### 4.2.2 함수 선언문으로 함수 정의하기
```
function square(x) { return x * x }; // 인수의 제곱을 계산해서 반환
```
- return문 다음에는 줄 바꿈 문자를 넣지 말 것!

### 4.2.3 함수 이름
- 모든 식별자를 함수 이름으로 사용가능

### 4.2.4 함수호출
```
square(3) // 9 > 소괄호로 인수를 묶어 입력함
```

### 4.2.5 인수
```
function dist(p, q){
    var dx = q.x - p.x;
    var dy = q.y - p.y;
    return Math.sqrt(dx*dx+dy*dy);
}
```

### 4.2.6 함수의 실행흐름
- 호출한 코드에 있는 인수가 함수 정의문의 인자에 대입된다.
- 함수 정의문의 중괄호 안에 작성된 프로그램이 순차적으로 실행된다.
- return문이 실행되면 호출한 코드로 돌아간다. return 문의 값은 함수의 반환값이 된다.
- return문이 실행되지 않은 상태로 마지막 문장이 실행되면, 호출한 코드로 돌아간 후에 undefined가 함수의 반환값이 된다.

### 4.2.7 함수 선언문의 끌어올림
```
console.log(square(5)); // 문제없이 동작함
function square(x) { return x * x; } 
}
```

### 4.2.8 값으로서의 함수
### 4.2.9 참조에 의한 호출관 값에 의한 호출
```
function add1(x) {return x = x+1; }
var a = 3;
var b = add1(a);
console.log("a= "+a+", b= "+b); 
```

### 4.2.10 변수의 유효범위
- 유효범위 : 변수에 접근할 수 있는 범위 (어휘적 범위, 동적범위)
- 전역변수와 지역변수의 유효범위(p.104 예제참조)
- 변수의 충돌 : 전역변수이름과 지역변수이름이 같아지면 두 변수가 충돌함
```
var a = "global";
function f(){
    var a = "local";
    console.log(a);  // local
    return a;
}
f();
console.log(a);      // global
```

### 4.2.11 블록 유효 범위 let과 const
- let, const > ES6부터 추가된 변수 선언자. 모두가 '블록 유효범위'를 갖는 변수를 선언함.
- let : 변수 선언, const : 한번만 할당할 수 있는 상수 선언
- let 선언자
var로 선언한 변수와 차이점 : let으로 선언한 변수의 유효범위는 블록 안
```
let x = "outer x";
{
    let x = "inner x";  
    let y = "inner y";
    console.log(x); // inner x
    console.log(y); // inner y
}
console.log(x); // outer x
console.log(y); // y is not defined
```

- const 연산자
: let문으로 선언한 변수처럼 동작하지만, 반드시 초기화해야 한다는 차이점이 있음
```
const origin = {x:1, y:2};
origin.x = 3;
console.log(origin);
```

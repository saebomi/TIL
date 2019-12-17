# Sass(SCSS) 정리<br>

## CSS Preprocessor
- css 전처리기
- 선택자의 중첩이나 조건문, 반복문, 다양한 단위의 연산 등 표준 CSS보다 훨씬 많은 기능을 사용해서 편리하게 작성
- sass와 scss의 차이점 <br>
 - {}(중괄호)와 ;(세미콜론)의 유무 <br>
 - Sass: <br>
 ```css
.list
  width: 100px
  float: left
  li
    color: red
    background: url("./image.jpg")
    &:last-child
      margin-right: -10px
```
 - Scss: <br>
 ```css
.list {
  width: 100px;
  float: left;
  li {
    color: red;
    background: url("./image.jpg");
    &:last-child {
      margin-right: -10px;
    }
  }
}
```

## 주석(Comment)
- Scss: <br>
 ```css
// 컴파일되지 않는 주석
/* 컴파일되는 주석 */
```
- Sass: <br>
 ```css
/* 컴파일되는
 * 여러 줄
 * 주석 */

// Error
/* 컴파일되는
* 여러 줄
    * 주석 */
```

## 데이터 종류(Data Types)
데이터 | 설명 | 예시
---|:---:|---:
`Numbers` | 숫자 | `1, .82, 20px, 2em…`
`Strings` | 문자 | `bold, relative, "/images/a.png", "dotum"`
`Colors` | 색상 표현 | `red, blue, #FFFF00, rgba(255,0,0,.5)`
`Booleans` | 논리 | `true, false`
`Nulls` | 아무것도 없음 | `null`
`Lists` | 공백이나 ,로 구분된 값의 목록 | `(apple, orange, banana), apple orange`
`Maps` | Lists와 유사하나 값이 Key: Value 형태 | `(apple: a, orange: o, banana: b)`

## 특이사항
- Numbers: 숫자에 단위가 있거나 없습니다.
- Strings: 문자에 따옴표가 있거나 없습니다.
- Nulls: 속성값으로 null이 사용되면 컴파일하지 않습니다.
- Lists: ()를 붙이거나 붙이지 않습니다.
- Maps: ()를 꼭 붙여야 합니다.

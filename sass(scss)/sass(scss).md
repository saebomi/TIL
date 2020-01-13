# Sass(SCSS) 정리<br>

## CSS Preprocessor
- css 전처리기 (less, sass(scss), stylus가 있음)
- 전처리기로 작성 후 css로 컴파일해야 
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
 - 여러줄 주석 사용시 라인별로 * 를 붙여야하고, 라인을 맞춰야 

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
- Numbers: 숫자에 단위가 있거나 없음
- Strings: 문자에 따옴표가 있거나 없음
- Nulls: 속성값으로 null이 사용되면 컴파일하지 않음
- Lists: ()를 붙이거나 붙이지 않음
- Maps: ()를 꼭 붙여야 함

## 중첩
- Scss: <br>
 ```css
.section {
  width: 100%;
  .list {
    padding: 20px;
    li {
      float: left;
    }
  }
}
```

## Ampersand (상위 선택자 참조)
- 중첩 안에서 & 키워드는 상위(부모) 선택자를 참조하여 치환
- Scss : <br>
 ```css
.btn {
  position: absolute;
  &.active {
    color: red;
  }
}

.list {
  li {
    &:last-child {
      margin-right: 0;
    }
  }
  ```

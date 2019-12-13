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

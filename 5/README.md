# 20220708 5강 함수

#### 함수 function
##### 특정 기능을 처리하는 자바스크립트 코드 묶음 
```
function book() {
  var title = "JS 책";
};

// 함수를 변수에 할당에 형태
var point = function(one, two) {
  var total = one + two;
  var bonus = total + 100;
};
```
##### 함수 구성 요소
1. function 키워드
2. 함수 이름
- 첫 문자는 영문자, $, 언더바 사용
- 함수 코드를 읽지 않더라도 이름과 파라미터로 기능을 알 수 있도록 시맨틱을 부여하여 작명
3. 파라미터 Parameter
4. 함수Body
- 중괄호 안에 작성한 코드

# 20220708 6강 오브젝트(Object)

#### 프로퍼티(Property)
##### {name : value} 형태
###### name
- 프로퍼티 이름 / 키를 작성
- 따옴표 작성 생략 가능
``` 
var book = {
  title = "책"
};
```
###### value
- JS에서 지원하는 타입 작성 (123, "ABC", true, {})
- 프로퍼티 확장도 가능
```
var book = {
  title = "책",
  point : {
    ten : 10,
    bonus : 200,
    promotion : function(){}
  }
};
```
##### 추가 & 변경
- var obj = {};
- obj.abc = 123;
- obj 오브젝트에 프로퍼티 이름으로 abc가 없으면 abc : 123 추가, 있으면 프로퍼티 값이 123으로 변경
```
// 점과 프로퍼티 이름 사용
var book = {};
book.title = "JS책";
console.log(book); // {title : JS책}

// 대괄호 사용
var book = {};
book["title"] = "JS책";
console.log(book); // {title : JS책}

// 변수 사용
var book = {title : "JS책"};
var varName = "title";
book[varName] = "HTML책";
console.log(book); // {title : HTML책}
```
##### 추출
```
// 오브젝트에서 프로퍼티 값 추출
var obj = {book : "책"};
console.log(obj.book); // 책
console.log(obj["sports"]); // undefined

// obj 오브젝트에 프로퍼티 이름인 book이 있으면 프로퍼티 값 반환, 없으면 undefined 반환
```

##### 열거
###### 오브젝트에서 프로퍼티를 열거
```
// for(변수 in 오브젝트) 문장;
// 변수 = 프로퍼티 이름이 item

var sports = {
  soccer = "축구",
  baseball = "야구"
};
for(var item in sports) {
  console.log(item);
  console.log(sports[item]);
}
/* soccer
축구
baseball
야구
```

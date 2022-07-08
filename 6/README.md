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
var book = {};
book.title = "JS책";
console.log(book); // {title : JS책}
```
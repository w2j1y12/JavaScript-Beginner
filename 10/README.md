# 20220712 10강 Object 오브젝트(ES3 기준)

![10_프로퍼티리스트](https://user-images.githubusercontent.com/62472117/178714106-5a7e9544-913c-4212-b55a-09bf091f7628.png)

#### new Object() 
- 파라미터 : 값 opt
- 반환 : 생성한 인스턴스
##### 인스턴스를 생성하여 반환
###### 파라미터의 데이터 타입에 따라 생성할 인스턴스 결정
###### 파라미터 값이 undefined, null이면, 빈 Object 인스턴스 반환
```
var newNum = new Number(123);
console.log(typeof newNum); // object
console.log(typeof newNum + 100); // 223

var newObj = new Object(123);
console.log(typeof newObj); // object
console.log(newObj + 100); // 223 
// 파라미터의 데이터 타입에 따라 인스턴스 타입 결정
```
```
var newObj = new Object(0;
console.log(newObj); // {}
```
#### Object()
- 파라미터 : 값 opt, {name : value}
- 반환 : 생성한 인스턴스
##### Object 인스턴스 생성
```
var obj = Object({name : "JS"});
console.log(obj); // {name : JS}

var emptyObj = Object();
console.log(emptyObj); // {}
```

#### Object 생성 방법
##### var abc = {};
###### var abc = Object()와 같음
```
var obj = Object({name : "value"});
console.log(obj); // {name:value}
console.log(obj instanceof Object); // true -> Object로 생성한 인스턴스가 맞음
```
```
var obj = {name : "value"};
console.log(obj); // {name:value}
console.log(obj instanceof Object); // true
```

#### valueOf()
- data : Object 인스턴스, 숫자
- 파라미터 : 사용하지 않음
- 반환 : 프리미티브 값
##### data 위치에 작성한 Object 인스턴스의 프리미티브 값 반환
```
var obj = {key:"value"};
console.log(obj.valueOf()); // {key:value}
```

#### 함수와 메소드 연결 및 호출
##### 함수
- 오브젝트에 연결
- Object.create()
```
console.log(Object.create); // function create() { [native code] } -> Object에 create가 존재하므로 함수 출력
console.log(Object.prototype.create); // undefined -> Object.prototype에 create가 존재하지 않으므로 undefined 출력
```
##### 메소드
- 오브젝트의 prototype에 연결
- Object.prototype.toString() or 인스턴스를 생성하여 호출
```
console.log(Object.prototype.toString); // function toString() { [native code] } // Object.prototype에 toString이 존재하므로 함수 출력

var obj = {}; // 인스턴스를 사용하여 메소드를 호출할 때는 prototype 사용 x -> prototype에 연결된 메소드로 인스턴스를 생성하기 때문
console.log(obj.toString); // function toString() { [native code] }
```
##### 함수와 메소드를 구분해야 하는 이유
- JS 코드 작성 방법이 다름
- 함수는 파라미터에 값을 작성하고, 메소드는 메소드 앞에 값을 작성
```
console.log(String.fromCharCode(49,65)); // 1A
```



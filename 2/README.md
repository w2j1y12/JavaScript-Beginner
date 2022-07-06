# 20220706 2

#### Semantic : 의미를 부여하여 변수 이름을 작명

#### console.log(data) : 소괄호 안에 작성된 값을 브라우저 콘솔창에 출력
##### + data : 파라미터 값

```
var point = 123;
console.log(point); // 123
```

#### JS는 정수와 실수를 구분하지 않음
##### 64비트 부동 소수점 처리
###### 123을 123.0으로 처리

```
console.log(.123); // 0.123
console.log(0.12 + 5); // 5.12
```
#### 상수 : 변경할 수 없는 값
##### JS는 변수의 값을 변경할 수 있으므로 상수 변수는 선언적 의미
###### 영문 대문자를 사용하여 상수로 사용한다는 시맨틱 선언
###### JS가 제공화는 상숫값은 변경 불가 ex) MAX_VALUE, MIN_VALUE
```
var ONE = 123;
ONE = 456;
console.log(ONE); // 456
console.log(Number.MAX_VALUE); // 1.79~~
```
#### typeof 연산자
##### 데이터(값) 타입 반환
```
var point = 123;
console.log(typeof point); // number

var book = "책";
console.log(typeof book); // string
```
#### Number Type
##### 부호(+,-)를 가진 값

```
var point = 123;
console.log(typeof point); // number
point = -1.23;
console.log(typeof point); // number
```
##### Number Type의 특수한 3개 값
###### NaN : Not-a-Number
###### Infinity : 양수 무한대
###### -Infinity : 음수 무한대

```
var point = 1 * "A";
console.log(point); // NaN
```
#### String type
##### 값을 "" 또는 '' 사이에 작성
##### ""와 '' 같이 사용할 때
```
var point = "책, ,'123'";
console.log(point); // 책, '123'
point = '책, "123"';
console.log(point) // 책, "123"
```
##### 따옴표에 숫자를 작성하면 문자 타입
```
var value = "123";
console.log(typeof value); // string
```
#### Undefined Type
##### 변수를 선언만 한 것으로 undefined가 초깃값으로 설정
```
var point;
console.log(point); // undefined
```
##### 변수에 undefined 할당 가능
```
var point = undefined;
console.log(point); // undefined
```
#### Null type
##### undefined는 단지 변수만 선언한 것, null은 할당해야 할 값이 null

```
var book;
console.log(book); // undefined

var point = null;
console.log(point); // null
```
#### Boolean type
##### true, false

#### Object type
##### Property : {name:value} 형태 - JS의 기본 구조
```
var book = {
  title:"책", point:123
};
console.log(book); // {title:책, point:123}
```
##### Object는 프로퍼티 집합

```
console.log(typeof null); // object
console.log(typeof {book:"책"}); // object
// null의 데이터 타입이 null x
```


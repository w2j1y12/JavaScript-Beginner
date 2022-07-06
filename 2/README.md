20220706

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

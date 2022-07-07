# 20220706
# 3강 연산자

#### 연산자
##### 규칙에 따라 계산하여 값을 구함

#### 표현식
##### 표현식 평가 ex) var total = 1+2;
##### 평가 결과 : 표현식을 평가하면 결과 반환 

#### 할당 연산자
##### 단일 할당 연산자
###### = 하나만 사용
##### 복합 할당 연산자
###### = 앞에 연산자 작성

#### 해석
##### JS code를 기계어로 바꾸는 것 = Compile

#### 실행 순서
##### ex) var result = 1+2+6;
1. = 왼쪽의 표현식 평가
2. = 오른쪽의 표현식 평가(왼쪽에서 오른쪽으로 평가 : 1+2 -> 3+6)
3. = 오른쪽 표현식의 평가 결과를 왼쪽 표현식 평가 결과에 할당

#### + 연산자
##### + 양쪽의 표현식을 평가 -> 평가 결과를 더함
```
var value = 1+2+4;
console.log(value); // 7
```
##### 한 쪽이라도 숫자가 아니면 연결
```
var two = "2";
var value = 1 + two;
console.log(value); //12
console.log(typeof value); // String
```
##### Q. 1+5+"ABC"의 결과는?
```
var value : 1 + 5 + "ABC";
console.log(value); // 6ABC
// 왼쪽에서 오른쪽으로 
```

#### 숫자로 변환
##### 연산하기 전에 우선 숫자로 변환
1. undefined -> NaN
```
var value;
console.log(10+value); // NaN
```
2. Null -> +0
3. Boolean -> true:1, false:0
```
console.log(10+null); // 10
console.log(10+true); // 11
console.log(10+false); // 10
```
4. Number -> 변환 전,후 같음
5. String -> 값이 숫자이면 숫자로 연산 (+ 더하기는 연결)
```
console.log(10+"123"); // 10123
console.log(123-"23") // 100
```
#### - 연산자
##### String 타입이지만, 값이 숫자이면 Number 타입으로 변환하여 계산

#### * 연산자
##### 숫자 값으로 변환할 수 있으면 변환
##### NaN 반환 -> 양쪽의 평가 결과가 하나라도 숫자가 아닐 때
```
console.log(10*"20"); // 20
console.log(10*true); // 10
console.log(10*false); // 0
console.log(10*null); // 0
console.log(10*"A"); // NaN
```
##### 소수 값이 생기는 경우 처리
```
console.log(2.3*3); // 6.8999999999995
console.log(2.3*10*3/10); // 6.9
// IEEE 754 유동 소수점 처리 때문
// 실수를 정수로 변환하여 값을 구하고 다시 정수를 실수로 변환
```
#### / 연산자
##### NaN 반환 -> 양쪽의 평가 결과가 하나라도 숫자가 아닐 때 / 분모, 분자가 모두 0일 때
##### 분모, 분자가 0일 때 -> 분모가 0이면 Infinity / 분자가 0이면 0 반환
```
console.log(10/"A"); // NaN
console.log(0/0); // NaN
console.log(10/0); // Infinity
console.log(0/10); // 0
```
#### % 연산자
```
console.log(5%2.5); // 0
console.log(5%2.3); // 0.40000000000036
console.log(5*10-(2*2.3*10))/10); // 0.4
```

#### 단항 연산자
##### 기본 형태는 +(-)value (항이 하나)
##### 값을 Number 타입으로 변환
```
var value = "7";
console.log(typeof value); // string
console.log(typeof +value); // Number
console.log(typeof Number(value)); // Number
// Number() 함수 사용하는 것이 가독성이 좋음
```
#### 후치 연산자
##### 기본 형태는 value++(--)
##### 값을 자동으로 1 증가시킴(또는 감소)
###### 단, 문장을 수행한 후 증가(감소) = 세미콜론 다음에서 증가(감소)
```
var one = 1;
var value = one++ + 3;
console.log(value); // 4
console.log(one); // 2
```
```
var two = 2;
var value = two-- + 3;
console.log(value); // 5
console.log(two); // 1
```

#### 전치 연산자
##### 기본 형태는 ++(--)value
##### 값을 자동으로 1 증가시킴(또는 감소)
###### 단, 문장 안에서 1 증가(감소) = 표현식을 평가하기 전에 1 증가 -> 표현식에서 증가된 값을 사용
```
var one = 1;
var value = ++one + 3;
console.log(value); //5
```
```
var two = 2;
var value = --two + 3;
console.log(value); // 4
```
#### ! 연산자
##### 논리 NOT 연산자
##### 기본 형태는 !value
##### 표현식 평과 결과를 true, false로 변환 -> true => false / false => true
##### 원래 값은 바뀌지 않으며 사용할 때만 변환
```
var value = true;
console.log(!value); // false
console.log(!!value) // true
```





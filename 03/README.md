# 20220706 3강 연산자

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
#### 유니코드 Unicode
##### 세계의 모든 문자를 통합하여 코드화
##### http://www.unicode.org/
##### JS는 u 앞에 역슬래시 작성
```
console.log("\u0031"); // 1
console.log("\u0041"); // A
// 역슬래시 자체를 문자로 표현하려면 두 개 작성
console.log("\\0031"); // \u0031
```
#### UTF(Unicode Transformation Format)
##### 유니코드의 코드 포인트를 매핑하는 방법

#### 관계 연산자
##### >, <, <=, >=
1. 양쪽이 Number 타입일 때
- 왼쪽이 오른쪽보다 크면 true, 아니면 false 반환
```
console.log((1+2) > 1); // true
```
2. String 타입 비교
- 한 쪽이 String 타입이면 false
```
console.log(1>"A"); // false
```
- 양쪽이 모두 String 타입이면 유니코드 사전 순서로 비교
```
console.log(("\u0033" > "\u0032")); // true
console.log("A" > "1"); // true -> u0041 > u0031
console.log("가" > "다"); // false
```
- 문자 하나씩 비교
```
console.log("A07" > "A21"); // false
// A =A => 0 > 2 x => false
```
#### 동등 연산자(==)
##### 왼쪽과 오른쪽의 값이 같으면 true, 다르면 false
##### 값 타입은 비교하지 않음
```
console.log(1 == "1"); // true
// 문자타입을 숫자타입으로 변환하여 비교
```
```
var value;
console.log(value == undefined); // true
console.log(value == null); true
// typeof는 다르지만 값만 연산하기 때문에 true
```
#### 부등 연산자(!=)
##### 왼쪽과 오른쪽 값이 다르면 true, 같으면 false
##### a != b 와 !(a == b) 같음

#### 일치 연산자(===)
##### 왼쪽과 오른쪽의 값과 타입이 모두 같으면 true, 값 또는 타입이 다르면 false
```
console.log(1 === "1); // false
```
``` 
var value; // undefined
console.log(value == null); // true
console.log(value === null); // false
```
#### 불일치 연산자(!==)
##### 값 또는 타입이 다르면 true, true가 아니면 false

#### 콤마 연산자(,)
##### 콤마로 표현식을 분리

#### 그룹핑 연산자(())
##### 소괄호 안의 표현식을 먼저 평가

#### 논리 OR 연산자(||)
##### 표현식의 평가 결과가 하나라도 true이면 true, 아니면 false
```
var value, zero = 0, two = 2;
console.log(value || zero || two); // 2
// undefinde || 0 || 2 -> false || false || true 
// true가 된 시점의 값을 반환
```
```
var value, zero = 0;
console.log(zero || value); // undefined
// 0 || undefined -> false || false
// 모두 false이면 마지막 변숫값 반환
```
##### 왼쪽 결과가 true이면 오른쪽은 비교하지 않음
```
var one = 1;
console.log(one === 1 || two === 2); // true
// two를 선언하지 않았기 때문에 원래 error가 발생
// 오른쪽에서 이미 true가 나왔기 때문에 ㄱㅊ
```
#### 논리 AND 연산자(&&)
##### 표현식의 평가 결과가 모두 true이면 false, 아니면 false
```
var one = 1, two = 2;
console.log(one && two); // 2
// 1 || 2 -> true || true 
// 모두가 true이면 마지막 값을 반환
```
##### 왼쪽 결과가 false이면 오른쪽은 비교하지 않음
```
var one = 1, zero = 0;
console.log(one && zero && nine); // 0
// 1 || 0 || ? -> true || false || ? 
// 이미 zero가 false이므로 오른쪽은 비교 x -> nine error x
```
#### 조건 연산자
##### exp ? exp-1 | exp-2 (3항 연산자라고도 함)
##### exp 표현식을 먼저 평가
###### true이면 exp -1 결과 반환
###### false이면 exp-2 결과 반환
```
console.log(1 === 1 ? "같음" : "다름"); // 같음
console.log(1 === "1" ? "같음 : "다름"); // 다름
```
#### 연산자 우선순위
##### ()가 가장 높음
##### https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Operator_Precedence

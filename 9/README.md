# 20220710 9강 String 오브젝트

#### String 오브젝트
##### "ABC"처럼 문자처리를 위한 오브젝트
###### 즉, String 오브젝트에 문자 처리를 위한 함수와 프로퍼티가 포함되어 있으며, 함수를 호출하여 문자 처리

#### 문자열 연결
###### + or \ 로 연결
```
var concat = 123 + "abc" + "가나다라"; 
console.log(concat); // 123abc가나다라
```
```
var concat = "abc \ 가나다라";
console.log(concat); // abc가나다라
```

![9_String프로퍼티리스트](https://user-images.githubusercontent.com/62472117/178147024-f5b2f057-d7a7-40e8-9cc0-1e5c4da6fb15.png)
![9_String프로퍼티리스트2](https://user-images.githubusercontent.com/62472117/178147126-87a60089-b4b1-49c4-8a9e-cf56e3025551.png)

#### String()
- 파라미터 : 변환 대상 opt
- 반환 : 변환한 값
##### 파라미터 값을 String 타입으로 변환하여 반환
###### 값을 작성하지 않으면 빈 문자열 반환
```
var value = String(123);
console.log(value); // 123
console.log(typeof value); // string
console.log(typeof("" + 123)); // string
```
#### new String()
- 파라미터 : 값 opt
- 반환 : 생성한 String 인스턴스
##### String 인스턴스를 생성하여 반환
##### 파라미터 값을 String 타입으로 변환
###### 파라미터 값 => 프리미티브 값
```
var obj = new String(123);
console.log(typeof obj); // object
```
#### valueOf() 
- data : String 인스턴스, 문자
- 파라미터 : 사용하지 않음
- 반환 : 프리미티브 값
##### String 인스턴스의 프리미티브 값 반환
```
var obj = new String(123);
console.log(obj.valueOf()); // 123
```
#### length 프로퍼티
##### 문자 수 반환
```
var value = "ABC";
console.log(value.length); // 3
```
```
var value = "ABC";
for(var k = 0; k < value.length; k++) {
  console.log(value[k]);
};
/* A
B
C */
```
#### trim()
- data : 삭제 대상
- 파라미터 : 사용하지 않음
- 반환 : 삭제한 결과
##### 문자열 앞뒤의 화이트 스페이스 삭제
```
var value = "  abcd  ";
console.log(value.length); // 8
console.log(value.trim().length); // 4
```

#### toString()
- data : 문자열, String 인스턴스
- 파라미터 : 사용하지 않음
- 반환 : 변환한 값
##### data 위치의 값을 String 타입으로 변환
```
var value = 123;
var result = value.toString();
console.log(typeof result); // string
```
#### JS 함수 호출 구조
##### 데이터 타입으로 오브젝트를 결정하고, 오브젝트의 함수를 호출
```
var value = 123;
value.toString(); // Number 오브젝트의 toString() 호출

"123".toString(); String 오브젝트의 toString() 호출
```
```
var result = toString(123);
// Object 오브젝트의 toString() 호출
// 123을 오브젝트로 간주 -> Object 형태를 
console.log(result); // [object Undefined]
```

#### charAt()
- data : 반환  대상
- 파라미터 : 반환 기준 인덱스
- 반환 : 인덱스 번째 문자
##### 인덱스의 문자를 반환
```
var value = "sports";
console.log(value.charAt(1)); // p
console.log(value[1]); // p
```
```
// 문자열 길이보다 인덱스가 크면 빈 문자열 반환
var value = "sports";
console.log(value.charAt(12)); // ""

// 일반적으로 존재하지 않으면 undefinde 반환
console.log(value[12]); // undefinde
```
#### indexOf()
- data : 검색 대상
- 파라미터 1 : 검색할 문자열
- 파라미터 2 : 검색 시작 위치, 디폴트 0
- 반환 : 인덱스
##### data 위치의 문자열에서 파라미터의 문자와 같은 첫 번째 인덱스를 반환
```
// 왼 -> 오
var value = "123123";
console.log(value.indexOf(2)); // 1
consoel.log(value.indexOf(23)); // 1

// 두 번째 파라미터 작성 -> 작성한 인덱스부터 검색
console.log(value.indexOf(2, 3)); // 4
console.log(value.indexOf(2, -1)); // 1 -> 두 번째 파라미터가 0보다 작으면 1
console.log(value.indexOf(2, 9)); // -1 -> 두 번째 파라미터가 length보다 크면 -1
console.log(value.indexOf(2, "A")); // 1 -> 두 번째 파라미터가 NaN이면 처음부터 검색

// 같은 문자 없으면 -1 반환
console.log(value.indexOf(15)); // -1
```

#### lastIndexOf()
- data : 검색 대상
- 파라미터 1 : 검색할 문자열
- 파라미터 2 : 검색 시작 위치, 디폴트 0
- 반환 : 인덱스
##### data 위치의 문자열에서 파라미터의 문자와 같은 인덱스를 반환
###### 뒤에서 앞으로 검색
```
var value = "123123";
console.log(value.lastIndexOf(2)); // 4

// 두 번째 파라미터 작성 -> 작성한 인덱스부터 검색
console.log(value.lastIndexOf(1, 4)); // 3

// 두 번째 파라미터가 0보다 작으면 -1 반환
console.log(value.lastIndexOf(2, -1); // -1
```
#### Q
##### indexOf()와 lastIndexOf()를 통합하여 발생 가능한 케이스를 기술하고 이에 맞는 코드를 작성하세요.

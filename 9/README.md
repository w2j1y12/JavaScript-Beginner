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
#### 코딩 시간
##### Q. indexOf()와 lastIndexOf()를 통합하여 발생 가능한 케이스를 기술하고 이에 맞는 코드를 작성하세요.

#### concat()
- data : 연결 시작 값, string 인스턴스
- 파라미터 : 연결 대상 opt, 다수 작성 가능
- 반환 : 연결한 결과
##### data 위치의 값에 파라미터 값을 작성 순서로 연결하여 문자열로 반환
##### String 인스턴스를 작성하면 프리미티브 값을 연결
```
var result = "sports".concat("축구", 11);
console.log(result); // sports축구11

var obj = new String(123);
console.log(obj.concat("ABC")); // 123ABC
```
#### toLowerCase() & toUpperCase()
##### 영문 소문자, 대문자 변환
```
console.log("ABCDE".toLowerCase()); // abcde
consoel.log("abcde".toUpperCase()); // ABCDE
```

#### substring()
- data : 반환 대상
- 파라미터 1 : 시작 인덱스
- 파라미터 2 : 끝 인덱스
- 반환 : 결과
##### 파라미터의 시작 인덱스부터 끝 인덱스 '직전'까지 반환
```
var value = "01234567";
console.log(value.substring(2, 5)); // 234

// 두 번쨰 파라미터 x -> 끝까지 반환
console.log(value.substring(5)); // 567
console.log(value.substring()); // 01234567

// 다양한 추출 조건 작성
console.log(value.substring(5,20)); // 567 -> 두 번째 파라미터가 length보다 크면 시작 인덱스부터 끝까지 반환
console.log(value.substring(-7,2)); // 01 -> 두 번쨰 파라미터가 음수이면 0으로 간주
console.log(value.substring(5,1)); // 1234 -> 첫 번째 파라미터 값이 두 번쨰 파라미터 값보다 크면 파라미터 값을 바꿔서 처리
console.log(value.substring(5,"A")); // 01234 -> NaN은 0으로 간주
```
#### substr()
- data : 반환 대상
- 파라미터 1 : 시작 인덱스
- 파라미터 2 : 반환할 문자 수
- 반환 : 결과
##### 파라미터의 시작 인덱스부터 지정한 문자 수를 반환
```
var value = "01234567";
console.log(value.substr(0,3)); // 012

// 첫 번째 파라미터 < 0 -> length에서 파라미터 값을 더해 시작 인덱스로 사용
console.log(value.substr(-3,3)); // 567

// 두 번째 파라미터 x -> 양수 무한대로 간주
console.log(value.substr(4)); // 4567
console.log(value.substr()); // 01234567
```
#### slice()
- data : 반환 대상
- 파라미터 1 : 시작 인덱스
- 파라미터 2 : 끝 인덱스
- 반환 : 결과
##### 파라미터의 시작 인덱스부터 끝 인덱스 직전까지 반환
```
var value = "01234567";
console.log(value.slice(1,4)); // 123

// falsse/undefinde/null/빈 문자열 = 0
console.log(value.slice(false,4)); // 0123 

// 첫 번쨰 파라미터 x or NaN = 0
console.log(value.slice("A")); // 01234567
console.log(value.slice()); // 01234567

// 두 번째 파라미터 x -> length사용
console.log(value.slice(5)); // 567
console.log(value.slice(5,3)); // "" -> 첫 번째 >= 두 번째 -> 빈 문자열

// 두 번째 파라미터 < 0 -> length에 더해 사용
console.log(value.slice(4,-2)); // 45
console.log(value.slice(-5,-2)); // 345
console.log(value.slice(-2,-5)); // ""
```
#### match()
- data : 매치 대상
- 파라미터 : 정규표현식, 문자열
- 반환 : [매치 결과]
##### 매치 대상에 정규 표현식의 패턴을 적용하여 매치하고 매치 결과를 반환
```
var value = "Sports";
console.log(value.match(/s/)); [s]
console.log(value.match("spo")); // null
```
#### replace()
- data : 치환 대상
- 파라미터 1 : 정규 표현식, 문자열
- 파라미터 2 : 대체할 값, 함수
- 반환 : 치환 결과
##### 매치 결과를 파라미터에 작성한 값으로 대체하여 반환
###### 두 번째 파라미터에 함수 작성 -> 함수 실행 -> 함수에서 반환한 값으로 대체
```
var value = "abcabc";
console.log(value.replace("a","바꿈"); // 바꿈bcabc
console.log(value.replace(/a/,"바꿈"); // 바꿈bcabc

function change() {
  return "함수";
};
console.log(value.replace(/a/, change())); // 함수bcabc
```
#### search()
- data : 검색 대싱
- 파라미터 : 정규 표현식, 문자열
- 반환 : 매치된 인덱스
##### 검색된 첫 번째 인덱스 반환
```
var value = "cbacba";
console.log(value.search(/a/)); // 2
console.log(value.search("k")); // -1 -> 매치되지 않음
```
#### split()
- data : 분리 대상
- 파라미터 1 : 분리자(정규 표현식, 문자열)
- 파라미터 2 : 반환 수
- 반환 : 결과
##### 분리 대상을 분리자로 분리하여 배열로 반환
```
console.log("12_34_56".split("_")); // [12,34,56]

// 분리자 작성 x -> 문자를 하나씩 반환
var value = "123";
console.log(value.split("")); // [1,2,3] 빈 문자열
console.log(value.split()); // [123] 작성 x

// 두 번쨰 파라미터에 반환 수를 작성
var value2 = "12_34_56_78";
console.log(value.split("_",3)); // [12,34,56] 
console.log(value.split("A")); // [123] -> 분리자가 분리 대상에 없으면 분리 대상 전체를 하나의 배열로 반환
```

#### charCodeAt()
- data : 반환 대상
- 파라미터 : 반환 기준 인덱스
- 반환 : 인덱스 번째 문자
##### 인덱스 번째의 문자를 유니코드의 코드 포인트 값을 반환
```
var value = "1Aa가";
for(var k=0;k<value.length;k++) {
  console.log(value.charCodeAt(k));
};

// 인덱스가 문자열 길이보다 크면 NaN 반환
console.log(value.charCodeAt(12)); 

/* 49
65
97
44032
NaN */
```

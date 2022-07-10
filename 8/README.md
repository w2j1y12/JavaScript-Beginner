# 20220709 8강 Number 오브젝트                                         

#### Number 오브젝트
##### 숫자처리를 위한 오브젝트
###### 즉, Number 오브젝트에 숫자 처리를 위한 함수와 프로퍼티가 포함되어 있으며, 함수를 호출하여 숫자 처리
![8_프로퍼티리스트](https://user-images.githubusercontent.com/62472117/178107590-2d00e175-e56d-454f-a955-b03df13d8d48.png)

#### Number()
##### Number(파라미터)
- 파라미터 : 반환할 값 opt
- 반환 : 반환할 값
##### 파라미터 값을 Number 타입으로 변환
##### 파라미터 값이 String 타입이라도 값이 숫자이면 변환 가능
```
console.log(Number("123") + 500); // 623
console.log(Number("ABC"); // NaN
```
##### 숫자로 변환할 수 있으면 변환
```
console.log(Number(0x14)); // 20
console.log(Number(true)); // 1
console.log(Number(null)); // 0
console.log(Number(undefined)); // NaN
```
##### 파라미터 값을 작성하지 않으면 0을 반환
![8_Number상수](https://user-images.githubusercontent.com/62472117/178108250-c1ed0de2-27ad-46d4-948c-cdb59b7d3529.png)
###### 상수는 값을 변경, 삭제할 수 없음
###### 영문 대문자 사용이 관례

#### new 연산자
- constructor : 생성자
- 파라미터 : 값 opt
- 반환 : 생성한 인스턴스
##### 오브젝트로 인스턴스를 생성하여 반환
###### 원본을 복사하는 개념
###### new 인스턴스를 사용하면 인스턴스
``` 
var obj = new Number(); // 인스턴스 생성 및 반환
console.log(typeof obj); // object
```
##### 인스턴스마다 값을 갖기 위해 인스턴스 생성
```
var oneObj = new Number("123");
console.log(oneObj.valueOf()); // 123

var twoObj = new Number("456");
console.log(twoObj.valueOf()); // 456
```
#### Number 인스턴스 생성
- 파라미터 : 값 opt
- 반환 : 생성한 Number 인스턴스

#### 프리미티브 값(Primitive Value)
##### 언어에 있어 가장 낮은 단계의 값
###### ex) var book = "책"; -> "책"은 더이상 분해, 전개 불가

##### 프리미티브 타입
- Number, String, Boolean : 인스턴스 생성 가능
- Null, Undefined : 인스턴스 생성 불가
- Object는 프리미티브 값을 제공하지 않음

#### 인스턴스의 프리미티브 값
##### var obj = new Number(123);
###### 인스턴스를 생성하면 파라미터 값을 인스턴스의 프리미티브 값으로 설정
##### 프리미티브 값을 갖는 오브젝트 
###### Boolean, Data, Number, String
```
var obj = new Number(123);
console.log(obj + 200); // 323
```
#### valueOf()
- data : Number 인스턴스, 숫자
- 파라미터 : 사용하지 않음
- 반환 : 프리미티브 값
##### Number 인스턴스의 프리미티브 값 반환
```
var obj = enw Number("123");
console.log(obj.valueOf()); // 123
```
#### toString()
- data : 변환 대상
- 파라미터 : 진수 opt, 디폴트는 10진수
- 반환 : 변환한 값
##### data를 String 타입으로 변환
```
var value = 20;
console.log(20 === value.toStirng()); // fasle
console.log(value.toString(16)); // 14
```
##### 변환 시 주의사항
```
console.log(20..toString()); // 20
// 유동 소수점
```
#### toLocaleString()
- data : 변환대상
- 파라미터 : 사용하지 않음
- 반환 : 변환한 값
##### 숫자를 브라우저가 지원하는 지역화 문자로 변환
###### 지역화를 원하지 않으면 toString()으로 변환
```
var value = 1234.56;
console.log(value.toLocaleString());
console.log(value.toLocaleString('de-DE'));
console.log(value.toLocaleString('zh-Hans-CN-u-nu-hanidec));

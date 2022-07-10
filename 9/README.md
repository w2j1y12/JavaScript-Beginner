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

# 20220707 4강 문장(Statement)

#### 세미콜론(;)
##### 문장을 끝나게 하는 역할 

#### 화이트 스페이스(White Space)
##### 사람 눈에 보이지 않는 문자
###### 가독성을 위한 것이며, 문자마다 기능을 가지고 있음
###### ex) 스페이스 / 탭 

#### 블록({})
##### 실행 그룹으로 블록 안의 모든 문장 실행
```
var one = 1, two = 1;
if(one === two) {
  var result = one + two;
  console.log(result); // 2
};
```

#### if
##### 기본 형태는 fi(표현식) 문장 1
###### + if(표현식) 문장 1 else 문장 2
##### 조건에 따른 처리
###### 표현식 평가 -> 평가 결과를 true / false로 변환
###### true이면 문장 1, false이면 문장 2 실행
```
var a = 1, b = 1;
if(a === b) console.log("블록을 사용하지 않음"); // 블록을 사용하지 않음

if(a === b)
  console.log("1번 줄") // 1번 줄
  cosnole.log("2번 줄"); // 2번 줄
 ```
 ```
 var a = 1, b = 1;
 if(a=== b) {
  console.log("블록 사용"); // 블록 사용
};
```
```
var a = 1, b = 2 ;
if(a === b)
  console.log("블록 사용하지 않음, true");
else 
  console.log("블록 사용하지 않음, else");
// 블록 사용하지 않음, else
```
```
var a = 1, b = 2;
if(a === b) {
  console.log("블록 사용, true");
} else {
  console.log("블록 사용, else"):
} 
// 블록 사용, else
```

#### debugger
##### debugger 위치에서 실행 멈춤
```
debugger;
var sports = "스포츠";
console.log(sports);
// debugger 위치에서 멈춰서 아무것도 x
```

#### while
##### 기본 형태는 while(표현식) 문장
##### 표현식의 평가 결과가 false가 될 떄까지 문장을 반복하여 실행
###### 즉, 반복이 종료되는 조건이 필요함
```
var k = 1;
while(k<3) {
  console.log(k);
  k ++;
};
/* 1
2 */
```

#### do ~ while
##### 기본 형태는 do 문장 while(표현식)
##### 처리 방법은 while과 같으며, do 문을 먼저 실행함
```
var k = 0;
do {
  console.log("do : ", k);
  k ++;
} while (k < 3) {
  console.log("while : ", k);
};
/* do : 0
do : 1
do : 2 
while : 3 */
```
#### for()
##### for(초깃갑 opt; 비교 opt; 증감 opt) 문장

#### 코딩 시간
##### Q. for()문을 사용하여 1에서 50까지 반복하면서 홀수 번째 값과 짝수 번째 값을 누적하고 반복한 값을 누적합니다. 반복을 완료하면 누적한 홀수 번째 값과 누적한 짝수 번째 값을 출력합니다. 누적한 전체 값을 출력합니다
```
var even, odd;
var sumeven = 0, sumodd = 0;
for(var k = 1; k < 51; k ++){
    if((k%2)==0) {
        even =  k;
        sumeven += even;
    } else {
        odd = k;
        sumodd += odd;
    }
};
console.log("짝수 : ", sumeven); // 짝수 : 650
console.log("홀수 : ", sumodd); // 홀수 : 625
```
#### break
##### 반복을 종료시킴
```
var k = 0, m = 0;
while(k < 3) {
  m ++;
  if(m === 2) }{
    break;
  };
  console.log(m);
};
//1
```
```
for(var k = 0; k < 3; k ++) {
  if(k ===1) {
    break
    console.log("k === 1");
  };
  console.log(k);
};
// 0
```
#### continue
##### 반복문의 처음으로 분기
```
for(var k = 0; k < 5; k ++) {
  if(k === 2 || k === 3) {
    continue; // k ++로 감
  };
  console.log(k);
};
/* 0
1
4 */
```
#### switch
##### switch(표현식) {case 표현식 : 문장 리스트 opt default : 문징 리스트 opt};
``` 
var exp = 1;
switch(exp) {
  case 1 :
    console.log(100);
  case 2 :
    console.log(200);
};
/* 100
200 */
// case 1 아래의 문장들도 수행하므로 break 작성 해줘야 함
```
##### 일치하는 case가 없으면 default 수행
``` 
var exp = 7;
switch(exp) {
  case 1 : 
    value = 100;
  default :
    value = 700;
  case 2 :
    value = 200;
};
console.log(value);
// 200
// 위와 마찬가지로 default 이후의 문장도 수행하므로 value = 200
```


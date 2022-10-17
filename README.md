# core-javascript
# 본격적인 시작 전
데이터 타입은 모든 자바스크립트 서적에 처음으로 등장하는 중요한 부분을 차지 합니다. 처음 언어를 접했을 때 무작정 외우고 지나갔던 개념이였습니다. 중요하다는 생각보단 유려하고 키보드 누르는 소리가 계속 들릴만한 긴 코드를 짜고 싶다는 생각에 마음만 앞선 채 개 눈 감추듯 지나갔던 파트 였습니다. 

하지만 신입으로서 면접을 보면 볼 수록 기초는 더욱 중요해졌고, 데이터 타입은 제 발목을 잡았습니다. 흔들리는 기초 위에 사상누각에 불과했던 스킬들은 무너지고 부셔진 뒤 이제서야 중요성을 느끼며 공부를 시작하니 새롭게 느껴집니다.

# 데이터 타입
데이터 타입은 왜 필요하고 첫 번째로 나올 만큼 중요한 개념일까요?
잠시 요리에 비유하자면 볶음밥을 만들기 위해선 우선 쌀을 씻어야 하고 양파를 다듬고 물에 불리는 재료 손질 작업이 필요합니다. 마찬가지로 개발자는 일상에서 발생한 문제들을 프로그래밍을 통해 해결하는 직업으로 문제들을 원자재인 데이터를 활용하여 원하는 요리로 만들 수 있게 가공하는 과정이 필요합니다. 그렇기 때문에 재료들은 어떤것들이 있고 어떤 특징을 가지고 있는지 찬찬히 돌아보여 음미하는 시간이 필요합니다.

>목표 : 자바스크립트가 데이터를 처리하는 과정을 살펴보고 기본형 타입과 참조형 타입이 서로 다르게 동작하는 이유를 이해하고 이를 적절히 활용할 수 있게 되는 것을 목표로 합니다.

## 데이터 타입의 종류
크게 두 가지가 있습니다. 기본형(원시형) 타입과 참조형 타입 입니다.
기본형에는 숫자, 문자, 불리언, null, undefined, 심볼이 있습니다.
참조형은 객체가 있고, 배열, 함수, 날짜, 정규표현식 등과 Map,Set 등이 객체의 하위 분류에 존재합니다.

그렇다면 어떤 기준으로 기본형과 참조형을 구분하는 걸까요?
일반적으로 기본형은 할당이나 연산시 복제되고 참조형은 참조된다고 알려져 있습니다.
기본형은 불변성을 띕니다. 이것을 더 잘 이해하기 위해선 메모리와 데이터에 대한 지식이 필요하고, 나아가 식별자와 변수의 개념을 구분할 수 있어야 합니다. 

## 데이터 타입에 관한 배경지식
### 메모리와 데이터
컴퓨터는 모든 데이터를 0 또는 1로 변환하여 기억합니다. 하나의 메모리 조각을 비트라고 합니다. 8비트는 1바이트가 됩니다. 

자바, C 등의 정적 타입 언어는 메모리의 낭비를 최소화하기 위해 데이터 타입별로 할당 메모리 영역을 2바이트, 4바이트 등으로 나누어 정해놓았습니다. 사용자 입장에서는 데이터 타입마다 일일이 메모리를 할당하는 것은 번거로운 작업이지만 메모리 용량이 매우 부족했던 시절에는 불가피한 선택이었습니다.

한편 자바스크립트 등장 당시 과거보다 월등히 메모리가 커진 상황에서 메모리 압박에 자유로워졌습니다. 넉넉하게 메모리를 할당할 수 있었습니다. 숫자의 경우 정수형인지 부동소수형인지를 구분하지 않고 64비트, 즉 8바이트를 확보합니다. 덕분에 개발자가 형변환을 걱정해야 하는 상황이 훨씬 덜 발생하게 됐습니다.

각 비트는 고유한 식별자를 지닙니다. 바이트 역시 시작하는 비트의 식별자로 위치를 파악할 수 있을 것입니다. 모든 데이터는 바이트 단위의 식별자, 더 정확하게는 메모리 주솟값을 통해 서로 구분하고 연결할 수 있습니다.

### 식별자와 변수
변수는 변할 수 있는 수 입니다. 컴퓨터 용어로 쓸 때는 변할 수 있는 무언가라는 명사로 확장시켰습니다.

여기서 가리키는 무언가 란 데이터를 말합니다. 식별자는 어떤 데이터를 식별하는 데 사용하는 이름, 즉 변수명 입니다.

## 변수 선언과 데티어 할당
### 변수 선언 
변할 수 있는 데이터를 만든다. 결국 변경 가능한 데이터가 담길 수 있는 공간 또는 그릇이 됩니다.
```
var a;
```

### 데이터 할당
```
var a;
a = 'abc';

var a = 'abc';
```

![image](https://user-images.githubusercontent.com/85912592/191025763-5e43dd2e-dbf9-4578-9ea0-8745090f6453.png)

# 10.02

### 실행컨텍스트

1. Rexical Environment랑 Variable Envi 가 있는데 Variable Envrionment의 역할
2. 스코프의 개념
3. 스코프 체인을 Rexical Environment와 엮어서 설명
4. Rexical Environment에서 어떤 정보를 가지고 실행컨텍스트의 스코프를 참조하나요
5. outer environment에 대해 알고 계신가요
6. 호이스팅이란?
7. var와 let,  const가 다르게 작동하는데 어떻게 작동하나요
8. var의 스코프는 블록레벨 스코프가 아닙니다. 이걸 es6이전 문법에서 블록레벨 스코프를 가지게 할 수 있는 방법을 낸 게 있다. 무엇인지 아시나요?(즉시실행 함수)
9. 실행컨텍스트 하면 이벤트 루프가 항상 나오는데 이벤트 루프에 대해 콜스택이라는 키워드를 엮어 설명해주세요
10. 마이크로 태스크와 매크로 태스크를 프로미스 등 엮어서 설명\

### this

1. 화살표함수에서 this는 어떻게 작동할까요.
2. 명시적이로 this를 바인딩하는 방법은 어떤게?
3. 클로저로 this를 어떻게 명시적으로 바인딩하나요?
4. 클로저는 뭘까요
5. 클로저는 어떤 경우에 사용하나요(변수 은닉 외에 다른 사용경우도 알아보시면 좋을 것 같네용)
6. 1급객체는 뭔가요?

### 콜백함수

1. 콜백헬을 es6 이전에는 어떻게 해결했나요?
2. 프라미스는 어떤 식으로 구현이 되어있을 지 상상해보시겠어요?


### 데이터타입
### 데이터타입 중 기본형과 참조형의 차이
### 기본형타입의 예시 세가지
### 변수를 선언한다는 것은 어떤 의미일까요?
### 호이스팅은 뭘 의미할까요
### 호이스팅의 장점
### 가비지컬렉터의 개념
### 기대하고 하는 질문은 아닙니다. 가비지컬렉터의 최적화 기법
### 불변성을 지키기 위한 기법 중 깊은복사를 써보세요

### 실행컨텍스트
### 실행컨텍스트에 들어있는 variable environment에 대해 설명해주세요
### 스코프체인의 개념
### 스코프체인을 outer environment라는 키워드를 섞어서 설명
### 실행컨텍스트에서 콜스택이라는 개념이 나옵니다. 콜스택이 뭐고 어떤 역할을 하는지요?
### 콜스택과 힙 간의 관계
### 비동기함수를 처리하는 순서가 마이크로 태스크랑 매크로태스크가 다른데 키워드를 말씀해주시면서 설명
### 함수 선언문과 표현식은 어떻게 다를까요
### 이벤트 루프의 개념
### 자바스크립트의 map이 어떻게 구현되어 있나요

### This
### 자바스크립트 메서드에서 this는 어떤 것을 가리키나요
### 생성자함수에서 인스턴스는 어떤 걸 가리키나요

### 콜백함수
### 콜백함수에 콜백헬에서 프라미스 내부가 어떻게 되어있을 지 상상해보시겠어요?(while)
### async await은 내부가 어떻게 되어있을까요?(제너레이터)
### 제너레이터에 대해서 알고 계신가요?

10/8
데이터 타입에서 참조형과 기본형 타입의 차이에 대해서 설명해주시겠어요?
기본형은 값을 복사하고, 참조형은 주소값을 복사한다는 말을 해석해주시겠어요?
참조형 데이터는 GC에서 값을 수거할 때 어떨때 사용하는지?
클로저는 수거하나요?
콜백함수는 뭘까요?
콜백함수의 조건이 일급 객체여야 하는데 일급 객체의 조건이 무엇일까요?
실행 컨택스트가 무엇일까요?
어떤 정보들이 담겨있는지 말씀해주시겠어요?
this는 생성자 함수에서 어떻게 작동하나요?
콜백함수에서의 this는요?
스코프 체인은 어떻게 작동할까요?
생존과 제거는 어느 시점에서 이루어질까요?
실행컨텍스트는 언제 생성되나요?
함수가 호출될 때 실행컨텍스트가 어떻게 작동할까요?
스코프 체인을 탈 때 어떻게 작동할까요?
화살표 함수에서 this는 왜 자신을 가리키지 않을까요?
this 바인딩을 명시적으로 하는 방법은 무엇이 있을까요?

## 221017

### 프로미스 체이닝이란?
### 프로미스 내부 로직은 어떻게 구현되었을까요?
### 제너레이터는 어떤 배경에서 나왔을까요?
### 제너레이터 내부 구현은?
### 호이스팅은 뭘 의미할까요?
### var, let, const 어떻게 다르게 동작할까요?
### 클래스 문법이 나오게된 배경이 어떻게 될까요?
### 클래스에 컨스트럭터는 어떤 일들을 할까요?
### 클래스라는게 객체 지향을 기반하여 만들어진 개념인데요, 객체 지향이 추구하는 것들은 뭐가 있을까요?
### 그것들에 대해 구체적으로 설명해주시겠어요?
### 커링 함수의 예를 들어주실 수 있을까요?
### 고차 함수라는 개념이 있는데 이게 나오기 까지 1급 객체여야합니다. 1급 객체의 조건이 뭘까요?
### 클로저란 무엇이고 어떻게 활용하면 좋을까요?

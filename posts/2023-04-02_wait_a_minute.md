# setInterval, setTimeout

충성! 상병 김지홍입니다. 오랜만입니다. 어떻게 살았냐 궁금하신 분들도 있겠지만 각설하고 일단
오늘은 자바스크립트에서의 타임 스케쥴링에 대해 알아봅시다. 군인이기에 휴먼군인체로 말씀드리겠습니다.

> 타임 스케쥴링(Time Scheduling) : 한 마디로 몇 분 **뒤에 or** 몇 분 **마다** 이거해라는 거

죄송하지만, 자바스크립트 명세(EMCAScript)에는 따로 없는 내용입니다.

(생각 해보면 몇분뒤에 코드를 실행하고 그런 거는 따지고 보면 브라우저의 기능이긴 합니다)

→ Window Object 안에 있음

 

## `setInterval()` : 몇 밀리초 마다 이거해주실 수 있으십니까?

![meaning of Interval](https://file.notion.so/f/s/c858a0db-68e0-4fcd-b8c2-83020296fffd/en.dict.naver.com_.png?id=97cef700-8099-4bd4-9556-1702ffef6722&table=block&spaceId=f0d2a5b2-c6a6-45b0-aa4b-84df3b9bbc9c&expirationTimestamp=1680530623494&signature=_bHKvuKP__yUyMjDRXjSj-2ERP26YY_3mlfl7ucUKZI&downloadName=en.dict.naver.com_.png)

*출처 : 네이버 영어사전*

`setInterval()` 함수는 몇 밀리 초 간격마다 함수를 호출하도록 설정하는 함수입니다. 

```jsx
setInterval(간격마다 호출할 콜백함수, 간격);
```

참고로 *콜백함수*란 **함수에 인자로 전달해서 나중에 호출할(Callback) 함수** 라는 뜻이 있습니다.

일단 예시로  5초에 한번씩 현재 시간을 콘솔창에 찍어보는 코드를 짜봅시다. 

```jsx
// 5초(5000 밀리초)에 한번 씩 logDate 함수(콜백함수)를 호출해서 시간을 표시하는 코드
setInterval(function logDate() {console.log(new Date())}, 5000)
```

좀 더 ES6스럽게 화살표함수를 사용해서도 구현할 수도 있습니다.

```jsx
// 5초(5000 밀리초)에 한번 씩 logDate 함수(콜백함수)를 호출해서 시간을 표시하는 코드
// But 화살표함수
setInterval(() => console.log(new Date()), 5000)
```

이렇게 코드를 짜서 `F12` 키를 누른 다음에 콘솔에 입력해주면 아래와 같이 5초에 한번씩 날짜를 출력해줄 것이다! 

- 여기에 GIF 들어갈 예정!

## setTimeout : 몇 밀리초 뒤에 이거해주실 수 있으십니까?

## 중첩! setTimeout를 재귀적으로 실행해서 setInterval 처럼

흠… 잠시만 그러면 setTimeout 함수의 실행이 **끝나기 전에** setTimeout 함수를 **또 실행하면** 

setInterval 함수처럼 사용할 수 있는 거 아닌가?라는 생각을 할 수 있다.

아마 알고리즘에 대해 조금이라도 공부해봤다면 재귀함수에 대해 들어봤을 것이다.

setTimeout 함수를 재귀적으로 중첩하면 몇 밀리초 뒤에 이거해가 계속 이어지므로 실제로는 setInterval 처럼 몇 밀리초 마다 이거해의 기능을 수행하게 된다.

- 여기에 피그마로 그림 설명 넣자 재귀함수 실행과 setTimeout 중첩

## 정확성 문제

[https://blog.bitsrc.io/how-to-get-an-accurate-setinterval-in-javascript-ca7623d1d26a](https://blog.bitsrc.io/how-to-get-an-accurate-setinterval-in-javascript-ca7623d1d26a)

## 더 알아볼거

- 콜백함수

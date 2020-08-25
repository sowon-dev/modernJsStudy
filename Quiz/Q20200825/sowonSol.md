[setTimeout과 setInterval을 이용한 호출 스케줄링](https://ko.javascript.info/settimeout-setinterval) 를 바탕으로 만들어본 퀴즈입니다.

## 문제
setInterval() 함수를 이용하여 콘솔창에 10초를 카운트한 뒤 10초가 끝나면 카운트가 종료되는 함수를 만들어보세요.


## 힌트 
setInterval() 종료는 clearInterval() 사용하면 됩니다.

```js
let num = 0 ;
 
function cntTen(){
   num++;
   console.log(num); // 숫자확인
   if(num == 10){
     console.log('10초 종료');
     clearInterval(stopInterval);
    }
  }
 
/*1초마다 cntTen 함수 실행*/
let stopInterval = setInterval(cntTen, 1000);
```
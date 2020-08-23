### 문제 1. 다음 코드의 실행 결과로 알맞은 것은?<br>
-> 단, split은 인자값을 기준으로 문자열을 나누는 역할을 수행함<br>
<pre>var ch = "자바스크립트 다 까먹었다 망했네...";
var arr = ch.split(" "); // split : 인자값을 기준으로 문자열을 나누는 함수

for(let i = 0; i < arr.length; i+=2)
{
    console.log(i + " : " + arr[i]);
}</pre>


### 문제 2. 다음 코드의 실행 결과로 알맞은 것은?<br>
<pre>var say = 'Hello';

function print() 
{
  console.log(say);
  
  var say = ' World';
  console.log(say);

  function inner_print() 
  {
    console.log(say);
    
    var say = 'Good';
    console.log(say);
    say = ' Bye';
    
    console.log(say);
  }

  inner_print();
}

print();</pre>
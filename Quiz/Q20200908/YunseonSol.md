## 아래의 예상 출력이 나오도록 handler1 을 채우시오.
힌트1: eyeCount의 value를 홀수로 설정하는 경우 메시지만 출력하고, 짝수로 설정하는 경우 이 값을 객체 속성의 값으로 설정한 후 예상 출력을 출력한다.
<br>
힌트2: [Proxy와 Reflect 참고](https://ko.javascript.info/proxy#ref-881)

```js
function Monster() {
    this.eyeCount = 4;
  }
  
  const handler1 = {
    set(obj, prop, value) {
      if ((prop === 'eyeCount') && ((value % 2) !== 0)) {
        console.log('Monsters must have an even number of eyes');
      } else {
        console.log(Reflect.set(obj,prop,value));
      }
    }
  };
  
  const monster1 = new Monster();
  const proxy1 = new Proxy(monster1, handler1);
  
  proxy1.eyeCount = 1;
  // expected output: "Monsters must have an even number of eyes"
  
  console.log(proxy1.eyeCount);
  // expected output: 4

  proxy1.eyeCount = 2;
  // expected output: true

  console.log(proxy1.eyeCount);
```
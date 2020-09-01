
https://ko.javascript.info/class#ref-1566 를 바탕으로 만든 퀴즈입니다.

아래는 클래스 문법으로 작성한 코드입니다.
출력값을 참고하여 빈칸에 알맞은 코드를 작성해보세요. 
출력값
```console
이은재님 출입시간은 2020-8-30 19시 28분(시스템시간)입니다
박나래님 출입시간은 2020-8-30 19시 28분(시스템시간)입니다
```



```js
class Person{
    // 1. 생성자 함수를 만들기

    constructor(name) {
        this.name = name;
    }

    // 2. 메서드를 생성
    display() {
        let today = new Date();
        console.log(this.name+"님 출입시간은 "+
            today.toLocaleDateString()+" "+today.getHours()+"시 "+today.getMinutes() +"분입니다");
    }
};

//인스턴스생성
let lee = new Person("이은재");
let park = new Person("박나래");

lee.display();
park.display();
```

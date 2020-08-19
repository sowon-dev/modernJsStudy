## 풀이
----------------------------------

##### 기본적으로 브라우저 콘솔창에서 this를 칠 경우
```
this;
>Window("use strict" 모드에서는 undefined)
>this는 기본적으로 전역객체(Window)를 참조한다.
```
<br>
##### 1번 문제
```
var data = 10;
function outer(){
    function inner(){
        this.data = 20;
        data = 30;

        console.log("1. data= " + data);
        console.log("2. this.data = " + this.data);
        console.log("3. window.data = " + window.data);
    }
    inner();
}
outer();
```
##### 결과 및 해설
```
1. data= 30
2. this.data = 30
3. window.data = 30
```
**일반 중첩함수에서 this가 무엇을 가리키는지 알아보는 문제**이다. inner()안의 this.data에서 this가 전역객체(Window)를 가리키기 때문에, this.data는 outer() 밖의 전역변수 data와 동일하다. 따라서 전역변수 data의 값이 20으로 바뀐다. 그 다음, `data = 30`에서 data는 지역 변수 내에서 data가 있는지 찾고 없다면 outer()를 호출한 영역에서 data를 찾는다. inner()와 outer() 모두 지역변수로 data가 없기 때문에 여기서 data 역시 전역변수 data를 가리킨다. 따라서 전역변수 data의 값이 30으로 바뀐다. 따라서 결과가 모두 30으로 나온다.

<br>
##### 2번 풀이
```
var data = 10;
function MyClass() {
    this.data = 0;
}
MyClass.prototype.method1 = function(){
    function inner(){
        this.data = 20;
        data = 30;

        console.log("1. data= " + data);
        console.log("2. this.data = " + this.data);
        console.log("3. window.data = " + window.data);
    }
    inner();
}
var my1 = new MyClass();
my1.method1();
```
##### 결과 및 해설
```
1. data= 30
2. this.data = 30
3. window.data = 30
```
**메소드 내부의 중첩함수에서 this가 무엇을 가리키는지 알아보는 문제**이다. 원래 메소드에서 this를 사용하면 메소드를 호출한 객체를 가리킨다. 하지만, 객체의 메소드 내부에서 만들어진 중첩 함수에서 this는 객체가 아닌 전역객체(Window)를 가리킨다. 따라서 1번이랑 마찬가지로, 중첩함수 내부의 this.data와 data가 모두 전역변수 data를 가리키고 결과가 모두 30으로 나온다.


#### 추가정보
`this`는 일반적으로 메소드를 호출한 객체가 저장되어 있는 속성이다. 
```
1. 일반 함수에서 this -> Window
2. 중첩 함수에서 this -> Window
3. 메소드에서 this -> 메소드를 호출한 객체
4. 메소드 내부의 중첩 함수에서 this -> Window
```
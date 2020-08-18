this 용법을 알아보는 문제입니다.

1. 실행 결과를 맞혀보세요.
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


2. 실행 결과를 맞혀보세요.
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

[4.4 객체:기초 메서드와 'this'참고](https://ko.javascript.info/object-methods#ref-1049)의 계산기문제를 참고하여 만든 문제입니다.

```js
let remoteControl = {

    currentCh() {
        this.a = +prompt('기본 채널을 선택하세요:', 1);
        if(this.a  <= 0){
            this.a = +prompt('기본 채널을 다시 선택하세요:', 1);
        }
        let result = confirm("채널을 올릴까요?");
        (result == true) ? remoteControl.chUp() : remoteControl.chDown()
    },

    chUp() {
        if(this.a <= 0){
            alert("현재채널은 1입니다")
        }else{
            alert("현재채널은"+(this.a+1)+"입니다")
        }
    },
  
    chDown() {
        if(this.a <= 0){
            alert("현재채널은 1입니다")
        }else{
            alert("현재채널은"+(this.a-1)+"입니다")
        }
    },
  };

  remoteControl.currentCh();
```

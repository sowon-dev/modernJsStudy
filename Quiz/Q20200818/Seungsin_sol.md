### 1. 다음 코드들이 어떤 결과를 반환할까요?
```
function User(){   
  this.name = "John";   
  return "Sandy";   
}   
alert( new User().name );   
```

-> 해당 생성자의 return문은 원시형을 return하기 때문에 무시되어 John이 출력됩니다.

```
function User(){   
  this.name = "John";   
  return { name : "Sandy" };   
}   
alert( new User().name );  
```

-> 해당 생성자의 return문은 객체를 return하므로 객체가 반환되어 Sandy가 출력됩니다.


### 2. 다음의 기능을 수행하는 addCalcul() 메서드를 만들어보세요.    
- 사용자에게 숫자를 입력받습니다.    
- '취소'를 누르면 종료되고 총 합을 보여줍니다.   

```
let cal = {
            sum: 0,
            num: 0,
            calcul() {
                this.num = prompt("더할 숫자 입력, 취소를 누르면 종료됩니다.", 0);
                while (this.num) {
                    this.sum = Number(this.sum) + Number(this.num);
                    this.num = prompt("더할 숫자 입력, 취소를 누르면 종료됩니다.", 0);
                }
                if (!(this.num)) {
                    alert(this.sum);
                }
            }
        };

        cal.calcul();
 ```

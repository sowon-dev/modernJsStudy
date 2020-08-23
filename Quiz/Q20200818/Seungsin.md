### 1. 다음 코드들이 어떤 결과를 반환할까요?
```
function User(){   
  this.name = "John";   
  return "Sandy";   
}   
alert( new User().name );   
```
```
function User(){   
  this.name = "John";   
  return { name : "Sandy" };   
}   
alert( new User().name );  
```

### 2. 다음의 기능을 수행하는 addCalcul() 메서드를 만들어보세요.    
- 사용자에게 숫자를 입력받습니다.    
- '취소'를 누르면 종료되고 총 합을 보여줍니다.    

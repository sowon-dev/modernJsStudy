[모던자바스크립트튜토리얼 프라미스](https://ko.javascript.info/promise-basics)에 관한 문제입니다.

## 아래의 콜백지옥코드를 프라미스로 변경한 코드입니다. 빈칸에 알맞은 코드를 적으세요. 
 
UserStorage 클래스를 이용하여 아래 4가지를 사용자에게 id, pw를 입력받아 두 메서드 loginUser(), getRoles()를 실행하는 코드입니다. 

```js
class UserStorage{
    loginUser(id, pw, onSuccess, onError){
        setTimeout(()=> {
            if((id === 'Kim' && pw === '1234') || (id === 'Lee' && pw === '5678')){ 
                onSuccess(id); 
            }else{ 
                onError(alert(new Error('존재하지 않는 사용자입니다')));
            }
        }, 2000); //2초뒤에 실행
    }

    getRoles(user, onSuccess, onError){
        setTimeout(()=>{
            if(user === 'Kim'){ 
                onSuccess({name:'Kim', role:'관리자'});
            }else{ 
                onError(alert(new Error('권한이 없습니다')));
            }
        }, 1000); //1초뒤에 실행
    }
}//end of Class

const userStorage = new UserStorage();
const id = prompt('아이디를 입력하세요');
const pw = prompt('비밀번호를 입력하세요');

userStorage.loginUser(id, pw, 
    (user) => {
        userStorage.getRoles(user, 
            userWithRole => { alert(`환영합니다. ${userWithRole.name}님은 ${userWithRole.role}입니다`);},
            error => {console.log(error);}
        );
    }, 
    (error) => {console.log(error)}    
);
```

위의 콜백지옥코드를 Promise로 변경해봅시다.

```js
class UserStorage{
    loginUser(id, pw){
        return 

           [빈칸]
    
    }

    getRoles(user){
        return new Promise((resolve, reject) => {
            setTimeout(()=>{
                if(user === 'Kim'){ 
                    resolve({name:'Kim', role:'관리자'});
                }else{ 
                    reject(alert(new Error('권한이 없습니다')));
                }
            }, 1000); //1초뒤에 실행
        })

    }
}//end of Class

const userStorage = new UserStorage();
const id = prompt('아이디를 입력하세요');
const pw = prompt('비밀번호를 입력하세요');

userStorage.loginUser(id, pw)

    [빈칸]

.catch(console.log);
```
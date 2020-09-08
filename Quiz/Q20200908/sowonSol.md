```js
//프라미스로 변경
class UserStorage{
    loginUser(id, pw){
        return new Promise((resolve, reject)=> {
            setTimeout(()=> {
                if((id === 'Kim' && pw === '1234') || (id === 'Lee' && pw === '5678')){ //일치하면 id전달
                    resolve(id); 
                }else{ //불일치시 Error라는 오브젝트를 만들어서 에러메세지출력 
                    reject(alert(new Error('존재하지 않는 사용자입니다')));
                }
            }, 2000); //2초뒤에 실행
        })
    }

    getRoles(user){
        return new Promise((resolve, reject) => {
            setTimeout(()=>{
                if(user === 'Kim'){ //일치하면 오브젝트를 만들어서 전달
                    resolve({name:'Kim', role:'관리자'});
                }else{ //불일치시 Error라는 오브젝트를 만들어서 에러메세지출력 
                    reject(alert(new Error('권한이 없습니다')));
                }
            }, 1000); //1초뒤에 실행
        })

    }
}//end of Class

//풀이 

//객체생성
const userStorage = new UserStorage();

//사용자에게 id, pw받아오기
const id = prompt('아이디를 입력하세요');
const pw = prompt('비밀번호를 입력하세요');

userStorage.loginUser(id, pw)
.then(user => userStorage.getRoles(user))
.then(user => alert(`환영합니다. ${user.name}님은 ${user.role}입니다`))
.catch(console.log)
```

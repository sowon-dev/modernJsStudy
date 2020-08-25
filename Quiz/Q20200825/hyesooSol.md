```javascript
let ex1 = '((3+4)/9)*(4+1)/(5-2)*8)'; //false
let ex2 = '3+(7/(6+5))'; //true
let ex3 = '6*(2+(4/2-1)'; //false
let ex4 = '(3+4)/7*6+((2-3)*2)'; //true

function is_pair(s){
    let stack =0;
    for(let i = 0; i < s.length; i++){
        if(s[i] == '(') {
            stack++;
        }else if (s[i] == ')') {
            stack--;
        }
    }
    return stack == 0;
}

console.log(is_pair(ex1));
console.log(is_pair(ex2));
console.log(is_pair(ex3));
console.log(is_pair(ex4));
```

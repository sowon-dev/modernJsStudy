### 문제1 

```javascript
function quiz(num){
    let i,j,k;
    for(i=1; i<=num; i++){
       console.log('*'.repeat(i));
    }
    for(i=1; i<=num; i++){
        numbers = ''
        for(j=1; j<=i; j++){
            numbers += `${j}`;
        }
        console.log(numbers);
    }
    for(i=1; i<=num; i+=2){
        star2 = ''
        for(j=1; j<=(num-i)/2; j++){
            star2 += ' ';
        }
        for(k=1; k<=i; k++){
            star2 += '*';
        }
        for(j=1; j<=(num-i)/2; j++){
            star2 += ' ';
        }
        console.log(star2);
    }
}

quiz(5);
quiz(3);
```

### 문제2

```javascript
function max(num1, num2, num3){
    let max;
    if(num1 > num2){
        if(num1 > num3) { max = num1;}
        else { max = num3;}
    }
    else{
        if(num2 > num3) {max = num2;}
        else { max = num3;}
    }
    console.log(`max is ${max}`);
}

max(3,5,6);
```

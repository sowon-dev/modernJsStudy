### 1. n의 팩토리얼을 구하는 함수 fact를 작성하여라.<br>
```
function fact(n)
{
    if(n <= 1)
    {
        return 1;
    }
    return n*fact(n-1);
}
fact(5); // test
```

### 2. 실행결과에 알맞도록 myConcat 함수를 완성하여라. <br>

```
function myConcat(separator)
{
	var s = "";
	for(let i = 1; i < arguments.length; i++)
	{
		s+= arguments[i];
                        if(i < arguments.length-1)
                        {
                        	s+= separator;
		}
	}
	return s;
}

console.log(myConcat("/", "apple", "orange", "peach"));
```

실행결과<br>
apple/orange/peach
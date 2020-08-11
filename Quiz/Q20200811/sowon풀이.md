
## 1번문제 : 구구단 가로출력

```js
for(let dan=2; dan<=9; dan++){
	document.write('<br>')
	for(let num=1; num<=9; num++){
		document.write(dan+'*'+num+'='+(dan*num)+' ')
	}
}
```

## 2번문제 : 구구단 세로출력

```js
for(let i=2; i<=9; i++){
	document.write('    <' + i +'단>  ')
}

for(let dan=1; dan<=9; dan++){
	document.write('<br>') 
	for(let num=2; num<=9; num++){
		document.write(num+'*'+dan+'=   '+(dan*num)+', ')
	}
}
```

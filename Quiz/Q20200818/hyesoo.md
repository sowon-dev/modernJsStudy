이 문제는 깊은 복사를 별도의 내장 메서드 없이 for문과 if문으로만 구현해보고자 만든 문제입니다.

```javascript
let ironman = {
    name: "Tony Stark",
    age: 53,
    species: 'human',
    nation: 'USA',
    'belongs to': {
        name: 'Avengers',
        since: 2011,
    },
};

//이 부분을 채워주세요. 별도의 내장 메서드를 사용하지 않고, for문, if문, typeof를 사용하여 구현하였습니다.


spidy.name = 'Peter Parker';
spidy.age = 21;
spidy['belongs to'].since = 2018;

console.log(ironman);
console.log(spidy);
```

콘솔에 찍히는 내용이 아래와 같도록 가운데 코드를 채워주세요

```bash
{
  name: 'Tony Stark',
  age: 53,
  species: 'human',
  nation: 'USA',
  'belongs to': { name: 'Avengers', since: 2011 }
}
{
  name: 'Peter Parker',
  age: 21,
  species: 'human',
  nation: 'USA',
  'belongs to': { name: 'Avengers', since: 2018 }
}
```

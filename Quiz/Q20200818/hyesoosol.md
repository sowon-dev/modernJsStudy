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

let spidy = {};
for (let prop in ironman) {
    if (typeof ironman[prop] == 'object') {
        spidy[prop] = {};
        for (let key in ironman[prop]) {
            spidy[prop][key] = ironman[prop][key];
        }
    } else {
    spidy[prop] = ironman[prop];
    }
}

spidy.name = 'Peter Parker';
spidy.age = 21;
spidy['belongs to'].since = 2018;

console.log(ironman);
console.log(spidy);
```

### 무엇이 출력될까요?<br>

```
function Rabbit(name) {
	this.name = name;
}
Rabbit.prototype = {
	eats: true
};

let rabbit = new Rabbit("Pink Rabbit");
let rabbit2 = new Rabbit("Brown Rabbit");
rabbit.eats = false;

alert(rabbit2.eats);
```

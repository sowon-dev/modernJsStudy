**order.js**
```javascript
const {checkStock, makeOrder} = require('./store.js');

const order1 = {
    items : [['egg',1],['apple',3]],
    money : 4000
}

const order2 = {
    items : [['egg',3],['apple',4]],
    money : 4500
}

const order3 = {
    items : [['bread',2]],
    money : 5000
}

checkStock(order1)
.then((resolvedOrder)=>{
    return makeOrder(resolvedOrder)
})
.then((successMessage) => {
    console.log(successMessage);
})
.catch((errorMessage) => {
    console.log(errorMessage);
})
```

**store.js**
```javascript
const store = {
    egg: {
        stock: 10,
        cost: 500
    },
    apple: {
        stock: 5,
        cost: 1000
    },
    bread: {
        stock: 1,
        cost: 2500
    }
}

function checkStock(order){
    return new Promise((resolve,reject)=>{
        const items = order.items;
        let inStock = true;
        let outOfStock = '';
        for (let i=0; i < items.length; i++){
            if(store[items[i][0]].stock < items[i][1]){
                inStock = false;
                outOfStock = items[i][0];
                break;
            }
        }
        if (inStock){
            let totalPrice = 0;
            items.forEach(item => {
                totalPrice += item[1]*store[item[0]].cost
            });
            resolve([order,totalPrice]);
        } else {
            reject(`${outOfStock}의 재고가 부족합니다.`)
        }
    })
}

function makeOrder(returnedArray){
    const order = returnedArray[0];
    const totalPrice = returnedArray[1];
    return new Promise((resolve,reject) => {
        if(order.money >= totalPrice ){
            resolve(`주문이 완료되었습니다. 거스름돈은 ${order.money - totalPrice}원 입니다.`)
        } else {
            reject(`지불하신 금액이 ${totalPrice - order.money} 원 부족합니다.`)
        }
    })
}

module.exports = {checkStock,makeOrder};
```

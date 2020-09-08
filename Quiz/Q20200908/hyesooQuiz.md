프라미스 체이닝과 모듈 가져오기를 이용하여 주문 시스템을 만들어보는 문제입니다 !

**store.js** 와 **order.js** 의 두 가지 파일이 존재합니다.

**store.js** 파일은 주문을 하는데에 필요한 checkStock과 makeOrder 함수를 정의하고, 모듈로 내보냅니다.
checkStock 으로는 재고가 있는지 확인하고, makeOrder 로는 손님이 지불한 돈이 물건의 총 가격보다 크거나 같은지 확인합니다.
<br/><br/>
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
    // 이 부분을 채워주세요 !!
    // 손님이 지불한 금액이 물건의 총 금액보다 크거나 같으면 resolve하고, 그렇지 않으면 reject 합니다.
    // resolve와 reject에는 거스름돈이나 부족한 금액을 알려주세요
}

module.exports = {checkStock,makeOrder};
```

store 오브젝트는 가게에 있는 물건들의 각각의 재고와 가격을 가지고 있습니다. <br/>
예를 들어 지금 이 가게에는 500원짜리 달걀이 10개, 1000원짜리 사과가 5개, 2500원짜리 빵이 1개 재고로 있습니다. <br/>

store에 담긴 정보와 order에 담긴 정보를 비교하여 주문을 완료하거나 reject 합니다.


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
.then(
    //이 부분을 체워주세요
})
.then((successMessage) => {
    console.log(successMessage);
})
.catch((errorMessage) => {
    console.log(errorMessage);
})
```
order1,2,3는 각각 손님이 주문한 내역을 의미합니다. items는 손님이 주문한 물건과 그 개수를 담고 있습니다. money는 손님이 낸 금액입니다. <br/>
예를 들어 order1은 egg를 1개, apple을 3개 주문하고 4000원을 지불했습니다.

checkStore 함수가 받는 파라미터를 order1, order2, order3 차례로 바꾸어 실행하면 다음과 같은 결과를 출력합니다.

![스크린샷 2020-09-08 오후 9 02 34](https://user-images.githubusercontent.com/43427306/92475901-1776fe80-f219-11ea-922c-b19f4f853154.png)


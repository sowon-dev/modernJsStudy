### 1. 다음 조건에 알맞은 코드를 작성하세요.

두 정수 a, b가 주어졌을 때 a와 b 사이에 속한 모든 정수의 곱을 리턴하는 함수,<br> 
answer을 만들어주세요. 예를 들어 a = 3, b = 5인 경우, 3 * 4 * 5 = 60이므로<br>
60을 리턴합니다.<br>
<br>
### 2. 다음 코드의 실행 결과로 알맞은 것은?
```
<script type="text/javascript">
    function car(name) {
        this.name = name;
        this.start = function() {
            alert(this.name + "차가 출발한다.");
        }
    }

    car1 = new car("Sonata");
    car1.start();
    
    car2 = new car("SM5");
    car2.start();
</script>
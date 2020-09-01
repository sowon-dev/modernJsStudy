```javascript
<script>
function getMonthName (month) {
    month -=1;
    const months = ["Jan","Feb","Mar","Apr","May","Jun","Jul","Aug","Sep","Oct","Nov","Dec"]
    if (months[month] != null) {
        return months[month];
    } else {
        throw "inputError";
    }
}

try{
    let monthName = getMonthName(+prompt("오늘은 무슨 달인가요?",0));
    alert(monthName);
} catch(e) {
    alert(e)
}
</script>
```

```
| sun | mo | tu | we | th | fr | sat |
|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
<%*
const days = parseInt(moment().daysInMonth()) + parseInt(moment().startOf("month").format("d"))
const table = []
table.push("|")
for (let i = 0; i < days; i++) {
   if (i > 0 && i % 7 === 0) {
        table.push("\n|")
   }
   table.push(`[[${moment().day(i).format("YYYY-MM-DD")}]]|`)
}
tR += table.join("")
%>
```

| sun | mo | tu | we | th | fr | sat |
|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
<%*
const days = parseInt(moment().daysInMonth()) + parseInt(moment().startOf("month").format("d"))
const table = []
table.push("|")
for (let i = 0; i < days; i++) {
   if (i > 0 && i % 7 === 0) {
        table.push("\n|")
   }
   table.push(`[[${moment().day(i).format("YYYY-MM-DD")}]]|`)
}
tR += table.join("")
%>
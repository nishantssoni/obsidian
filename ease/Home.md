

> [!quote] 
> If you think the prize of winning is too high,
> wait till you get the bill from regrets. 

**Extra Two hours if you achieve your goals**
### stats
```dataviewjs
let pages = dv.pages('"7 - Calendar"').array(); // Convert pages to an array

// Parse total_hour , default to 0 if missing or invalid
let totalHours = pages.reduce((sum, p) => sum + Number(p.total_hour || 0), 0);

let avgRating = 0;
let perDayReal = totalHours / pages.length;
let goal_done_count = pages.reduce((sum, p) => sum + Number(p.goal_done || 0), 0);
let perDay = (totalHours + (goal_done_count * 2)) / pages.length;

if(perDay > 10){
	avgRating = 5;
}
else if(perDay > 8 && perDay < 10){
	avgRating = 4;
}
else if(perDay > 5 && perDay < 8){
	avgRating = 3;
}
else if(perDay > 3 && perDay < 5){
	avgRating = 2;
}
else{
	avgRating = 1;
}

//
// let avgRating = 
//    pages.reduce((sum, p) => sum + Number(p.study_rating || 0), // 0) / pages.length;


let notes = dv.pages('"6 - Zettelkasten"').array(); // Convert pages to an array

// Parse total_hour and study_rating as numbers, default to 0 if missing or invalid
let no_of_notes = notes.length;
let no_of_calendars = pages.length;


dv.table(["Metric", "Value"], [
    ["Total Hours", totalHours],
 //   ["Avg Per Day Hours", perDay.toFixed(2) ],
    ["Average Study Rating (max: 5)", avgRating],
    ["Total No. of study days", no_of_calendars],
    ["Total No. of Main Notes", no_of_notes],
]);

```
#### calendar
```dataview
table from "7 - Calendar" sort file.name desc limit 3
```
#### Index
```dataview
table from "4 - Index"
```
#### Future YTD Watch
1. [[NN zero to Hero by Andrej]]
2. [[How To get Rich without getting lucky (Naval)]]

#### Pending Projects source YTD
3. [[tennis analysis using Opencv]]
4. [[Building a Social API using Fast API]]


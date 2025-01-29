

> [!quote] 
> If you think the prize of winning is too high,
> wait till you get the bill from regrets. 

### stats
```dataviewjs
let pages = dv.pages('"7 - Calendar"').array(); // Convert pages to an array

// Parse total_hour and study_rating as numbers, default to 0 if missing or invalid
let totalHours = pages.reduce((sum, p) => sum + Number(p.total_hour || 0), 0);
let avgRating = 
    pages.reduce((sum, p) => sum + Number(p.study_rating || 0), 0) / pages.length;

dv.table(["Metric", "Value"], [
    ["Total Hours", totalHours],
    ["Average Rating", avgRating.toFixed(2)],
]);


```
```dataview
table total_hour, study_rating from "7 - Calendar" limit 3
```
### Currently Running Indexes
1. [[Applied AI index]]

### Future YTD Watch
1. [[NN zero to Hero by Andrej]]

### Pending Projects source YTD
1. [[tennis analysis using Opencv]]
2. [[Building a Social API using Fast API]]


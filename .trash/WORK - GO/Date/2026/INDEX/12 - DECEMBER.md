```dataviewjs
// 1. Fetch pages and sort by Filename descending
let pages = dv.pages('"WORK - GO/Date/2026/12"')
    .sort(p => p.file.link, 'desc');

// 2. Calculate the Totals (using .array() to ensure they are treatable as numbers)
let totalOT = pages.OT.array().reduce((acc, val) => acc + (Number(val) || 0), 0);
let totalTrucks = pages.trucks.array().reduce((acc, val) => acc + (Number(val) || 0), 0);

// 3. Prepare the rows and CONVERT to a standard array with .array()
let rows = pages.map(p => [
    p.file.link, 
    p.trucks || 0, 
    ((Number(p.out) || 0) - (Number(p.in) || 0)), 
    p.OT || 0
]).array(); // <--- CRITICAL FIX: This converts DataArray to a standard JS Array

// 4. Now rows.push will work without error
rows.push([
    "**TOTAL**", 
    `**${totalTrucks}**`, 
    "", 
    `**${totalOT}**`
]);

// 5. Render the Table
dv.table(["Date", "Trucks", "ODO", "OT"], rows);
```
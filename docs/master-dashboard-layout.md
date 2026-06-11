# Master Dashboard Layout

## Goal
Create one visible command center tab that summarizes the entire workbook.

## Dashboard grid recommendation
Use columns `A:L` with section blocks.

### Header area
- `A1:L2` merged title area: **Teacher Command Center Dashboard**
- `A3:C6` Teacher profile
- `D3:F6` Class profile
- `G3:L6` Quick reminders

### KPI cards
Place labels in column `B` and formulas in column `C`.
- `B8` Total Students
- `B9` Attendance Rate
- `B10` Students Absent Today
- `B11` Students Late Today
- `B12` Assignments Due This Week
- `B13` Awaiting Grading
- `B14` Upcoming Assessments
- `B15` Parent Contacts This Month
- `B16` Students Requiring Intervention
- `B17` PD Hours YTD

### Upcoming dates
- `E8:H15`
- headers in row 8: Date, Category, Event, Owner
- spill/results start at row 9

### Attendance snapshot
- `J8:L15`
- metrics for present, absent, late, monthly attendance

### Student support alerts
- `A20:D30`
- headers: Student, Reading, Math Number, Overall

### Assignments & assessments
- `F20:I30`
- headers: Type, Title, Date/Due, Status

### Recent communication
- `J20:L30`
- headers: Date, Student, Topic

### Planning snapshot
- `A33:F40`
- week start, focus, next assessment, current unit

### Professional snapshot
- `H33:L40`
- PD hours, next certification expiry, next meeting, notes

## Suggested formatting
- soft floral banner
- KPI cards with pastel fills
- conditional formatting for overdue items
- freeze top row
- hide gridlines for polished appearance

# One-Tab-Only Simplified Version

This version is for users who want a truly simplified workbook centered on a single worksheet.

## Important limitation
A one-tab-only version is best for light use. It cannot replace the flexibility of a full multi-sheet system for large-scale tracking.

## Recommended sections on one tab
Use one worksheet called `One Tab Dashboard` with these stacked sections:

### Section 1 — Teacher & class profile
Columns A:D
- Teacher Name
- School
- Grade
- Homeroom
- School Year
- Reporting Period

### Section 2 — KPI summary
Columns A:C
- Total Students
- Attendance Rate
- Students Absent Today
- Students Late Today
- Assignments Due This Week
- Awaiting Grading
- Upcoming Assessments
- Parent Contacts This Month
- Students Requiring Intervention
- PD Hours YTD

### Section 3 — Student mini roster
Columns A:G
- Student ID
- Student Name
- Reading
- Writing
- Math
- Overall Standing
- Intervention?

### Section 4 — This week’s tasks
Columns I:M
- Type
- Title
- Date/Due
- Status
- Notes

### Section 5 — Attendance today
Columns A:E
- Student
- Attendance Code
- Entry Time
- Minutes Late
- Notes

### Section 6 — Recent communication
Columns G:K
- Date
- Student
- Contact Type
- Topic
- Follow-Up

### Section 7 — Upcoming important dates
Columns A:D
- Date
- Category
- Event
- Owner

### Section 8 — Planning focus
Columns F:J
- Current Unit
- Literacy Focus
- Numeracy Focus
- Next Assessment
- Weekly Notes

## Simplified formulas
If all data is kept manually on one tab, summary formulas can reference local ranges.

### Example total students
`=COUNTA(A25:A44)`

### Example attendance rate
`=COUNTIF(B55:B74,"Present")/COUNTIF(B55:B74,"<>")`

### Example intervention count
`=COUNTIF(G25:G44,"Yes")`

## Best use case
This version is best for:
- a smaller class snapshot
- weekly planning
- simple tracking
- printable teacher-at-a-glance use

## Recommendation
Offer both products:
1. Full dashboard-first workbook
2. One-tab-only simplified teacher snapshot

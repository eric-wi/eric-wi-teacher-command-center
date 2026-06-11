# Dashboard Formulas Guide

Assumes sheet names match the CSV names after import and headers are in row 1.

## Header/profile suggestions
- `B3`: Teacher Name
- `B4`: School
- `B5`: Grade
- `B6`: Homeroom
- `E3`: School Year
- `E4`: Reporting Period
- `E5`: Total Active Students
- `E6`: Today's Date

### Example static/linked entries
- `E5`  
  `=COUNTIF('Student Directory'!H:H,"Active")`
- `E6`  
  `=TODAY()`

## KPI formulas

### C8 Total Students
`=COUNTIF('Student Directory'!H:H,"Active")`

### C9 Attendance Rate
`=IFERROR(COUNTIF('Attendance Tracker'!G:G,"Present")/COUNTIFS('Attendance Tracker'!G:G,"<>"),0)`

### C10 Students Absent Today
`=COUNTIFS('Attendance Tracker'!A:A,TODAY(),'Attendance Tracker'!G:G,"Absent")`

### C11 Students Late Today
`=COUNTIFS('Attendance Tracker'!A:A,TODAY(),'Attendance Tracker'!G:G,"Late")`

### C12 Assignments Due This Week
`=COUNTIFS('Assignment Tracker'!G:G,">="&TODAY(),'Assignment Tracker'!G:G,"<="&TODAY()+7)`

### C13 Awaiting Grading
`=COUNTIF('Assignment Tracker'!J:J,"Awaiting Grading")`

### C14 Upcoming Assessments
`=COUNTIFS('Assessment Tracker'!E:E,">="&TODAY(),'Assessment Tracker'!E:E,"<="&TODAY()+14)`

### C15 Parent Contacts This Month
`=COUNTIFS('Communication Log'!A:A,">="&EOMONTH(TODAY(),-1)+1,'Communication Log'!A:A,"<="&EOMONTH(TODAY(),0))`

### C16 Students Requiring Intervention
`=COUNTIF('Student Progress Tracker'!L:L,"Yes")`

### C17 PD Hours YTD
`=SUM('Professional Development Tracker'!E:E)`

## Upcoming dates table
Headers in `E8:H8`
- E8 Date
- F8 Category
- G8 Event
- H8 Owner

### Google Sheets dynamic formula in E9
`=SORT(FILTER({'Important Dates Tracker'!A2:A,'Important Dates Tracker'!B2:B,'Important Dates Tracker'!C2:C,'Important Dates Tracker'!F2:F},'Important Dates Tracker'!A2:A>=TODAY(),'Important Dates Tracker'!G2:G<>"Y"),1,TRUE)`

## Student support alerts
Headers in `A20:D20`
- A20 Student
- B20 Reading
- C20 Math Number
- D20 Overall

### Google Sheets dynamic formula in A21
`=FILTER({'Student Progress Tracker'!B2:B,'Student Progress Tracker'!C2:C,'Student Progress Tracker'!E2:E,'Student Progress Tracker'!K2:K},('Student Progress Tracker'!K2:K="Below")+('Student Progress Tracker'!L2:L="Yes"))`

## Assignments and assessments snapshot
Headers in `F20:I20`
- F20 Type
- G20 Title
- H20 Date/Due
- I20 Status

### Assignments block in F21
`=SORT(FILTER({'Assignment Tracker'!E2:E,'Assignment Tracker'!D2:D,'Assignment Tracker'!G2:G,'Assignment Tracker'!J2:J},'Assignment Tracker'!G2:G>=TODAY()-7),3,TRUE)`

## Recent communication
Headers in `J20:L20`
- J20 Date
- K20 Student
- L20 Topic

### Formula in J21
`=SORT(FILTER({'Communication Log'!A2:A,'Communication Log'!B2:B,'Communication Log'!E2:E},'Communication Log'!A2:A<>""),1,FALSE)`

## Attendance snapshot metrics
- `J8` Present
- `J9` Absent
- `J10` Late
- `J11` Attendance This Month

### K8
`=COUNTIF('Attendance Tracker'!G:G,"Present")`

### K9
`=COUNTIF('Attendance Tracker'!G:G,"Absent")`

### K10
`=COUNTIF('Attendance Tracker'!G:G,"Late")`

### K11
`=IFERROR(COUNTIFS('Attendance Tracker'!G:G,"Present",'Attendance Tracker'!A:A,">="&EOMONTH(TODAY(),-1)+1,'Attendance Tracker'!A:A,"<="&EOMONTH(TODAY(),0))/COUNTIFS('Attendance Tracker'!A:A,">="&EOMONTH(TODAY(),-1)+1,'Attendance Tracker'!A:A,"<="&EOMONTH(TODAY(),0)),0)`

## Conditional formatting suggestions
- overdue due dates: red fill
- upcoming due within 3 days: yellow fill
- intervention flagged: soft red row fill
- below expectation: orange fill

# Dashboard Formulas Guide

Assumes headers in row 1 and data beginning in row 2.

## Dashboard KPI cells

- `C2` Total Students  
  `=COUNTIF('Student Directory'!H:H,"Active")`

- `C3` Attendance Rate  
  `=IFERROR(COUNTIF('Attendance Tracker'!G:G,"Present")/COUNTIFS('Attendance Tracker'!G:G,"<>"),0)`

- `C4` Students Absent Today  
  `=COUNTIFS('Attendance Tracker'!A:A,TODAY(),'Attendance Tracker'!G:G,"Absent")`

- `C5` Students Late Today  
  `=COUNTIFS('Attendance Tracker'!A:A,TODAY(),'Attendance Tracker'!G:G,"Late")`

- `C6` Assignments Due This Week  
  `=COUNTIFS('Assignment Tracker'!G:G,">="&TODAY(),'Assignment Tracker'!G:G,"<="&TODAY()+7)`

- `C7` Awaiting Grading  
  `=COUNTIF('Assignment Tracker'!J:J,"Awaiting Grading")`

- `C8` Upcoming Assessments  
  `=COUNTIFS('Assessment Tracker'!E:E,">="&TODAY(),'Assessment Tracker'!E:E,"<="&TODAY()+14)`

- `C9` Parent Contacts This Month  
  `=COUNTIFS('Communication Log'!A:A,">="&EOMONTH(TODAY(),-1)+1,'Communication Log'!A:A,"<="&EOMONTH(TODAY(),0))`

- `C10` Students Requiring Intervention  
  `=COUNTIF('Student Progress Tracker'!L:L,"Yes")`

- `C11` PD Hours YTD  
  `=SUM('Professional Development Tracker'!E:E)`

## Conditional formatting suggestions

### Assignment Tracker overdue
`=AND($G2<TODAY(),$J2<>"Graded",$J2<>"Returned")`

### Assignment due in next 3 days
`=AND($G2>=TODAY(),$G2<=TODAY()+3,$J2<>"Graded")`

### Important Dates due within 7 days
`=AND($A2>=TODAY(),$A2<=TODAY()+7,$G2<>"Y")`

### Certifications expiring in 30 days
`=AND($C2>=TODAY(),$C2<=TODAY()+30)`

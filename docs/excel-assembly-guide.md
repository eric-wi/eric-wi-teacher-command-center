# Excel Assembly Guide

This guide shows how to turn the CSV starter pack into a polished Excel workbook.

## Part 1 — Download and extract
1. Download the repository ZIP from GitHub.
2. Extract the ZIP to a folder on your computer.
3. Confirm you can see the `csv` and `docs` folders.

## Part 2 — Create the workbook
1. Open Microsoft Excel.
2. Create a new blank workbook.
3. Save it immediately as `Teacher-Command-Center.xlsx`.

## Part 3 — Import the CSV files
Use **Data > From Text/CSV** for each CSV file.

Recommended order:
1. `01_Dashboard.csv`
2. `09_Student_Directory.csv`
3. `21_Assignment_Tracker.csv`
4. `24_Assessment_Tracker.csv`
5. `25_Student_Progress_Tracker.csv`
6. `26_Attendance_Tracker.csv`
7. `32_Communication_Log.csv`
8. `39_Important_Dates_Tracker.csv`
9. `33_Professional_Development_Tracker.csv`
10. all remaining optional sheets
11. `42_Lists.csv`
12. `43_Ontario_Grade_2_Curriculum_Map.csv`
13. `44_Comment_Bank.csv`
14. `45_Dashboard_Data.csv`

For each import:
1. Choose the CSV file.
2. Verify delimiter is comma.
3. Click **Load To...**
4. Choose **Table** and **New Worksheet**.
5. Rename the worksheet to the friendly sheet name, for example:
   - `Dashboard`
   - `Student Directory`
   - `Assignment Tracker`
   - `Assessment Tracker`

## Part 4 — Rename worksheets
Recommended worksheet names:
- Dashboard
- Student Directory
- Assignment Tracker
- Assessment Tracker
- Student Progress Tracker
- Attendance Tracker
- Communication Log
- Important Dates Tracker
- Professional Development Tracker
- Lists
- Ontario Grade 2 Curriculum Map
- Comment Bank
- Dashboard Data

## Part 5 — Set up the Dashboard sheet
1. Open the `Dashboard` sheet.
2. Widen columns A:L.
3. Set row heights:
   - Row 1 = 26
   - Row 2 = 26
   - Rows 3:6 = 22
   - Rows 8:17 = 22
4. Merge and center `A1:L2`.
5. Type the title: `Teacher Command Center Dashboard`.
6. Add teacher information labels in:
   - `A3` Teacher Name
   - `A4` School
   - `A5` Grade
   - `A6` Homeroom
   - `D3` School Year
   - `D4` Reporting Period
   - `D5` Active Students
   - `D6` Today

## Part 6 — Add dashboard formulas
Paste these formulas:

- `E5`
`=COUNTIF('Student Directory'!H:H,"Active")`

- `E6`
`=TODAY()`

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

Values in `C8:C17`:

- `C8`
`=COUNTIF('Student Directory'!H:H,"Active")`

- `C9`
`=IFERROR(COUNTIF('Attendance Tracker'!G:G,"Present")/COUNTIFS('Attendance Tracker'!G:G,"<>"),0)`

- `C10`
`=COUNTIFS('Attendance Tracker'!A:A,TODAY(),'Attendance Tracker'!G:G,"Absent")`

- `C11`
`=COUNTIFS('Attendance Tracker'!A:A,TODAY(),'Attendance Tracker'!G:G,"Late")`

- `C12`
`=COUNTIFS('Assignment Tracker'!G:G,">="&TODAY(),'Assignment Tracker'!G:G,"<="&TODAY()+7)`

- `C13`
`=COUNTIF('Assignment Tracker'!J:J,"Awaiting Grading")`

- `C14`
`=COUNTIFS('Assessment Tracker'!E:E,">="&TODAY(),'Assessment Tracker'!E:E,"<="&TODAY()+14)`

- `C15`
`=COUNTIFS('Communication Log'!A:A,">="&EOMONTH(TODAY(),-1)+1,'Communication Log'!A:A,"<="&EOMONTH(TODAY(),0))`

- `C16`
`=COUNTIF('Student Progress Tracker'!L:L,"Yes")`

- `C17`
`=SUM('Professional Development Tracker'!E:E)`

## Part 7 — Add tables
### Upcoming dates
Headers in `E8:H8`:
- Date
- Category
- Event
- Owner

In Excel, use either formulas or manually create a filtered table sourced from `Important Dates Tracker`.

### Student support alerts
Headers in `A20:D20`:
- Student
- Reading
- Math Number
- Overall

Source from `Student Progress Tracker` using filters for:
- Overall Standing = Below
- Intervention Required? = Yes

### Assignments & assessments
Headers in `F20:I20`:
- Type
- Title
- Date/Due
- Status

Use filtered views from `Assignment Tracker` and `Assessment Tracker`.

### Recent communication
Headers in `J20:L20`:
- Date
- Student
- Topic

Source from `Communication Log`.

## Part 8 — Create charts
Use `Dashboard Data`.
Recommended charts:
1. Attendance by month
2. Student performance distribution
3. Assignment status distribution
4. Parent communication count by month

## Part 9 — Formatting
1. Freeze top row on all sheets.
2. Turn on filters for all tracker sheets.
3. Hide these sheets if desired:
   - Lists
   - Ontario Grade 2 Curriculum Map
   - Comment Bank
   - Dashboard Data
4. Protect formula cells on Dashboard.

## Part 10 — Save your polished workbook
Save as:
- `.xlsx` for normal use
- `.xltx` if you want it as a reusable Excel template

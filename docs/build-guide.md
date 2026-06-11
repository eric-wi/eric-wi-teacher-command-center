# Build Guide

## Dashboard-first workbook assembly

### Keep these tabs visible
- Dashboard
- Student Directory
- Assignment Tracker
- Assessment Tracker
- Attendance Tracker
- Student Progress Tracker
- Communication Log
- Important Dates Tracker
- Professional Development Tracker

### Hide these tabs if desired
- Lists
- Ontario Grade 2 Curriculum Map
- Comment Bank
- Dashboard Data
- all optional planning/support tabs not needed daily

## Setup steps
1. Import all CSV files into a single workbook.
2. Rename tabs to friendly names without numeric prefixes if desired.
3. Build the Dashboard using `docs/master-dashboard-layout.md`.
4. Paste formulas from `docs/dashboard-formulas.md`.
5. Add filters to all tracker tabs.
6. Freeze row 1 on all sheets.
7. Protect formula cells on the Dashboard.

## Recommended charts sourced from Dashboard Data
- attendance by month
- assignment status summary
- student performance distribution
- communication count by month

## Suggested workflow
Use Dashboard as the only landing page. Enter and maintain data in the tracker tabs, while the Dashboard displays the summary.

# Part 3 - Data Integrity Audit

This is Part 3 of the assignment.
I checked the database for bad data and fixed the issues.

## Files
- import_validation.sql - checks row counts and NULL values
- integrity_audit.sql - checks duplicates and orphan records
- domain_rule_checks.sql - checks invalid status values and rules
- repair_plan.md - explains what issues I found and how to fix them
- staging_repair_scripts.sql - SQL scripts that fix the issues
- before_after_evidence.md - shows data before and after fixing
- README.md - this file

## Issues I Found
- typo 'actve' in student status
- invalid difficulty 'Very Hard' in problems
- wrong contest status values like published and done
- wrong submission status 'OK'
- score 999 which is more than max score 75
- negative score -10
- contest end time is before start time
- wrong attendance status 'joined'
- wrong regrade status values like open and closed
- wrong plagiarism flag status values like new and cleared
- similarity score 125 which is out of range
- wrong enrollment status 'ongoing'
- missing and invalid emails in students
- duplicate enrollment for same student and course
- orphan records pointing to students and courses that don't exist

## How to Run
sqlite3 codejudge_raw.db < import_validation.sql
sqlite3 codejudge_raw.db < integrity_audit.sql
sqlite3 codejudge_raw.db < domain_rule_checks.sql
sqlite3 codejudge_raw.db < staging_repair_scripts.sql
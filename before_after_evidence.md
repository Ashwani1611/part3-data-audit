# Before and After Evidence

## Issue 1 - Typo in student status
before: S0089|Kunal Gupta|actve
after:  S0089|Kunal Gupta|active
result: typo fixed successfully

## Issue 2 - Invalid problem difficulty
before: P0010|Knapsack 10|Very Hard
after:  P0010|Knapsack 10|Hard
result: difficulty changed to valid value

## Issue 3 - Invalid contest status
before:
CT001|CS205 Weekly Challenge 1|published
CT004|CS102 Weekly Challenge 4|published
CT006|CS205 Weekly Challenge 6|published
CT008|CS201 Weekly Challenge 8|scheduled
CT009|CS204 Weekly Challenge 9|published
CT010|CS103 Weekly Challenge 10|done

after:
CT001|CS205 Weekly Challenge 1|active
CT004|CS102 Weekly Challenge 4|active
CT006|CS205 Weekly Challenge 6|active
CT008|CS201 Weekly Challenge 8|upcoming
CT009|CS204 Weekly Challenge 9|active
CT010|CS103 Weekly Challenge 10|completed
result: all contest statuses mapped to valid values

## Issue 4 - Wrong submission status
before: SUB000208|OK
after:  SUB000208|Accepted
result: status changed to valid value

## Issue 5 - Score greater than max score
before: SUB000103|score 999|max score 75
action: moved to suspicious_submissions table for manual review
result: not directly changed as correct score is unknown

## Issue 6 - Negative score
before: SUB000056|S0148|-10
after:  SUB000056|S0148|0
result: negative score set to 0 until verified

## Issue 7 - Contest end time before start time
before: CT005|start 2025-04-05 12:00:00|end 2025-04-05 11:00:00
after:  CT005|start 2025-04-05 11:00:00|end 2025-04-05 12:00:00
result: start and end times swapped correctly

## Issue 8 - Wrong attendance status
before: A000046|joined
after:  A000046|Present
result: status changed to valid value

## Issue 9 - Wrong regrade request status
before:
RG0001|open
RG0003|closed
RG0023|done

after:
RG0001|pending
RG0003|rejected
RG0023|approved
result: all regrade request statuses mapped to valid values

## Issue 10 - Wrong plagiarism flag status
before:
PF0001|new
PF0003|cleared
PF0005|reviewing

after:
PF0001|pending
PF0003|dismissed
PF0005|pending
result: all flag statuses mapped to valid values

## Issue 11 - Similarity score out of range
before: PF0015|125.0
action: moved to suspicious_flags table for manual review
result: not directly changed as correct value is unknown

## Issue 12 - Wrong enrollment status
before: E00042|ongoing
after:  E00042|active
result: status changed to valid value

## Issue 13 - Missing or invalid email
before:
S0005|Ayaan Gupta|(empty email)
S0018|Anika Patel|ravi.no-at-symbol.codejudge.edu
S0077|Nisha Chatterjee|(empty email)
action: moved to students_bad_email table for manual review
result: cannot guess correct email so flagged for verification

## Issue 14 - Duplicate enrollment
before: S0001|C006|count 2
after:  S0001|C006|count 1
result: duplicate record removed successfully

## Issue 15 - Orphan records
records moved to orphan_records table:
SUB000013 has student S9999 not in students table
SUB000038 has problem P9999 not in problems table
E00718 has student S9999 not in students table
E00719 has course C999 not in courses table
A000018, A000068, A000104, A000176, A000227, A000257 have student S9999
A000032 has session SES9999 not in sessions table
action: all moved to orphan_records table for review
result: original data not deleted just flagged for verification
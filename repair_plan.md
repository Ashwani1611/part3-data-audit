# Repair Plan

## Issue 1 - Typo in student status
record: S0089 Kunal Gupta has status 'actve' instead of 'active'
this is clearly a typing mistake
I will correct the spelling to 'active'

## Issue 2 - Invalid problem difficulty
record: P0010 Knapsack 10 has difficulty 'Very Hard'
valid values are only Easy, Medium or Hard
I will change it to 'Hard' as that is the closest valid value

## Issue 3 - Invalid contest status values
records: CT001, CT004, CT006, CT009, CT010 have wrong status values
published means it is live so I will change to 'active'
scheduled means not started so I will change to 'upcoming'
done means finished so I will change to 'completed'

## Issue 4 - Wrong submission status
record: SUB000208 has status 'OK'
OK is not a valid status in our system
it most likely means the submission was accepted
I will change it to 'Accepted'

## Issue 5 - Score is more than max score
record: SUB000103 has score 999 but max score for that problem is 75
this is clearly wrong data and cannot be correct
I will not fix this directly but move it to staging for manual check

## Issue 6 - Negative score
record: SUB000056 student S0148 has score -10
a score cannot be negative
I will update it to 0 until someone verifies the correct score

## Issue 7 - Contest end time is before start time
record: CT005 ends at 11:00 but starts at 12:00
the times are clearly swapped by mistake
I will swap start and end time to fix this

## Issue 8 - Wrong attendance status
record: A000046 has status 'joined'
valid values are Present, Absent or Late
joined most likely means the student was present
I will change it to 'Present'

## Issue 9 - Wrong regrade request status
records: many regrade requests have status 'open', 'closed' or 'done'
these are not valid values in our system
open means not resolved yet so I will change to 'pending'
closed means rejected so I will change to 'rejected'
done means resolved so I will change to 'approved'

## Issue 10 - Wrong plagiarism flag status
records: many flags have status 'new', 'cleared' or 'reviewing'
new means just created so I will change to 'pending'
cleared means no plagiarism found so I will change to 'dismissed'
reviewing means still checking so I will change to 'pending'

## Issue 11 - Similarity score out of range
record: PF0015 has similarity score 125.0
score should be between 0 and 1 only
this is clearly wrong data
I will move it to staging for manual check

## Issue 12 - Wrong enrollment status
record: E00042 has status 'ongoing'
valid values are active, dropped or completed
ongoing means currently studying so I will change to 'active'

## Issue 13 - Missing or invalid email
record: S0005 Ayaan Gupta has empty email
record: S0018 Anika Patel has email without @ symbol
record: S0077 Nisha Chatterjee has empty email
these need correct email addresses
I cannot guess the correct email so I will flag for manual verification

## Issue 14 - Duplicate enrollment
record: S0001 is enrolled in C006 two times
only one enrollment record should exist per student per course
I will delete the duplicate row

## Issue 15 - Orphan records
record: SUB000013 has student S9999 who does not exist
record: SUB000038 has problem P9999 which does not exist
record: E00718 has student S9999 who does not exist
record: E00719 has course C999 which does not exist
record: A000018 and others have student S9999 who does not exist
record: A000032 has session SES9999 which does not exist
these records have no parent record so they are invalid
I will move them all to a staging table for review
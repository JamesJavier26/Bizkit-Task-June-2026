The double-booking bug happened because the overlap check only verified whether the new booking's start date fell within an existing booking, missing other overlap scenarios such as a booking that completely contains an existing one. The overlap logic was changed to return not (end_a < start_b or end_b < start_a), which correctly detects all overlapping date ranges by only allowing bookings when one range ends before the other begins.

For the double-booking bug (Task 1), the original code allowed me to book from january 1 to january 30 and now it will not be allowed.

I used Github Copilot to help me sove some of the tasks. I tested multiple times before committing the fix and ensured that the output is correct.
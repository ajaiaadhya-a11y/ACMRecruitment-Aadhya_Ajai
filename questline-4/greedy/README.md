# Initial thought process
This program uses notes of denominations 5 and 10 to give balance
# Algorithm used for each bill
we take each bill through iteration from the list and check for five rupees and ten rupees notes
$5 Bill: No change required. Increment $5 count.
$10 Bill: Requires $5 change. Decrement $5 count by 1, increment $10 count by 1.
$20 Bill: Requires $15 change.
     Prefer giving one $10 bill + one $5 bill. If not available, fall back to three $5 bills.
If at any point we cannot give the required change, return false. If we finish processing all customers, return true.
# Time complexity 
We iterate through the array once in linear time
# Space complexity 
we only use two integer counters

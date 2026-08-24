# LEMONADE CHANGE CODE
Since leetcode doesn't have user to input, the code must be written inside a Class method.
We should then define the function and pass the input list directly into the function arguments as a parameter (named bills)
We then initialise 2 variables: five = 0 and ten = 0.
We only track $5 and $10 bills. $20 bills are useless for giving change, so we never need to count them.

Customer Logic Loop
Customer pays $5 (bill == 5): No change required. Increment five += 1.
Customer pays $10 (bill == 10): Requires $5 change.
If five == 0, return False immediately (cannot make change).
Otherwise, give one $5 bill (five -= 1) and keep the $10 bill (ten += 1).
Customer pays $20 (bill == 20): Requires $15 change.
Greedy Choice 1: Try to give one $10 bill + one $5 bill (ten > 0 and five > 0).
Greedy Choice 2: If no $10 bill is available, give three $5 bills (five >= 3).
If neither combination is available, return False.

Why the Greedy Choice Works

$5 bills are more flexible than $10 bills because $5 bills can be used to make change for both $10 and $20 purchases. Holding onto $5 bills for as long as possible by using up $10 bills first guarantees maximum flexibility for future customers.

If the loop finishes without failing, returning True confirms every customer received change.

# ASSIGN COOKIES CODE
g.sort() and s.sort(): Sorts both the greed factors (g) and cookie sizes (s) in ascending order (smallest to largest). Sorting allows us to match the smallest available cookie to the child with the smallest greed factor.

Pointers and Counter

child: Pointer tracking our position in the children array g.

cookie: Pointer tracking our position in the cookie array s.

content: Counter for total satisfied children.

Two-Pointer Traversal Loop

while child < len(g) and cookie < len(s): Traverses both lists until we run out of children or cookies.

If s[cookie] >= g[child]: The current cookie is big enough to satisfy the current child.

Increment content += 1 (child satisfied).

Move child += 1 to check the next child.

Move cookie += 1 since this cookie is now used.

Else (s[cookie] < g[child]): The cookie is too small for the current child.

Only move cookie += 1 to try the next, larger cookie. (The child stays at the same position waiting for a bigger cookie).

Why the Greedy Choice Works
Giving the smallest valid cookie to the least demanding child leaves the largest cookies available for children with larger greed factors later in the arrays.

Finally, return content yields the total count of satisfied children.

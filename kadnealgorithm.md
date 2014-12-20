dp[i] -> max value from first position to i
For each position:
dp[i] = max(dp[i - 1] + Number[i], 0) // This is max_ending_here
maxsingleelement = max(maxsingleelement, Number[i]) // Check case all negative values.
Then we will get our solution taking the max dp[i]
For each position again:
sol = max(sol, dp[i]) // This is max_so_far
This implementation has O(n) in time complexity and memory usage.
Then we can use only two variables in the solution you gave us. The complexity will be the same but memory usage will be constant .
By the way, what happen when all the elements are negative values? This is a possible case. Based in this case I like to use a variable (maxsingleelement) that stores the max value from each Number[i]. At the end, if this value is lower than 0 then I return maxsingleelement otherwise return sol (max_so_far)



o have it return  - 1 (i.e. the least negative element) instead, u can initialize max_so_far to  - ∞ instead of 0.

### Coding Challenge

**Part 1**

Assumptions - There's only single pair in the given data (list) that sums upto the target number (2020).

**Answer**: Product - 514579. In this case, the product seems to be the LCM of the two numbers which sum up to 2020 as both numbers are co-prime.

**Part 2**

Assumptions - There's only single triplet in the given data (list) that sums upto the target number (2020).

**Answer**: Product - 158661360 (201, 715, 1104)


### Case Study

**Part 1**

**1. Assumption - Bidding events are sequential for given bid prices**

1. If bidding events are sequential (i.e total events as cummultive sum of all previous events observed till the current bid price), and we observe losses given bid price for n events and then m wins for the same bid price, and then shift to next higher bid price. In this case, we should observe win rate w.r.t overall events that were recorded up until current bid price
2. In that case, bid prices $0.1 and $0.4 have the highest odds of 0.415, but in a bidding scenario higher bid has more chances of winning even with same win rate. Also, the number of wins corresponding to $0.4 is more than that for $0.1 from the given data which means we start losing auctions with $0.1 more early even with the same win rate. 
3. So, the optimal price to bid is **$0.4**, because higher bid price, higher chances of winning in an auction scenario as compared to $0.1

- **Answer** - Expected win rates for each bid price is given in column **total_win_rate** of the above dataframe, (win_rate.csv) file.


**2. Assumption - Bidding events are independent for given bid prices**

1. If events are independent w.r.t to each bid price, then bidding should be done with bid price of highest win rate (4) i.e $5, ignoring $9 because only 1 event

- **Answer** - Expected win rates for each bid price is given in column **win_rate** of the above dataframe.

Win rate table: https://docs.google.com/spreadsheets/d/1-wqicoev9g2ZNMFvFf6ty4IGt31Z3FqRzfSx5ddkAfQ/edit?usp=sharing


**Part 2**

1. From the above stats, we can see that although $0.4 has higher chances of winning but the the number of wins and the total revenue generated is more with bid price of $0.2.
2. This is because the numner of wins for $0.2 are far more than that of $0.4, the publisher might be more interested in paying $0.2 than $0.4 in an ideal scenario based on total number of wins. 

**Answer - $0.2 should be the optimal bid price for maximizing revenue.**
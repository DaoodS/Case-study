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

- **Answer** - Expected win rates for each bid price is given in column **total_win_rate** of the above dataframe


**2. Assumption - Bidding events are independent for given bid prices**

1. If events are independent w.r.t to each bid price, then bidding should be done with bid price of highest win rate (4) i.e $5, ignoring $9 because only 1 event

- **Answer** - Expected win rates for each bid price is given in column **win_rate** of the above dataframe.

**app	bid_price	win	events	total_events	total_win_rate	total_odds	total_events_per_bid	win_rate	odds**
0	A	0.01	0	100000	100000	        1.000	        0.000000	100000	                1.0	        0.000000
1	A	0.01	1	0	    100000	        0.000	        0.000000	100000	                0.0	        0.000000
2	A	0.10	0	7000	107000	        0.065	        0.000000	10000	                0.7	        0.000000
3	A	0.10	1	3000	110000	        0.027	        0.415385	10000	                0.3	        0.428571
4	A	0.20	0	8000000	8110000	        0.986	        0.000000	10000000	            0.8	        0.000000
5	A	0.20	1	2000000	10110000	    0.198	        0.200811	10000000	            0.2	        0.250000
6	A	0.40	0	700000	10810000	    0.065	        0.000000	1000000	                0.7	        0.000000
7	A	0.40	1	300000	11110000	    0.027	        0.415385	1000000	                0.3	        0.428571
8	A	0.50	0	80000	11190000	    0.007	        0.000000	100000	                0.8	        0.000000
9	A	0.50	1	20000	11210000	    0.002	        0.285714	100000	                0.2	        0.250000
10	A	0.75	0	7000	11217000	    0.001	        0.000000	10000	                0.7	        0.000000
11	A	0.75	1	3000	11220000	    0.000	        0.000000	10000	                0.3	        0.428571
12	A	1.00	0	400	    11220400	    0.000	        0.000000	1000	                0.4	        0.000000
13	A	1.00	1	600	    11221000	    0.000	        0.000000	1000	                0.6	        1.500000
14	A	2.00	0	30	    11221030	    0.000	        0.000000	100	                    0.3	        0.000000
15	A	2.00	1	70	    11221100	    0.000	        0.000000	100	                    0.7	        2.333333
16	A	5.00	0	2	    11221102	    0.000	        0.000000	10	                    0.2	        0.000000
17	A	5.00	1	8	    11221110	    0.000	        0.000000	10	                    0.8	        4.000000
18	A	9.00	0	0	    11221110	    0.000	        0.000000	1	                    0.0	        0.000000
19	A	9.00	1	1	    11221111	    0.000	        0.000000	1	                    1.0	        inf



**Part 2**

1. From the above stats, we can see that although $0.4 has higher chances of winning but the the number of wins and the total revenue generated is more with bid price of $0.2.
2. This is because the numner of wins for $0.2 are far more than that of $0.4, the publisher might be more interested in paying $0.2 than $0.4 in an ideal scenario based on total number of wins. 

**Answer - $0.2 should be the optimal bid price for maximizing revenue.**
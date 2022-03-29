# knapsack_dp
    01 knapsack dealing with dynamic programming algorithm

# pseudocode
    1.
    C[i][k]: item 1~i且負重k下的最大獲利
    for k = 0 ~ w
        C[0,k] = 0
    for i = 1 ~ n
    	C[i,0] = 0
        for k = 1 ~ W
	    if(W[i] <= k): #拿得動item i
	        if(V[i] + C[i-1,k-w[i]] >= C[i-1,k])
		    C[i,k] = V[i]  C[i-1,k-w[i]] #取物品i 用剩下的k-Wi重量 拿1~i-1的item
		else:
		    C[i,k] = C[i-1,k] #不取物品i
            else:
	        C[i,k] = C[i-1,k] #拿不動item i  

    2.
    is_selects: 各物品是否取的list (從結果倒回來推)
    for item i ~ item 1:
        if C[i][k] == C[i-1][k]
            代表item i不用取
        else
            res - item i價值
            w - item i重量
	   
    3. check result is correct or not

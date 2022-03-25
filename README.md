C[i][k]: item 1~i且負重k下的最大獲利

C[i][k] = { 0 ,if i=0 or k=0
	    C[i-1][k], if k < Wi               #拿不動物品i
	    max { C[i-1][k]         , if k>=Wi #不取物品i
		  Vi + C[i-1][k-Wi]            #取物品i 用剩下的k-Wi重量 拿1~i-1的item

is_selects: 各物品是否取的list (從結果倒回來推)
for item i ~ item 1:
    if C[i][k] == C[i-1][k]
        代表item i不用取
    else
        res - item i價值
        w - item i重量

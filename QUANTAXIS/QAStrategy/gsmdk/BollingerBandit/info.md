##布林强盗系统

策略介绍：

布林强盗交易系统是一个中长线策略（本例假想的使用周期是日线），将采用后者的规则，
价格超过50日移动平均线上方1个标准差作为买进信号的标准，跌破50日移动平均线下方1个
标准差作为卖出信号的标准（主体交易条件）。

持有头寸的时间每多一天，计算移动平均线的天数减一。持有头寸时间越长，我们越容易带
着利润离场。计算移动平均线的天数最小可以递减到10。如果达到10，则不再递减。除了主
条件，次交易为如果持多仓，移动平均低于上轨发出平仓信号；加入这个离场条件是为了
防止布林强盗系统在止损之后重复入场。如果我们不使用这个离场条件，当移动平均在
上轨上方时，多头入场条件仍然成立，因此多头头寸将会建立。

策略逻辑： 

入场条件：
     当前价格突破布林带上轨，收盘价大于之前第30个交易日的收盘价；
     boll bandit周期的均价大于下轨且当前价格小于均价；
     
出场条件：
     当前价格低于之前第30个交易日的close，且低于了下轨；
     boll bandit周期的均价低于下轨且当前价格小于均价；

# Efficiently Inefficient 读书笔记

[TOC]



## Chapter 2 Evaluating Trading Strategies

### Alpha and Beta

regression to benchmark.

significance of $\alpha$ : t-statistic

*market neutral*: $\beta = 0$

to make a strategy market neutral, $\beta$ gives the *hedge ratio*.

### Risk—Reward Ratios

Sharpe Ratio
$$
SR = \frac{E(R - R_f)}{\sigma(R-R_f)}
$$
usually not used for strategies that have <u>skewed returns and crash risk</u>

Information Ratio
$$
IR = \frac{\alpha}{\sigma(\varepsilon)}
$$
where 
$$
R_t = \alpha + \beta R^b_t + \varepsilon_t
$$
if the hedge fund have a specific benchmark, IR is simply computed as
$$
IR_{benchmared} = \frac{E(R - R^b)}{\sigma(R - R^b)}
$$
ie. extent to which beats the benchmark / tracking error

We should always use annualized measurement since
$$
SR^{annualized} = SR \times \sqrt n
$$
as we increase the measurement frequency $n$, we decreased the measured SR.

### Stale-Price

Suppose a strategy completly clone benchmark but delay report for one period, then regress $R_t$ on $R^b_{t-1}$ appears to have zero beta, this is *stale-price problem*

Solution: regress also to lagged periods,
$$
R_t = \alpha^{adjust} + \beta^0 R^M_t + \beta^1 R^M_{t-1} + \cdots + \beta^L R^M_{t-L} + \varepsilon_t
$$
we can estimate the "true" all-in beta as
$$
\beta^{all-in} = \beta^0 + \beta^1 + \cdots + \beta^L
$$
and the adjusted IR is
$$
IR^{adjust} = \frac{\alpha^{adjust}}{\sigma(\varepsilon)}
$$


## Chapter 3 Finding and Backtesting Strategies

### Finding Strategies

Understand who is taking the other side of your trade and why

> If you don't know who the sucker is, it's you

Two main sources of repeatable profits:

- compensation for Liquidity Risk
- Information Advantages

#### Information perspective

- Production of information: fundamental analysis
- Access to information
- Behavioral finance and the limit of arbitrage. Fundamental risk and noise trader risk.

#### Market Liquidity Risk

liquidity-adjusted CAPM.

> Don't catching a falling knife

premiums earned by fix-income arbitrage hedges funds: buy cheap liquid security and short-sell a corresponding liquid security, earning a spread as compensation for market liquidity risk.

Market Making is another form to earn market liquidity risk premium.

#### Funding Liquidity Risk

margin CAPM

Another implication: many investor prefer to buy risky securities over applying leverage to safer securities.

#### Providing Liquidity to Demand Pressure

A *contrarian trading* become profitable and providing liquidity by buying low and selling high.

demand pressure may come form

- corporate event
- some investors want to hedge risk
- institutional frictions such as some investor face inevstment constraints
- behavioral biases

### Backtesting Strategies

two kinds of strategy:

- portfolio rebalance rule
- enter—exit rule

data mining and biases

- biased universe
- announcement time
- over-optimized parameter

#### equivalence of portfolios and regressions

分层法（多空零投资组合）和回归法之间的关系

- A time series regression corresponds to market timing strategy
- A cross-sectional regression corresponds to security selection strategy
- A univariate regression correspond to sorting securities by one signal; a bivariate regression corresponds to double-sorting securities by two signals, <u>allowing you to determine whether one signal add value beyond the other</u>.

回归法可以方便的添加更多变量，而组合法 multi-sorting 随着变量的增加会越来越复杂。



## Chapter 4 Portfolio Construction and Risk Management

### Portfolio Construction

general principles:

- diversification
- position limits. Control the risk of being blown up by a single position
- make larger bet on higher convinction trades
- think of the size of bet in terms of its risk
- correlations matter
- dynamically resize postions acording to risk and conviction

quantatitive portfolio optimization problem:
$$
\max_{x} x^\prime E(R) - \frac{\gamma}{2} x^\prime \Omega x
$$
FOC:
$$
 0 = E(R) - \gamma \Omega x
$$
which gives the optimal portfolio:
$$
x = \gamma^{-1} \Omega^{-1} E(R)
$$
this result implys that, optimal portfolio is characterized by <u>taking large postions for securities with large expected returns, low variance, and low correlation to other postions</u>

### Risk Management

#### Measure of Risk

Volatility. Not capture well the crash risk

VaR. Capture tail risk.
$$
Pr(loss > $10 millon) = 1\%
$$
ES, expected shortfall, the expected loss given already lose more than VaR 
$$
ES = E(loss | loss > VaR)
$$
Stress Loss. By performing stress test.

#### Risk Management: Perspective Risk Control

diversification, risk limits and position limits, liquidity management, tail hedging via options, etc.

#### Reactive Risk Control: Drawdown Control

$$
VaR_t \leq MADD - DD_t 
$$

Why most traders selling near the bottom? Because this **defines** the bottom. When selling is over, price start rebounding.

> As a trader, never panic, but if you are going to panic, panic first.

> the strongest weak hand suffers the largest loss

Leveraged hedged funds are weak in the sense that they are easily hit margin requirement. The weak hands that "panic first"  suffer lower losses than the "strongest weak hands", which are forced to sell at the bottom.



## Chapter 5 Trading and Financing a Strategy — Market and Funding Liquidity

这一章讨论的是从 paper-trading 到 trading in real world 这个过程中要考虑的两个重要问题：

- 5.1 ~ 5.5 Transaction Cost.  即章节副标题中的 Market Liquidity
- 5.6 ~ 5.11 Funding Liquidity and Leverage

何谓 Market Liquidity, Funding Liquidity?

- Securities with high transaction costs are said to be *iliquid*. 
- Securities with episodic spikes in TC are said to have a lot of *market liquidity risk*;
- leverage is associate with *funding liquidity risk*, that is, the risk that trader cannot continue to finance his positions and forced to liquidate in a fire sale.

### Transaction Cost

TC包含两个部分：(increasing TC) market impact  + (const TC)  Bid—Ask Spread. (Decreasing TC: OTC)

Three measurement of TC:

- $TC = P^{execution} - P^{befroe}$
- $TC = P^{execution} - P^{after}$
- $TC = P^{execution} - P^{VWAP}$

estimating expected TC: 

- trade size
- security characteristics: volatility, daily traidng volume, shares outstanding, floating shares
- market conditions: bid—ask spread, depth of limit order book

#### Implementation Shortfall: the cost of trading and not trading

definition:  IS = TC + OC 

calculation: TC is known, and 

IS = performance of paper portfolio - performance of live portfolio

This spearation is used to analysis whether we are <u>trading too quickly or too slowly ?</u>

- strategy in illiquid market we have high TC, implying you optimally trade slowly.
- strategy with <u>large alpha decay</u> have high OC, implying you optimally trade fast.

#### capacity of a strategy or an asset manager

(Fig 5.3)

Since either paper return or marginal shortfall increasesl as AUM increases, total dolla profit of eventually start to fall when AUM is too large.

### Funding Liquidity Risk and Leverage

To avoid being forced into a fire sale: 

- lock-up provisions
- redemption notice periods
- gates or side pockets. May create a "run" on hedge fund. <u>Having a gate make it more likely that the fund will need it</u>

#### Funding Liquidity Risk and Gambler's Ruin

*gambler's ruin*: the risk that you end up bankrupt despite having the odds in your favors.

In investments, you may have edge (alpha) but limited capital with leverage subject to margin requirements, this risk is reffered to as *funding liquidity risk*

Moreover, <u>when a hedged fund is forced to unwind its postions, it tends to be at a time when investment opportunities are **particularly** good.</u>  Especially in *liquidity spiral*

#### Liquidity Spiral: When Everyone Runs For the Exit

1. start: some kind of shock cause leveraged traders to lose money
2. increase margin requirement, forcing deleverage positions , risk management push to reducing portions, redemptions, etc.
3. second round of selling ….

It's an example of <u>crash risk</u> that is difficult to detect during normal trading days: <u>While price changes are driven by fundamental news on normal days, price changes are driven by forced selling during liquidity spirals.</u>

Liquidity spirals also change correlations across securities. During liquidity event, price starts to co-move. Liquidity crisis is contagious since losses in one market can lead to fire sales in other markets. 

(Fig 5.7 Spillover at the beginning of global financial crisis in 2008)

*predatory trading*: trading that exploits or in fact induces a liquidity spiral. 

Other kind of predatory trading is just to prevent themselves to be the next one forced to liquidate.



## Chapter 6 Intorduction to Equity Valuation and Investing

这一part讲的股票策略，特指选股策略。

- Chapter 7 主观股票策略（多空or纯多头）
- Chapter 8 股票做空策略
- Chapter 9 量化股票策略

价值投资（value investing）的基本方法就是找“便宜货”，即市场价格低于内在价值的股票。价值投资的两个风险：fundamental risk & liquidity risk，因为存在这两个风险，要考虑安全边际（margin of safety）。

几种估值方法

- Dividend Discount Model
  - 基本的股利贴现模型需要预测所有未来$t$期的股利$D_t$
  - Gordon's Growth Model 假设股利增长率为常数
  - Multi-Stage Dividend Discount Model 假设公司经历一段时间的高增长，然后达到一个新的价值$P_{t+T}$
- Earnings, Book Values and Residual Income Model
- 相对估值，eg. P = E * P/E, 其中 E使用该公司的Earnings, P/E采用同行业类似公司的



## Chapter 7 Discretionary Equity Investing

主观投资的方法：

- analyzing a firm's business and its future profit potential
- considering managment's 
  - ability to deliver this potential and 
  - its integrity to pay the profits to shareholders
- valuing the firm in relation to its price

简单地说就是：首先看一家公司的商业模式（怎么赚钱的）、盈利潜力；然后看这个公司的管理层，一看他们的能力（能不能按照这个模式赚到钱），二看他们的integrity（赚到钱了分给股东多少，是最大化股东利益还是最大化管理层自己的利益）；最后看估值，也就是看我们以上的这些分析是不是已经price-in了。

### Value Investing

价值投资的基本idea是： buying securities that appear cheap。这里最大的坑是，一只股票之所以看起来便宜，总是有某些uncomfortable的原因的，书中举了一个最典型例子：跌破book-value的股票是否值得买？答案是不一定，它可能是因为管理层会waste cash，因此shareholders是得不到好处的。

#### Fundamental Analysis

核心是估值，但所有的估值模型都要有input，估计这些input的过程就是fundamental analysis

- focusing on numbers: 看财务报表
- focusing on people：管理层、雇员、客户、供货商、竞争者
- focusing on industry dynamics: 分析行业动态（行业研究）
- bet on entire industry: 行业轮动

#### Margin of Safety

Robustness of valuation. Or, sensitivity of estimated intrinsic value to its inputs.

#### Value Trap

Does the stock look cheap because it *is* cheap or because it *deserves* to be cheap? Or, does the stock appear to be cheap only because its true fundamentals are collapsing? eg. low P/B driven by falling book-value.

How to mitigate value trap? focusing on quality characteristics.

### Quality Investing & Quality at a Reasonable Price

according to Asness, Frazzini and Pedersen (2013), four components: growth, profitability, safety and payout ratio

#### growth vs. growth trap

stocks offering a growth dream and little current profitability can be skeptical and overvalued if investors project growth too far into future.

 A growth firm is a good investment only when its growth is <u>not fully reflected in market price</u> 

growth is <u>*sustainable* growth in *profit*</u>. Examples of bad growth:

- assets growth driven by empire-building manager
- sales growth driven by low product price
- temporarily improving accounting numbers using accounting tricks

#### profitability and earnings quality

"earnings quality": how reasonable a company's accounting practices are.

- more or less aggressive in moving items off the balance sheet
- pushing expenses into future
- recognizing revenues early using so-call accruals

#### safety

- standard return-based measure: market beta, total return volatility or idiosyncratic volatility
- fundamental risk measure: e.g. past variation in profitability 

#### payout and management quality

how shareholder-frendly the firm is and how well mannaged it is. Does the firem's management seek to maximize shareholder's value or to extract private benefits for itself ?

But stocks that are cheap due to poor management and then profit from improving it - *activist investing*

#### quality at reasonable price

(figure: worldview of bargain hunter and growth investers)

 *GARP investing*: buying growing firms that are cheap relative to the expected growth which is called "growth at a reasonable price" investing. This concept can be generalized to "quality at a reasonable price" investing,  or *QARP investing* 

### Holding periods and Catalysts

- Gererally holding for long term. Warren Buffet sometimes take this idea to extreme seeking an infinite holding period
- sell a stock when convered to its fair value or become expensive. *Don't get married to your position*
- value-and-catalyst investor.
- create a catalyst



## Chapter 8 Dedicated Short Bias

### how short-selling work and why it can be difficult

1. 卖空所得的cash不能用于买其他securities，另外还需要一笔保证金
2. loan fee. rebate rate 一般来说是低于货币市场利率的，这中间的价差就是借出security的收益。一般来说 loan fee 都比较低，因为一手股票可以多次借出。securites lending market 受其自身的供求关系影响。
3. recall risk. 融券到期时，价格没有如愿跌到一定程度，而借出方又不展期。
4. short squeeze. 卖空证券多数是保证金交易，当价格上升时，可能会产生踩踏行情。<u>保证金交易下，做多和做空是不对等的，因为保证金是按照价格的一定比例在收取的。如果做多而价格跌了，除了逐日盯市结算损失之外，所需要的维持保证金是下降的；如果做空而价格上涨，除了逐日盯市结算损失之外，需要的维持保证金是增加的，做空者还要支付增加的这一部分保证金。</u>

### Short sale frictions mean that companies can be overvalued

short sale frictions makes it harder to express negative views => negtive views not reflected in prices, stocks being overvalued.

<u>investors focusing on forecasting the forecast of others</u> is called *Keynesian Beauty Contest*. Investors focus on what the stock price will be tomorrow—dirven by the average opinion of **buyers** tomorrow—rather than the long-term intrinsic value. 

#### speculative bubbles: an example

Suppose short selling is impossible and that price is always set by the most optimistic investors.

Miller(1977) discusses how short sale frictions can lead to overvaluation.

#### loan fees and stock valuation in an efficiently inefficient market

The short sellers's cost of borrowing a share is a source of income for the optimistic owner of the stock who lends it out. For stocks with significant divergence of opinions, prices and loan fees may both be very high.

#### empirical evidence on return of highly shorted stocks

(Empirical evidence) Stocks with high short interest have low subsequent return. Stock with high lending fees have low future return. Short sellers can identify misbehavior by firms

—consistent with the idea that short sellers can identify overvalued stocks, which subsequently fall in price.

### Firms vs. Shrot Sellers: Is Short-selling Good or Bad for Society?

- management do not like short sellers. They can take actions to make short-selling difficult: stock splits and distributions specifically designed to disrupt short-selling or coordinate with shareholders to withdraw shares from lending market.
- short selling make market more efficient by allowing both positive and negative opinions to be expressed, protecting investor from buying a worthless paper marketed by a malicious firm.
- short-selling may kill a firm that would otherwise be in good shape. eg. more difficult to issue share or borrow. Particular for bank stocks, it may create a bank run. So many country imply a temporary short sale ban of financial stocks during crisis. 

### Case Study: Enron

James Chanos 做空安然的几个理由 & 时间表（对 US. SEC 的说法）：

1. 1999-10: 安然使用的"gain-on-sale"的会计做法（大概就是把未来的预期收益提前确认到现在）是值得怀疑的，这会使得利润看起来非常高。即便在这么 aggressive 的会计做法下，它的 captital return 仍然低于 cost of capitial。
2. 2000 10-Qs: 看不懂的关联交易；高管正在卖出自己公司的股票。
3. 2000 10-K & 2001 10-Q：高管离职&高管继续卖出股票；大量一次性收益；仍然有可疑的关联交易。
4. <u>从2000年11月起Channos开始做空安然股票</u>
5. 2001夏：电力和能源特别是天然气价格下跌
6. 2001年8月：CEO辞职。<u>这时他们加大了空头仓位。</u>
7. <u>2001年12月安然宣布破产。</u>

### Interview with James Chanos

Q: 做空一个股票的步骤，从idea到实施？

A: 首先看能不能借到，如果借不到那就算了。然后分析多头的观点，找多头聊天，让他们反驳自己。最后内部讨论后由 senior partners 做决定。

Q: 决定是否做空的key numbers or red flags ?

A: eg. low return on capital with high growth like Enron, insider selling and departures, and

> If you can't understand the disclosures, usually there's a reason for that.

Q: 怎么确定负面消息是否已经反映在价格中了？

A: Good question. We don't know, it's a judgement call.

Q: 一个做空失败的例子？

A: 1996年做空America Online. 做空原因是有一笔巨大的write-off，说明它们从来都没盈利过、也不看好接下来的盈利前景。结果低估了互联网和狂热的力量，还好仓位不重损失比较少。得到的经验是要控制好仓位。

Q: 怎么控制风险的？

A: size the positon based on <u>volatility, borrow, and industry exposure</u>. 单个position不超过基金的5%。从不用杠杆。



## Chapter 9  Quantitative Equity Investing

### 9.1 Fundamental quantitative Investing

#### Value

book-to-market, earnings-to-price, dividends-to-price, cash flows-to-price, etc.

historically (US equity, 1926 ~ 2010) HML got 0.4 of sharpe (4.6% / 12.3%)

value-based portfolio losses if

1. cheap stocks get cheaper and expensive stocks get more expensive, or
2. "cheap" stocks turn out not to be cheap relative to their deteriorating fundamentals

#### Momentum

momentum == "catalyst"

value + momentum == cheap stock on the raise

#### Quality

buys "good" stocks that deserve higher-than-normal price and short-sells "bad" stocks that deserve to be cheap.

value + quality == "quality at reasonable price"

value + momentum + quality == buy raising stock that are cheap relative to quality and shorts falling stocks that are expensive.

#### Betting against Beta and Low-Risk Investing

empirically security market line is more flat than CAPM, due to leverage constraints.

Investors with leverage constraints pick up higher return by buying risky assets rather than leveraging safety assets ==> higher price ==> lower return

measurement of BAB factor: low beta, total volatility, idiosyncratic volatility, earnings volatility, etc.

may overweight non-cyclical insdustries. BAB factor should constructed within industries

#### Quant Portfolio Construction

- diversification eliminates idiosyncratic risk
- market neutral (both dollar and beta neutral)
- industry-neutral
- leaving the factor exposure that we really want to bet on.

#### Quant Event of 2007

<u>liquidity event</u>

What to do? depends on leverage of the fund, financing of leverage (margin requirement), and risk , size and liquidity of the portfolio.

### 9.2 Statistical Arbitrage

- dual-listed shares
- multiple share classes
- pairs trading (statistical) and *residual reversal* strategy
- Index arbitrage

### 9.3 High-Frequency Trading: Efficiently Inefficient Market Making

1. market making
2. stat arb
3. hit stale limit orders
4. identify large orders

#### market making

Market makers provide a service namely liquidity, or immediacy.

Market makers charge a price for this service, it's the transaction cost of natural buyers and natural sellers.

They constantly update the estimation of the equilibrium price, place new limit orders and cancel stale limit orders.



## Chapter 10  Introduction to Asset Allocation

宏观投资的两个部分：

1. 长期: stratigic asset allocation，类似于一种benchmark allocation
2. 短期: tactical asset allocation or market timing，在长期的基础上做一些调整

为什么长期资产配置要分散化于不同的大类资产？因为每种资产背后的premium或者说风险来源都不一样：

- equity: equity risk premium. 


- government bond: term premuim.  
- corporate bond: credit risk premium 
- illiquid and real assets: liquidity premium 

长期大类资产配置的几种方式：

1. 权重=各个资产本身的总市值。无需rebalance，交易次数少。"macro consistent".
2. 权重=常数。eg. 股债60/40。价格变动会引起rebalance，实际上会卖掉上涨的资产，买入下跌的资产。
3. 基于流动性。depends on redemption notice period.
4. 基于风险。权重=各个资产风险的倒数，更进一步可以考虑资产间的相关性。为什么会有这种方式？股债6/4 porfolio的风险完全是dominated by equity，实际上并没有分散风险。风险平价的分配方式才真正实现的分散风险的目的。风险平价的分配方式会将更大的权重赋予低风险资产，那么怎么达到目标expected return? leverage. 但是实际上有些人是leverage-avrese的，有些机构是面临leverage-constraints, 从这个角度看 traditional equity-dominanted asset allocation is efficiently inefficient.

短期战略性资产配置与择时：

找择时指标。数学方法就是回归和回测。书中的例子是用 dividend yield 作为 equity market 的择时指标。

### 主要资产类别的收益来源

#### Equity Returns

dividend yield + capital appreciation

按书中模型的idea，收益来源大概就是公司的earnings以及未来earnings的预期。

#### Bond Returns

yield + capital appreciation due to yield change , ie. duration * delta YTM

这里的应该是单指无风险的政府债券，收益来源包括持有债券时的 coupon yield 以及债券价格的变化（即市场收益率的变化）。风险来源其实就是利率变动风险。

#### Credit Returns

公司债同时包含利率风险和信用风险，获得一个 pure credit return 的方法是 long corporate bond and short government bond of the same duration，这种方法构建的组合收益率就是所谓的信用利差 credit spread。

#### Currency Returns

currency return = carry + currency appreciation 

其中 currency appreciation 长期来看与两国的通胀and/or预期通胀有关。



## Chapter 11 Global Macro Investing

### Carry Trades

long currency with high inserest rate financed by short-selling currency with low instrest rate.

最主要的风险是汇率风险，但可以在外汇市场上对冲。

收益分布是左偏的。这个策略的模式是 selling lottery.

> Carry trade goes up by stairs and down by elevator.

收益分布的左尾巴上有一个小的凸起，这个凸起反映了 carry trade 的汇率风险的一个特征：高carry货币贬值经常是一起贬值，使得diversification失效，称为 "carry-trade unwinds".

广义的carry定义: ammount you will earn if prices stay the same.

广义的 carry 策略: investing in securities with high carry while short-selling securities with low carry.

- currency carry trade
- bond carry trade.  Long bonds in country with high carry while short bonds in county with low carry.
- yield-curve carry trade.  Trade on yield curve.
- commodity carry trade.
- equity carry trade. The carry of equity is its dividend yield. It is closely related to valuation.
- credit carry trade. Earn credit spread, exporse to credit risk.

### Central Bank Monitoring

全球宏观策略关注各国央行的动作，而要理解或预测央行下一步的动作，先要理解各国央行的政策目标和政策限制

各国央行的政策目标：

- US: two objective: inflation and employment. It set interest raty according to Taylor rule.
- European Central Bank: single objective of price stability 
- Countries with a pegged exchange rate: raising interest rate when currency is falling and vice versa.

Then how to trade?  

- simple way: buy or sell bonds or interest rate futures  
- speculate on slope of yeild curve. 因为央行货币政策影响的是短期利率，从而 yield curve 变得平坦or陡峭

一般来说汇率稳定也央行的目标之一，因此央行会让汇率缓慢的移动到新的fundamental上，这个过程中，外汇市场上就会产生趋势

### Trading on Economic Developments

如何定义economic environment? 两个维度：growth and inflation，4种组合

|                            | Strong Growth | Slow growth    |
| -------------------------- | ------------- | -------------- |
| High inflation             | Overheated 过热 | Stagflation 滞胀 |
| Low inflation or deflation | Goldilocks    | Lost decade 萧条 |

每种经济环境下，各大类资产的表现：

- overheated: 
  - 债市：央行加息 => 债券价格下降收益率上升，yield curve 变平坦；
  - 股市：繁荣，因为 1. growth fuels profit 2. inflation does not affect  ==>> real value raise
  - credit: falling credit spread
- Goldilocks:
  - 股、债：not-too-hot and not-too-cold. 
  - Volatility may be falling, lowing option prices
- Stagflation:
  - 股、债： stock suffer due to poor growth and bond suffer due to inflation 
  - commodities, gold, inflation-protected securities : may do well
- lost decade:
  - bond yield likely to fall.

经济状况由总供给和总需求决定，接下来就讨论总供给和总需求的 drivers （复习一下中级宏观）

What drives aggregate supply?

长期：Solow model: Y = A*f(K, L)，技术进步、人口增长、教育、投资

短期：短期供给决定于就业率，而失业率与通胀率负相关，即 Philips curve, 原因在于 sticky nominal wages.

What drives aggregate demand?

跟曼昆的中级宏观那本书里的AD曲线推导逻辑一致：

IS curve + Taylor rule => lower inflation leads to higher aggregate demand

现在把AD和AS放在一起， supply and demand **shocks** determine growth and inflation

总需求和总供给冲击的几种情况：

|                            | Strong Growth                | Slow growth                |
| -------------------------- | :--------------------------- | -------------------------- |
| High inflation             | **总需求扩张** 消费信心增强；央行增发货币、放松信贷 | **总供给收缩** 国际油价上升；资本贬值；效率损失 |
| Low inflation or deflation | **总供给扩张** 国际油价下跌；技术进步；人力资本提高 | **总需求收缩** 消费信心下降；货币紧缩、信贷收紧 |

### Country selection and other global macro trades

#### Value & Momentum

Macro momentum: buying markets that have outperformed while shorting markets that have underperformed

Macro value: buying cheap markets while shorting expensive markets. 

这里 Macro value investment 的关键是显然是怎么定义 "cheap" 和 "expensive". 书上说 it depends on where we thinks the fundamental value is. 那么具体到各类资产，value trade 到底是怎么implement的呢？除了equity market 提供了估值指标这个方法之外，currency market, bond market, commodity market 给出的方法全都是 long-run reversal.

接下来给出了一个Value and Momentum策略在4个市场上的的empirical study，净值曲线基本上都是很漂亮的向上的一条曲线，原因是value用的是比较长期的参数，即value = long-run reversal, 而momentum用的是比较短期的参数，也就是说 value and momentum are not **exactly** opposite

#### Global Trade flow

讨论国际贸易的影响。

进出口对汇率的影响：出口大于进口 => 本币买入增多 => 本币升值压力 

implications of "terms of trade": Dutch desease

#### Political events and regulatory uncertainty 

跟中国市场有关的主要是 1. 监管环境变化 2. 产业政策

### Themetic global macro

主题投资。实际上也是预测某一方面的宏观经济走势，也是赌单边。

eg. 预测中国经济超预期发展 => 做多中国股市、做多中国主要商品进口国的股市、做空债券（如果预期通胀）

感觉这个跟A股概念投资差不多。

### Soros's theory of boom/bust cycles and reflexivity

索罗斯的framework中有两个逻辑是与传统有效市场假说不同的：1. 价格绝大多数情况下是脱离基本面的 2. 更进一步的，价格可以影响基本面。当价格脱离基本面时，市场的feedback要么是 self-correcting 要么是 self-reinforcing，前者会使价格趋向于 equlibrium 而后者会产生 dynamic disequilibrium

我们关注两个方面：一是实际的经济周期(underlying trend that prevals in reality)，二是人们的对应经济周期的看法(misconception relating to the trend)，reality 和 misconception 互相作用，形成了一个繁荣/萧条周期。

一个繁荣/萧条周期的4个阶段：

1. trend in reality and misconception positively reinfroce each other
2. be tested by negative feedback, if survived the test, both will be reinforced
3. misconceptions has been so far from reality, doubts grow and people lose faith
4. a point is reached and trend is reversed

### 对索罗斯的采访

（感觉这个采访索罗斯并没有说出什么实质性的东西，当然问的问题也都是million dollar question）

Q：为什么你对市场情绪、认知偏差、以及监管者和市场参与者的想法如此了解？

A：市场是永远在变化的，我在适应市场的变化这方面特别好

Q：你能说说怎么适应吗

A：我把市场视为不断变化的东西（没正面回答）

Q：你能不能描述一下自己在参与市场中的进化

A：（大概是讲了一段历史）

Q：能不能给个具体的例子，你在一个交易中怎么得到idea并且说服自己

A：（举了08年金融危机的例子，但没说到怎么convince的，都是I fell that, I believe that ..）

Q：（继续追问）How did you get conviction 

A：因为我创立了一个理论，还写了一本书，而且我很早就预测要崩盘了，但时间没预测对（答非所问）

Q：（穷追不舍）那我们怎么知道自己在cycle的哪一点上

A：我也不知道。。。（然后又讲了一堆他的 two funcions 理论）

Q：（接上述回答）所以您的意思就是boom和bust的时候各自用适合的策略的意思呗？

A： 对

Q：那怎么知道什么时候这两个状态会转换？

A：我也不知道。。。我自己在2000年科技股泡沫的时候还亏钱了呢

Q：那你作为investor总得做决定吧，有没有什么signal呢

A：我们正在找。。。

Q：（抛出一个具体的问题）你觉得Greenspan下一步会怎么做

A：it depends, each occasion was different...



## Chapter 12  Managd Futures

为什么CTA策略会流行？

- 历史证明趋势跟踪策略有用：30年58种涵盖各大类资产上的回测
- 与传统大类资产的相关性低，是一个很好的 divsifier

### 趋势跟踪策略的理论基础：life cycle of a trend

(图：life cycle of a trend)

1. Start of trend: initial underreaction
   - 锚定效应。人们会锚定历史数据
   - 处置效应。People tend to sell winners too early and ride losers too long.
   - Non-profit-seeking activies. 前面提到的央行行为、固定比例的长期资产配置方式
   - Frictions and slow moving capital
2. Trend continuation: overreaction
   - 羊群效应和正反馈交易
   - 确认偏误。perple tend to look for information that confirms what they already believe
   - 人们购买基金时会买最近表现好的基金，赎回最近表现不好的基金。
   - 机构风险管理会强制平掉损失过多的仓位。
3. End of trend.

### 实证研究：时间序列动量

这一节是用实证研究来证明：**趋势跟踪策略在较长历史时期内、绝大多数资产类别上都有效**

回测设定：

- 样本时间：1985 ~ 2012，大约30年；标的：股指、商品、债券、货币共58种
- 具体策略：上一期return为正就做多，return为负就做空，时时在场。
- 回看期1，3，12个月，分别代表短中长三种周期
- 周度调仓
- 分别按照资产大类（stock index, currency, bond, commodity）和回看期（1，3，12个月）做组合，另外再将所有的组合在一起。
- 组合权重分配方式为风险平价

研究结论：

- 58个市场中，90%以上都取得了正的收益，夏普比率平均值大概在0.5
- 组合策略中，事前设定的目标波动率和事后realized波动率相差不大（说明波动率的估计是比较准确的？）

### 实证研究：时间序列动量解释了大部分CTA基金的收益

找了5个CTA基金做业绩归因，发现**三种期限时间序列动量解释了这些基金的大部分收益**

- 三个时间序列因子的beta系数全部显著为正
- R2 > 0.5, corr > 0.6
- 只有一家alpha显著为正

### 采访 David Harding

他认为手画k线图有利于增强对数据的感觉，而电脑画图不利于对数据的深入理解：

> When you press a button on your computer and a chart appears, you don’t interact with the data in a very detailed way. Whereas if you draw these graphs day by day by hand, you reflect on the empirical nature of the data more deeply. (It strengthens) my feeling about the non-randomness of the data.	

关于有效市场假说，无情的嘲讽：

> "markets are efficient, and that they perfectly discount all future information". This theory would be laughable if it wasn’t so widely believed in.
>
> To preserve the ridiculous idea of efficient market theory, all surprises would have to be instantaneously discounted, but this is just not possible. The collapse of the banking system unfolded with a sickening series of events over time, so the stock market fell by 50% over the space of a year, and trend-following systems worked well.

使用动量策略的市场参与者的增加会消除趋势还是增强趋势？

> It’d probably change the autocorrelation spectrum of price data.

安利CTA策略好处：

> The best diversi cation you get from investing in a CTA is investing with somebody who doesn’t have a view about the future.

最后灌一碗鸡汤：没有圣杯、没有不变的规律

> There are no  final and immutable truths in financial markets. If you think you’ve found the answer and all you have to do is implement it forever, then you are ultimately doomed. To be competitive, you’ve got to work hard and keep at it and keep going all the time.



## Chapter 13 Introduction to Arbitrage Pricing and Trading

套利策略的风险：

1. 保证金。 require a cash outlay (eg. for margin repuirements)
2. 收敛前会有很大浮亏。 can lead to significant losses before tie converges
3. 套利关系消失。arbitrage link is broken so it never converges

### A general framework

无套利定价法三种方式：

1. if two securities have same payoffs
2. if a protfolio has the same payoff as a security. *replicating portfolio*
3. if a self-financing trading strategy has the same payoff as a security. *dynamic hedging strategy*. rebalanced  over time that do not requiey money in or out of the pocket

In the real world, traders face <u>transaction cost and funding costs</u>. ... we can find upper and lower bound for the value. 

The 3 types are increasingly influenced by <u>frictions</u>: while 1 and 2 involve buy-and-hold strategies, type 3 require dynamic trading.

The strength of arbitrage relation also depends on <u>whether it has a natrueal convergence time.</u> eg. dual-listed companies

### Option arbitrage

#### put-call parity for european options

creat "synthetic" stock with buying call and selling put with same strike price X and putting enough money in bank that yield X at the option expriation time T:
$$
C_t - P_t + \frac{X}{(1 + r_f)^T} = S_t
$$
this is an buy-and-hold trade with a given convergence time, namely the expiration of the options.

One exception: if the stock is difficult to sell short, the RHS can be larger.

#### option arbitrage trading in binomial model

#### arbitrage trading based on implied volatility: BSM formula

According to BSM model: IV of all options on the same underlying stock should be the same.

Exception: IV of OTM put of is higher especial for index options, aka. "smirk", because of potential jumps in stock price.

#### demand-based option pricing

investors pay for the "insurance" than the BSM model implied vol, banks and hedge funds take the other side, making an expected profit, not certain arbitrage profit -- options prices adjust to and efficiently inefficient level.



## Chapter 14 Fixed-Income Arbitrage

> 固定收益套利，就像是在压路机前捡硬币

- trade on the relative alue among fixed-income secureities
- significant amount of leverage.

some examples of fixed-income arbitrage:

- 新券旧券套利。Sell short newly issued *on-the-run* bonds against long positions in older *off-the-run* bonds
- yield curve trades called *butterflies*, swap spread trades, mortgage trades, and fixed-income volatility trades

### 14.1 Fixed-Income Fundamentals

#### bond yield and prices

Given a bond's price P, its *yield to maturity* (YTM) is the internal rate of return **if you hold the bond to maturity**. Conversely, given a bonds's YTM, its price is tht discounted value of the future coupons C and face value F at the discount rate:
$$
P_t = \sum_{t_i} \frac{C}{(1 + YTM)^{t_i-t}} + \frac{F}{(1 + YTM)^{T-t}}
$$

#### the yield curve

sometimes there are several bonds with same maturity but different coupon rates? use *zero-coupon* bond yield

<u>coupon bond can be viewed as a portfolio of zero-coupon bonds</u>

#### bond returns and duration

Why long-term bond price react more to yield change than bond of shorter maturity?

If you hold to maturity, you got the YTM. What if you only hold for a shorter period, eg. t to t+1 ?
$$
\text{bond return}_{t, t+1} = \frac{P_{t+1} + \text{possible coupon}}{P_t} - 1
$$
the bond return changes if and only if its yield changes.

the price sensitivity to yield change is called **duration**, D
$$
D_t = - \frac{\partial P_t}{\partial YTM_t}\frac{1 + YTM}{P_t}
$$
it can be shown that, D equals the weighted mean of remaining time to maturity whose weights are the corresponding cash flow:
$$
D_t = \sum_{t_i}(t_i - t) w_{t_i} \\
w_{t_i} = \frac{\text{cash flow}_{t_i}}{(1 + YTM)^{t - t_i} P_t}
$$
properties of duration:

- zero-coupon bonds: D == maturity
- longer term bonds are more sensitive than shorter term bonds, ie. has greater D

with the definition of D, we compute price change $\Delta P$ on a sudden change in yield $\Delta YTM_t$
$$
\frac{\Delta P_t}{Pt} \cong -\frac{D_t}{1 + YTM_t} \Delta YTM_t = - \bar{D_t} \Delta YTM_t
$$
here we introduct the **modified duration**,  $\bar{D_t} = D_t / (1 + YTM_t)$

we can also use modified duration to write the bond return over ${t, t+1}$
$$
\text{bond return}_{t, t+1} \cong YTM_t - \bar{D_t} (YTM_{t+1} - YTM_t)
$$

#### yield and returns of a leveraged bond

bonds are often leveraged, that is, bought by borrowed money using the bond as collateral.

When borrows against a bond in a *repo transaction*, she must pay an interest rate called the *repo rate*

gov bonds have almost the same repo rate, called *genreal collateral (GC) repo rate*. If a bond is viewed as "particular attractive" then one can borrow (money, using the bond as collateral) at a lower repo rate -- such a bond is called *on special* and the discount in its repo rate is called *specialness*:
$$
\text{repo}_t = GC_t - \text{specialness}_t
$$
A bond's repo rate change over time, and is driven by (1) GC repo rate, which in turn driven by cental bank monetary policy (2) specialness, which due to changes in bond market's liquidity characteristics.

Now the return on a leveraged bond is calcuated as before, subtracting the financing rate:
$$
\text{leveraged bond return}_{t, t+1} \cong YTM_t - repo_t - \bar{D_t}(YTM_{t+1} - YTM_t)
$$

#### Immunization

hedge the risk of <u>changes in the **level** of interest rates, ie. parallel up or down moves in the yield curve.</u>

#### Convexity

to improve the approximation:
$$
\frac{\Delta P_t}{P_t} \cong -\bar{D_t} \Delta YTM_t + \frac{1}{2} \text{convexity}_t (\Delta YTM_t)^2
$$
Convexity is defined as second derivative of bond price to yield changes
$$
\text{convexity}_t = \frac{\partial^2 P_t}{\partial(YTM_t)^2} \frac{1}{P_t}
$$
it can also be written as 
$$
\text{convexity}_t = \sum_{t_i} \frac{(t_i - t)(t_i - t + 1)}{(1 + YTM_t)^2} w_{t_i}
$$
where $w_{t_1}$ is same as above.




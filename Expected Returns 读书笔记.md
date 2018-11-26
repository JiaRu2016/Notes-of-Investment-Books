

[TOC]

# PART 1 Overview, historical returns and academic theories

## C5 Rational theories on expected return determination

## C6 Behavioral finance

### 6.1 Limits to Arbitrage

limits-to-arbitrage literature argue that arbitrage is both risky and costly

市场经常是无效的，因为套利有风险：

- fundamental risk. 基本面发生变化，套利空间不再存在。
- noise trader risk. 虽然你是对的但也有可能被noise traders踩死，尤其是当你 用杠杆或是给别人管钱时。

另外 limits-to-arbitrage literature 还有几个有意思的point

- Risk management systems that make sense for any **one** investor can increase **systemic** risk. Trigger a vicious cycle of position reduction and cause a rush to exit.
- difficulty of beating the market does not necessarily imply that market is efficient.

### 6.2 Psychology

biased beliefs && noncalssical preferences

#### 6.2.1 Biases

##### 6.2.1.1 Heuristic simplifications

Humans have limit attention, memory, and information-processing capacities, then heuristics—rules of thumb or mental shortcuts—evolved to help us select a subset of information that be believed to be most relevant.

###### Attention and memory biases

overweight information that is salient, vivid, attention grabbling, familiar, emotionally hitting, or simply more recent. We also like stories, and understand complex events through simple narratives.

distort our probability and frequency judgments

抓眼球的事件得到更多的关注；喜欢听故事；总想用简单的几句话理解复杂的事情（一张图/几分钟看懂XXX)）；不能正确的评估一件事发生的概率。

###### Representativeness

people rely too much on stereotypes instead of cold probability analysis. ignore sample size and base-rate information. 用书上的例子，即人们过分看重 Pr(stereotype of Librarian|Librarian) 而忽视了 Pr(Librarian)

representativeness 的一个常见表现：see patterns in truly random sequences

Box 6.1 

Seeing five successive tails ...

If believing in fair coin, they think head is due and <u>predict a reversal, to make the sequence more representative.</u> That is *gambler's fallacy*.

However if they do not know the coin is fair, they may  <u>use representativeness to infer an unfair coin and predict a tend</u>

which is true? If true process is salient, reversal error is common, whereas if thre process is unknown, people extrapolate too much.

###### Conservatism

underweight new evidence when updating priors. Anchoring.

Box 6.2 how to reconcile representativeness and conservatism

information has two dimensions: strength and weight (prob)

conservatism aries when evidence has low strength but high weight, whereas representativeness aries when evidence has high strength but low weight.

other literaturel: 人们对显著的、具体的、栩栩如生的故事和极端情况反应过度，而对抽象的统计信息、较远的信息反应不足。相比于一连串逐渐释放的、温和的信息，一个大新闻更可能引起人们的过度反应。

##### 6.2.1.2 Self-deception (overconfidence and limit to learning)

###### Overconfidence

Most feel they are above average

overconfidence typically when predictability is low and evidnece ambiguous, making feedback inconclusive.

overconfidence is one key reason for excessive trading.

overconfident investors overweight private information (data or research made by themselves) and underweight public information

###### Overoptimism

"future will be great, especially for me"

###### Biased self-attribution

People tend to attribute good outcomes to their own abilities and bad outcomes to external circumstances.

###### Confirmation bias

We seek evidence that supports our view and interpret ambigous evidence as supportive.

###### Hindsight bias

making past appear more predictable than it really was. This explains why active management is so popular, despite its poor record.

#### 6.2.2 Preferences

Traditional theory: EU = probability-weighted sum of Utilities of each outcome

PT: max U = w(p1)U(x1) + w(p2)U(x2)

##### Prospect Theory (PT) 

finds of PT:

- people cares about loss and gains (change in wealth) than about overall wealth.
- "reference point" matters, ie. whether a dollar is viewed as gains or loss.
- people exhibit loss aversion but can be risk seeking when facing the possibility of loss. S shape of value funciton. 
- people overweight low-probability events. This explains the simultaneous demand for both lotteries and insurance.

##### Framing Effects

analyzing problem in too isolated a fashion. 

Focus too much on asset-specific risks instead of its contribution to portfolio.

People make different choices depending on hwo a given problem is presented to them. "心理账户"

reference point or benchmark matters. Status quo is a natural benchmark, "dispositon effect"

##### More risk preferences: House money effect

Gamblers tend to become more willing to take risks when they are ahead (playing with house money)

More aggressive risk taking following winning and cautiousness following losses.

One interesting exception: If investors have a chance to fully recover a prior loss, they wil accept gambles that they would normally reject. （德扑河牌圈容易over-bet）

##### Ambiguity aversion

people prefer objective uncertainty ("known unknown") to ambiguity ("unknown unknown").

### 6.3 Applications

#### 6.3.1 Speculative bubbles and other macro-inefficiencies

#### 6.3.2 Cross-secctional trading opportunities and micro-inefficiency

### 6.4 Conclusion



## C7 Alternative interpretations for return predictability

### 7.1 Risk Premia or Market Inefficiency ?

Two main competing explanations of return predictability: time-varying risk premia and market inefficiency.

#### Time-varying risk premia

reflect either asset's changing riskiness or investor's changing risk aversion over time — or both.

buying opportunities tend to be greater in bad times when risk or risk aversion is higher.

Investors who differ from the market by **having longer investment horizon and greater risk tolerance** may be natural risky asset buyers during bad times when valuations are attracive.

这段话大概是这么一个逻辑：risk premia 在不同时期（经济环境下）是不一样的，bad times risk premia 比平时更高，但很多人活不过 bad times，只有那些投资周期长、风险厌恶低的人能活过bad times, 同时他们可以从bad times high risk premia 中获利。Implication: investors who is similar to market是挣不到钱的，只有 investors with longer horizon and greater risk aversion 才能在bad times中收割便宜货，也就是说只有 contrarian investor才能挣到钱。

#### Market inefficiency

- Availability of arbitrage captial  varies over time and is insufficient to eliminate all marekt inefficiency. 
- Arbitrage capital is scarcer for macro-opportunities (market-directional trades) than for minor-opportunities (relative value trades)
- some market inefficiencies have transformed into systematic risk factors.

### 7.2 Data Mining and Other "Mirage" Explanations

#### Data Mining

- any predictability observed in the past is **sample-specific**
- overfitting, and <u>how to measure the extent of overfitting?</u> statistical tools, cross-validation, out-of-sample test, extensive robustness checks (subperiod consistency, etc.), 
- <u>how to mitigate overfitting bias?</u> being simple in model specification and oncservative in parameter estimation.
- report bias. Particularly for managed funds data.

#### Peso Problem

*peso problem* refers to the difficulty of assessing time series that are plagued by important rare events which may or may not be realized in sample — closely linked to fat tails and black swans.

If a rare adverse event to which market assigns low probability did not materialize during the sample period, selling insurance against such and event appears highly profitable. More generally, risky asset returns have benefited from events that did not happen although they could have happend.

简单的说 peso problem 就是：在有限的样本期内，稀有事件发生的次数太少（0或1）样本量太小以至于无法得出关于该事件发生概率和/或该事件影响的、具有统计显著性的结论。具体到策略研究上，如果我们的策略实际上是 selling insurance against 某种黑天鹅事件，如果在回测的 sample period 上这类事件没有发生，看起来这个策略就是一个alpha, 但实际上它是一个beta.

#### Learning

Rational learning amidst structural uncertainty can lead to statistical evidence of predictable returns that is indistinguishable form the impact of irrational expectations. ??

一直没太懂经常提到的 rational learning 到底是什么。。。

#### Market frictions

Most academic predictability evidence is presented without taking into account trading costs and other market frictions.

Paper profits tend to be most consistent in illiquid assets (eg. small-cap stocks) or in trading styles that involve high turnover (eg. short-term reveral).

学术文献常常不考虑TC和market frictions, 很多看起来有用的策略, 要么是交易流动性很差的资产、要么是高换手率的策略。



# PART 2 A dozen case studies

| Assets                   | Dynamic strategy styles                | Underlying risk factors                  |
| ------------------------ | -------------------------------------- | ---------------------------------------- |
| Equity risk premium      | Value-oriented equity selection        | Growth factor and growth premium         |
| Bond risk premium        | Currency carry                         | Inflation factor and infaltion premium   |
| Credit risk premium      | Commodity momentum and trend following | Liquidity factor and illiquidity premium |
| Alternative asset premia | Volatility selling                     | Tail risks (volatility, correlation, skewness) |

## C8 Equity Risk Premium

### 8.1 Introduction and Terminology

outline of this chapter:

- theoretical determinants. 8.2
- historial experience. 8.3
- forward-looking value measures. 8.4
- survey forecasts.
- tactical forecasting for market timing

### 8.2 Theories and the Equity Premium Puzzle

Equity risk premium 应该是多少？ CAPM从横截面的角度回答这个问题，但这里我们更关注市场整体的 risk premium 应该是多少。

General idea：required risk premia reflect cov(asset return, MU of an extra dollar). Such theory is hard to explain equity—bond premium.

// TODO 

// 这部分内容应该是用到很多 Asset Pricing 的知识，复习一下。股权溢价之谜 —> CCAPM —> SDF。

### 8.3 Historical Equity Premium

这一节讲 historical realized equity premium.

 怎么看待历史数据？几个坑：

1. 名义与实际：如果样本期很长，要考虑通胀率对名义值的影响
   - <u>nominal equity premium</u> across vary long (50 years +) samples may reflect different inflation levels
   - <u>real equity market returns</u> have been more stable over time, with a 6.3% annual average.
2. 要考虑某段subsample是否恰好发生在某些重大事件（战争、恶性通胀等）之后，一般这些事件之后资产价格严重低估。这一点跟第5点也有关系，要考虑One-off valuation gains.
3. peso problem. Past U.S. market pricing was influenced by <u>the rare disasters that could have happened but did not</u>. And realized equity returns were boosted by the absence of catastrophies and then by a *repricing effect* by the end of 20th century  when the perceived likelihood of catastrophy have fallen.
4. Survivorship bias. We examine countries that have had good or at least continues capital market performance say G5.
5.  Adjust for unexpected windfall gains. 本书的一个关键主题就是 realized return 和 expected return 的关系，如果样本期内市场经历了较大的valuation chage, 那么即使在很长的样本期下 realized return 也会受到unexpected captital gains and loss 的影响。一些文献试图通过估计 repricing effect 来 recover 过去一段时间的平均期望收益。
6. 前面说的都是 time-series 上的问题。Box 8.1 讲了cross-sectional上的问题：flat SML. 另外提到了一个 good beta and bad beta ？

### 8.4 Forward-Looking (ex ante objective) Long-term ER Measures

- <u>carry measure</u>: broader payout yields (dividend, share buybacks)
- <u>valuation measure</u>: earnings yield and Gordon model (DDM) equity premium

#### 8.4.1 carry (narrow dividend yields vs. broader total payout yield)

这一节提到了三个可以用来measure equity carry的指标：现金股利、股票回购、并购收益。

现金股利率 Dividentd yield (D/P) 是传统的、也是最符合直觉的，衡量equity carry的指标（至少1990年之前是这样，empirically, 3% ~ 6%. ）但是在1990年之后逐渐跌落到2%左右，其实这反映的是美国股票市场的一个 structural change: 1982年某SEC法案之后，许多公司用股票回购来代替现金股利。

另一个观点：cash-financed M&A 也是 cash flow to investor 的一个component, 因此也应该算在carry内，这个观点不太流行，因为 high M&A 常常与与牛市同步。

Table 8.3 展示三种 carry measure 及其组合 1. 与下一季度return的correlation 2. 自相关系数 （1985~2009）。Divided yield 与下一季度收益率相关性最高但自相关也最高；Dividend yield + Net buyback yield 与下一季度收益率相关系数达到0.27, 但加入M&A yield之后反而下降到0.15，说明M&A yeild不是一个很好的预测指标。

#### 8.4.2 value measures: earnings yield and Fed Model

Absolute valuation: E/P

Relative valuation: spread between equity market E/P and 10-year Treasury yield. 

The Fed Model: $E/P_{S\&P500} = GovBondYield_{10y}$

puzzlingly close relation between earnings yield and inflation.

Other drivers besides inflation: GDP volatility, profit/GDP ratio, demographic pattern, etc.

#### 8.4.3 ex ante equity premia based on DDM

DDM model (Gordon's growth model):
$$
\text{Equity Risk Premium} = D/P - Y_{bond} + G
$$
the questions is **inputs** of DDM model.

### 8.5 Survey-Based Subjective Expectations

Surveys of investor's equity market views asking whether investors expected the market to go up or down.

- Retail investors.  Forecasts are higher following strong realized returns and during preceived good economic times, vice versa, ie. procyclical expected SP; Optimism regarding the macro-economy translates (too) directly into optimism on stock market prospects. 
- Professional investors. More countercyclical views on long-run forecasts.
- Accdemics, Economists' GDP forecasts, and Analysts' long-term earnings forecasts.

### 8.6 Tactical Forecasting for Market Timing

Fig 8.6 一篮子择时指标，corr(择时指标，未来一季度/一年/五年的return)。包括以下几类

- Valuations. Dividend yields, earnings yields, GDP/Stock market capitalization
- Money and credit. "Follow the Fed": falling short rates and steep yield cure is bullish for equities.
- Secular credit and leverage developments. 
- Business cycle indicators. Consumption / wealth ratio (CAY), output gap, unemployment rate, manufacturing confidence (ISM), consumer confidence, past real GDP growth and economists' consensus forecast of future GDP growth, etc.
- Risk. Stock market volatility.
- Sentiment and technicals
- Seasonals. January and Halloween effects. Major holidays, turn of month, and days of scheduled macro news announcements.



## C9 Bond Risk Premium

### 9.1 Introduction, Terminology and Theories

what is BRP (bond risk premium) ? 

(ex ante) excess return of default-free long-term bond over holding a sequence of short-term bonds. 

or, the required reward for **duration extension**

distinguish these 3 concept:

- BRP (expected term premium).  NOT observable
- realized average excess bond return. Observable
- yield curve steepness (term spread). Observable

data:

- Gov Bond
- long-term: 10y, short-term: 1y
- calculation of forward rate

theories relating to steep yeild curve:

1. PEH, pure expectation hypothesis.  Assume risk premia is zero, steep yeild curve indicates that market expects short rates to raise in the future.
2. random walk. Up-ward sloping yield curve only reflects required compensation for bearing duration risk

### 9.2 Historical Average Returns

figure 9.1: return ~ volatility  plot of US Gov bonds, recent 50 years

figure 9.2: two subperiod: before and after 1981, different patterns

- before 1981, dominated by yield increase, ie. capital loss greater for longer maturities 
- after 1981, yield declines, volatility increase

### 9.3 Alternative Ex Ante Measures of BRP

The main measure of BRP is  **curve steepness**. This section discuss curve steepness and other 3 measures.

#### yield curve steepness, YC

yeild curve reflect 1. Market E(future rate change)  2. required BRP. 

below the other measures try to isolate the BRP component from YC.

#### forward rate curve("C-P BRP")

Cochrane—Piazzesi (2005)

reg realized bond returns on five one-year forward rates, resulting coefficients is (-2.1, 0.8, 3.0, 0.8, -2.1)

suggest that YC **curvature** rather than **steepness** predicts returns.

#### term strustructure models (e.g. "K-W BRP")

Pure term structure model use only yield data

Macro-finance model also include macroeconomic factors

#### survey data ("SBRP")

Using survey data (consensus forecasts of future interest rates) is the most direct way to assess market expectations. Simply subtracting this measure form current long-term yield gives an estimate of BRP.

### 9.4 Yield Curve Steepness

Empirical study: reg Y ~ X or calculate corr(X, Y) where

- Y:  
  - next quarter/year excess return, or 
  - change in 10y/3m rate 
- X:  slope of YC eg. 10y-3m

Historically, YC did not exhibit any secular up or down trends

Relation with long-term infaltion: YC steepness has little correlation with Expected 10y inflation while survey-based BRP does.

Central bank policy determines the front-end of the curve while the market's inflation expectations determine the back-end levels

简单地说就是研究如下一篮子 X 之间的相关关系，以及这一篮子 X 对两种 Y 的预测能力：

- X = level, slope, curvature of YC, inflation expectation, and survey-based BRP
- Y = realized BRP, change in short and long rate.


### 9.5 Explaning BRP behavior: first targets, then four drivers

decomposing long-term yield:

long term yield = real short yield + E(inflation) + required BRP

4 major drivers of ex ante bond premia and real yields:

1. level-dependent inflation uncertainty
2. equity and/or recession-hedging ability
3. supply-demand factors
4. cyclical effects

2, 4: covariance with bad times

long-run variation in BRP <u>primarily driven by</u> level-dependent <u>inflation</u> premium

<u>over the past decade</u>, given stable inflation expectation, <u>real factors</u> have mattered more: negative equity beta (safe haven), supply-demand factors, and cyclical factors

#### Inflation Risk Premium (IRP)

<u>higher inflation levels</u> are associated with <u>greater inflation uncertainty</u>

=> higher required premia for holding nominal bonds

BRP history is primarily driven by time-varying inflation premia

- level of inflation expectations: one-year ahead inflation forecasts data
- inflation uncertainty: realized vol of inflation and bond yields, option-based implied volatility, self-reported inflation uncertainty
- ex anted real yields and BRPs

<u>the infaltion uncertainty explantion</u> is consistant with academics who:

link risk premia with "cov with major risks" and not to standalone risks

Another theory: inflation has real effects in that it exhibits predicatable cov with equities and real growth

yield curves were 

- inverted in 19th century when <u>real risk dominated</u>
- upward sloping in 20th century when <u>inflation risks dominanted</u>

interest rate targeting smoothed short-term rate volatility after the Fed was created in 1913 and gold standard was abandoned in 1933

#### Covariance risk and safe haven premium

BRP ~ cov(inflation, MU)

here we focus on <u>stock-bond correlation</u>

in theory, covariance rather than variance determine risk premia

safe haven premium: be recession hedges that smooth portfolio returns "just when it is most needed"

Fig 9.10: compare <u>60m/26week corr(stock, bond)</u> and <u>5y inflation</u>

Any rise in inflation expectation have triple-whammy effect:

1. direct impact
2. required BRP rise due to level-dependent inflation premium
3. a lost safe haven value

#### Supply—demand factors

1. fiscal effects
2. regulatory effects and pension fund demand
3. foreign flows

##### Fiscal supply effects

Treasury scarcity scare in 2000. Fiscal surpluses raised concern that Treasury bond market would disappear 

Maturity structure of gov debt. More percent of long-maturity bond in gov debt, more steepness

Matruirty structure matter more than the level of indebtedness, the latter may suffer form cyclicality

when rising debt and deficits, bond yield drops **more** when 1. E(inflation) is high 2. initial fiscal conditions are already poor

Unfunded pension and health care costs related to demographic challenges may cause fiscal problem

##### Regulatory effects and pension fund demand

eg. 1990s UK, 

minimum funding requirement + fiscal surpluses ==> long-term gilts extremely expensive

##### Foreign flows

in early 2000s, Asian central bank channeled their surpluses maily into US treasuries.

#### Cyclical factors

BRP and business cycle:

high required premia near business cycle troughs — steep YC

low required premia near business cycle peaks — inverted YC

Fig 9.11  Counter cyclical YC steepness. Compare YC, unemployment and recession dummy

### 9.6 Tactical Forecasting — Duration Timing

empirical result:  

Cov(Y: next quarter/year/5year excess return, X: ...)

- Generic BRP measure
  - YC 10y-3m
  - Survey-based BRP
  - ex ante real yield
- Inflation
  - Expected 10y inflation
  - Bond volatility (60day)
- Safe haven
  - Equity market return (60day)
  - Equity market volatility (60day)
  - Equity—bond correlation 
- Supply—demand
  - Federal debt / GDP ratio
  - Debt share of >10y Treasuries
- Cyclical
  - business conifdence
  - Corporate profits / GDP ratio
  - unemployment rate




## C13 Currency Carry

### 13.1 Introduction

A *currency carry trade* is investing in high-yielding currency such as Australian dollar, funded by borrowing low-yielding currency such as Japanese yen.

- Academics: UIP hypothesis (uncovered interest parity)

UIP implies that a 5% carry advantage of AUD over JPY reflects market's expecation of 5% depreciation in AUD/JPY spot exchange rate over the next year.  息差反映了市场对未来汇率变动的预期

- Empirical:  NO

subsequent depreciation did not on average fully offset the carry advantage;

Moreover, the carry advantage was even augmented by capital gains from short-term appreciation of the higher-yielding currency.

### 13.2 Historical Average Returns

Sample: since 1983 (coincides with Greate Moderation period, tailwinds for the carry-ranked protolio)

G10 currencies with the highest average yields also earned highest dollar returns

Performance of G10 carray strategy (long-short 3 currencies for each): 0.61SR. Emerging markets: better

push sample period back to 1953 when Bretton Woods regime: 0.51SR

Comments of this empirial result:

- Selection bias.  "G10" universe
- Diversification. More diversified portfolio (5-5 equal weight) earn higher return and higher volatility than less diversified portfolio (1-10 portfolio)
- Ranking model vs. pairwise carry trading. Similar.
- Costs. Turnover is modest due to slow-moving interest rate gaps. Major currency have low trading cost for institutional investors
- Other horizons. Does not matter due to slow-moving gap
- Other maturities. Does not matter since cross-country spreads are so similar across maturities.
- Other carry indicators. Real interest rate diff, dividing carry by some volatility measure.
- Dynamic portfolio construction. Scale position size by "risk-parity": recent historical vol or option-implied vol

### 13.3 Improvements / Refinements to the Baseline Carry Strategy

1. broadening to emerging markets
2. combining carry with other indicators
3. timing the carry strategy

#### Broadening to emerging markets

sample period: since 1994, exceptionally benign window for emerging markets.

high-inflation currency consistently outperform low-inflation currency (no hyperinflation in sample period)

return=16%, vol=12%, SR=1.3

larger profits partly reflect wider yield gaps across emerging markets.

#### Combining carry with other indicators

cross-country yield spreads (carry) = market's expectations of future spot rate change + ex ante excess return (required currency risk premium)

- carry plus value. Proxy E(\delta S) with PPP or other valuation models
- carry plus momentum. 
- carry plus yield change. Beside the yield level, recent **changes** in yields have empirical predictive ability, perhaps because they reflect the market's evolving mentary policy or growth expectations.

indicators that are able to contemporaneously explain FX moves:

- inflation differentials
- relative interest rates
- productivity and real-growth differences, terms of trade, current account, capical flow

#### Timing the strategy

##### ex ante opportunities 

<u>carry opportunities</u>: measured by dispersion of deposit rates or carry-to-volatility ratios

(Fig 13.6) dispersion of carry among G10, time-series

##### seasonals

January excess retrun

##### conditioners (regime indicators)

The jackpot question of carry timing: avoid carry crashes

- <u>Slow-moving warning signs:</u> overvalued high-yield currency && overcrowed carry positions
- <u>Possible triggers:</u> falls in other risky assets; rising vol and core; tightening global liquidity (especially low-yielding "funding currency")

indicators:

1. Carry Losses past month
2. Voaltility data.

### 13.4 Why Carry Strategy Work?

1. currency risk premia
2. irrational expectations. Underreaction to yield change
3. peso problems. Perhaps markets assigning a small prob to large depreciation — had not yet happend in the observed sample. Selling catastrophe insurance.  Risk premium + peso problem
4. Beta risk. high risk pyemia for asset that perform poorly in bad times. Defining "bad times" as decline in equity market, currency carry strategy have positive market beta. Positive CCAPM beta: low-yielding yen serve as recession hedges for US investors.
5. Skewness risk. Carry positons are gradually build up while unwinds tend to be rapid and sharp when leveraged liquidity providers hit funding constraints.

(Fig13.8) Alpha morphs into beta: carry became systematic risk factor. 

(3 series: rolling corr within carry strategies; rolling G10-carry EqBeta; rolling Emerging-carry EqBeta)

#### Interpreting the evidence

Burnside et al. 2010a. cost of eliminating the left tail via option buying is higher in equity market than FX.

"Crash-o-phbia"

irrationality: most crash insurance is cheap in good times and richen up after a crash.

#### Other strories

##### Hyperinflation

rare event that can destroy carry strategy even more effectively than a major unwind

eg. Zimbabwe; Argentina's devaluation in 2002

To prevent: 1. smart country selection 2. country-specific stop loss 3. diversification across countries

##### Irrational expectations

exchange rate flows and rates respond sluggishly to interest rate news.

recent change in cross-country spread are able to predict near-term  currency moves and excess returns

Survey-based proxies: Concerns forecasts does not tend to materialize. ofen fundamental stroy.

### 13.5 Carry Here, Carry There, Carry Everywhere

Fig 13.9  Carry-seeking strategies in four asset contexts

(FX G10, FX Emg, FI G10, Credits)

- Diversification amon carry-seeking strategies did NOT diversify away systemetic carry exposure: sharp losses tend to concentrated in bad times.
- success of cross-country carry while less profits in within-country carry — notably in credits or debt
  - Explanation 1: less capital was allocated to cross-country carry trading
  - Explanation 2: greater propensity to experience large losses during bad times
- Carry strategies fail to be as divrsifiers during systematic events, nor a  good diversifier for existing risk-seeking postions e.g. equity market.



## Chapter 15 Volatility selling (on equity indices)

### 15.1 Introduction

- index volatility selling is "selling lottery tickets whose payoffs tend to materialize during bad times"
- Negative skewness. losses are rare but large
- options: nonlinear payoffs
- informative about Market Expectation && Preference
- pricing of higher moment risks (volatility, skew, kurtosis, fat tails, jumps, correlation) 

#### About straddle 

A straddle postion is a type of long-volatility position …

<u>… but not a pure bet on high volatility if it is bought and held.</u>

A buy-and hold straddle is a bet on a <u>large price move</u> — not on high volatility.

<u>Gamma risk</u> rather than <u>vega risk</u>

pure volatility or variance exposure, i.e. exposure to vega risk, can be achieved via

-  **delta-hedged straddles** or 
- variance swaps

both capture the diff between IV and realized vol over the life of the contract

#### Delta hedging

delta-hedging is imperfect in reality

#### Variance swap

better

#### Interpreting IV

IV = realized volatility + volatility risk premium

IV smile or smirk, why? 

- symmetric smile: fat tials in asset return distribution
- asymmetric smirk: greater downside volatility, 

the excess of skew implied in index option;

- rational risk premium: greater risk aversion after down markets
- irration crash fears


### 15.2 Historical Performance of Volatility-Trading Strategies

#### CCW vs. volatility/variance-selling strategies

CCW: covered call writting.

CCW using ATM calls on S&P 500 index: half of long-run return related to directional risk (equity risk premium), half to IV > RV (volatility risk premium)  ??? 这个怎么算的？

derivatives: using OTM, using short-dated options

CCW == selling puts

CCW is bad diversifiers away form equity indices — corr is very high

CCW volatility is mainly driven by equity returns (directional exposure)

while Variance Swap returns are mainly dirven by diff(IV, RV) 

However, though designed to be mathematically delta neutral, Variance Swap exhibits empirical  market directionality (mild positive equity market beta) because **falling equity markets tend to coincide with rising volatility**

empirical result: lost 12 years' returns in 2 months in autumn 2008

(Fig 15.1) performance and risk of S&P 500 index option-trading strategies:

how 2008 "reveal" the riskiness of vol-selling strategies:

performance: (return, volatitliy, skew, kurtosis, corr with S&P500, S&P500 beta, alpha, sharpe ratio) *

sample period:  (1989 ~ 2007/2009) * 

strategy: (VolArb, CCW using ATM, CCW using OTM, PUT)

- downfalss are worse for "pure" volatility arbitrage strategy than for CCW

why long-run positive return for volatility selling?

gap between IV and RV (Fig 15.2). This hold for major equity indices but not for single stocks

### 15.3 Tweaks / Refinements

#### Correlation premium

Equity index option selling is much more profitable than individual equity option selling

for stock index options: IV > RV, but it's not true for single-stock options

this may be explained by **correlation risk premium**

Traders may hedge index options sales with purchased of single-stock options, this strategy suffer wehn correlation across stocks rises — typically duing crises and volatile bear markets

>  correlation trading: https://en.wikipedia.org/wiki/Correlation_trading

Market vol = vol(single-stocks) + corr(single-stocks)

index volatility rise faster than volatility of single-stocks => higher implied correlation of single-stocks

> dispersion trading: https://quantpedia.com/Screener/Details/237
>
> Question: It's a known fact that IV > RV in stock-index option, then how to exploit it ?
>
> Answer (traditional): selling option with delta hedging
>
> But we can also use **dispersion trading** to exploit this IV-RV gap:
>
> selling stock-index option while buy single-stock options
>
> profit when correlaiton is not strong while losses when correlaiton rises
>
> paper: Driessen, Maenhout, Vilkov(2009) Option-implied correlations and pricing of correlaiton risk

> https://www.math.nyu.edu/faculty/avellane/Lecture10Quant.pdf

#### Skewness premium

Fact: larger IV-RV gap ( option is "expensive" ) for OTM index put options than ATM options, 

ie. they appear systematically "expensive".

IV across strike price exhibit "smile" pattern — higher IV for OTM puts and calls than for ATM options

After 1987 crash, "smirk" replace the symmetric smile for index options

### 15.4 Why Volatility Selling is Profitable

#### Should we expect make money by option selling or option buying?

risk pattern of volatility-selling:

- Return distribution: **negative skew** and **<u>high kurtosis (fat tail)</u>**
- ie. frequent small gains interspersed with rare large losses

investor preference:

- <u>like high return and **positive skew** (first and third moments of return distribution)</u> However, the positive skew may be not true for delegated portfolio managers, see Taleb 2004
- dislike high volatility and kurtosis (second and forth moments)
- this investor preference make long options "expensive" and volatility selling profitable

Beside preferences, finance theory suggests that voaltility selling should carry positive risk premium if its losses tend to <u>coincide with equity market losses or other bad times</u>

为什么volatility-selling能长期稳定获利？两个解释：1. 偏好 postive skew 2. corr with bad times.

但是基金经理的激励机制使得它们更偏好 negetive skew 并倾向于seek volatility

#### Main challenges and main explanations

Three best historical trading opportunities and thus three main challanges for theory to explain:

1. profits form index volatility selling or dispersion trading
2. richness of OTM index puts
3. richness of OTM calls on single stocks

##### (i) Volatility risk premium

the significant gap between implied and realized variance, often defined as volatility risk premium, may reflect the combination of

- compensation for systematic risk: volatility risk, jump, skew, or correlation risk
- price pressure from investor supply and/or demand
- biased forecasts of realized volatility

Carr—Wu 2009: <u>stocks with higher variance beta</u> are associated with <u>higher variance risk pyemia</u>, 

where (1) is estimated by reg Var(single-stock return) ~ Var(S&P500 return) and (2) is measureed by IV-RV

Why there is volatility risk premium? variance risk premium may reflect:

- **empirical linkage** between stock return and variance, and/or
- stochastic volatility as a **distinct risk factor**

Stock market vairance tends to be higher during down markets, thus long volatily have <u>negaive stock market beta</u> ==> beta risk, but empirically this explains only a small protions ==> <u>an independent variance risk factor</u> seems to be the key contributor, this evidence is relatively weak

A stronger evidence for volatility premium: <u>volatility selling is more profitable for stocks with high volatility</u>

However, dispersion trading argues against simple variance risk premium:

the presence of significantly postitive gap between implied and realized volatilities for index options, and absence thereof for single stocks, suggests that **it is correlation risk rather than volatility risk that is priced**.

##### (ii) richness of OTM puts on stock index

a greater real-world frequency of downward jumps or higher downside volatility due to hgiher downside correlations across stocks, is NOT the primary reason for option-pricing asymmetries.

 Main alternative reason:

- A risk premuim for volatility, correlation, and/or skew may reflect investor demond for <u>downside protetion</u>. Greater risk aversion after down moves (wealth-dependent risk aversion)
- irrationality. overestimating the likelihood of low-prob envents or like lottery tickets
- peos problem. market has assigned a small prob to such an 1987 crash event. Was market pricing due to irrational memory or rational learning?

##### (iii) richness of OTM calls on single stocks

a story of lottery tickets preferences

#### Assessing irrational and rational explanations

- End-users tend to be net long index options and net short single-stock opitons
- End-users are most active in single-stock OTM calls and index OTM puts
- positie cross-sectional realtion between option demand and option richness
- Only a small portion of option market activity is related to volatility trading, most ar used as directional positions — say, by facilitating short selling or leverage



## C19  Tail Risks (volatility, correlation, skewness)

- definition of Tail risks: volatility as well as other **higher moments**, such as correlation and skewness
- relation between return and volatility is ambiguous。 不是波动率越大，预期所以越高（长期vs.短期，大类资产内部 vs. 大类资产之间 etc.）
- selling equity index volatility and overweighting volatile asset class appear to offer positive <u>long-run</u> rewards. However, <u>stocks with the highest recent volatility</u> tend to under perform other stocks. (KEY POINT: within asset class vs. across asset class). Higher market volatility does not predict higher <u>near-term</u> mareket returns
- One explanation: correlation risk is more <u>consistently ?</u> priced than volatility risk
- whether investors prefer positive skewness or nagative skewness?  Seems to be positive skewness. Evidence in Market Price: lottery-ticket-like stocks are overpriced; richness of OTM singles-stock calls and OTM index puts.
- <u>selling stock index volatility</u> and <u>leveringup low-beta or low-volatility assets</u> have the same pattern: high long-run returns and Sharpe ratios at the expense of losing money in bad times, just likt <u>carry trading</u> and <u>harvesting illiquidity premia</u>
- reward for tail risks appear time varying — extra high in the aftermath of an adverse event


### 19.1 Introduction

Chapter 15: pure volatility risk may not be well rewarded because, while index opiton selling has been profitable, single-stock opitons selling is not. **Correlation risk premium** seems better at explaining index option richness.

**relation between return and volatility is ambiguous:**

- While positive risk—return relation work in long-run **across** asset class, **cross-sectional** relations **within** asset class have the opposite pattern. Explanation: not all volatility is equal — some volatility may be liked, eg. lottery-ticket-like assets are often overpriced, and leverage constraints push return-seeking investor s toward riskiest assets in each asset class.  我们常说的“高风险高收益”的“常识“并不完全正确，这个表述在大类资产之间是成立的，但在大类资产内部并不是这样。两种解释：1. 有些波动是prefered的，例如类彩票的资产 2. 杠杆约束使得追求高收益的人被迫使用 risky asset
- 时间序列上的 volatility— subsequent return 关系也很微妙。
- volatility is insufficient risk measure. 仅用二阶距来度量风险是不完整的

Tail risk refer to <u>non-normal market moves such as abnormally large price changes</u> or <u>correlation spiking during crises</u>

#### Not all volatility is equal

Academics: only systemetic risk should be rewarded. CAPM does not imply positive volatility—return relation, instead, it implies positive cross-sectional beta—return relation. 

However since 1960s high-beta stocks have not outperformed low-beta stocks. 

Various stories: anti-value, lottery ticket, or "good beta".

Interestingly, downside betas and other measures of downside risk appear to be positively related to average returns.

### 19.2 Factor History

Fig 19.1 Rolling historical (3-month) stock and bond volatility

Peak stock market volatility coincide with bad times (1929~1933, 1987, 2008)

Fig 19.2 VIX and 3month EqMkt Return. Volatility spikes tend to coincide with the worst market meltdowns.

上面两张图都在说一件事：波动上升往往与市场大跌同时发生

Fig 19.3 option skew (implied volatility levels across strike prices) 波动率微笑or坏笑

- Index options have much lower IV tha single-stock options, thanks to diversification 
- index skew is much more pronounced. (个股期权smile, 指数期权1987前smile, 1987之后smirk)
- all volatility shot up in 2008 amidst the market meltdown

OTM index put options are particularly expensive

### 19.3 Historical Evidence on Returns vs. Volatility && Correlation

这一节总结了关于“收益与波动到底是不是正相关”这个问题的各种角度、各种设定下的实证结果

- equity market - cross-sectional
- equity market - time series
- option market
- corelation and skewness

#### Cross-sectional relation between recent vol and future single-stock returns

近期波动率最高的那一组underperform.  <u>**hockey stick pattern**</u>

但这个策略交易成本会吃掉所有利润，这是个高换手策略（？？）

Ang et al. 2006 documented high-vol stocks' underperformance (whether total vol or idiosyncratic vol), robust to calculation window of vol, inclusion of many control factor and works in all G7 markets

Challenge: Volatile smal-cap stocks are lotter-ticket-like that may be systematically overpriced, several studies points this and can largely "explain away" the volatility—return relation:

- Frieder—Jiang(2008) 区分上行波动率和下行波动率，近期下行波动率与未来收益没有关系，但近期上行波动率与未来的低收益有显著关系。（意思是，investor's lottery-ticket preference overpice stocks with high upside vol ）
- Bali—Cakici—Whitelaw(2010) 因子：近一个月最高日收益率， 最高的一组underperform
- Boyer—Mitton—Vorkink(2009) 自己造一个measure of expected skewness, 结论：low returns for high-skew portfolios

从市场划分的角度看：散户主导的市场充满lottery-seekers, inverse vol—reward relation; 机构投资者为主的市场 vol—return realion 则是正的。

个股期权市场与股票市场的联动：both directions. (Ang—Bali—Cakici2010). Informed traders

#### Volatility factor risk premium

Pollet— Wilson(2008)

Market Variance = average var of single stocks + average corr across stocks

average corr have significantly positive relation to next quarter equity market returns, while average var of single stocks has no relation

Table 19.1 Corr(return, vol)

- return: monthly S&P500 returns
- vol
  - contemporaneous and lagged 
  - levels (Vol) and changes (dVol)
  - 1month

Bollerslev—Zhou(2007) ax ante variance risk premium proxy: gap between IV and RV

#### Option strategies

Recall conclusitons in Chapter 15:

- Equity index options tends to be **expensive** (IV >> RV), especially OTM puts
  - index volatility selling can be profitable with high but volatile reutrns and terrible timing of losses
  - index skew trading (or volatility selling with OTM puts) may be even more profiable
  - correlation/dispersion trading can give more consistent profits as  some volatility risk is hedged
- For single-stock options, IV do not consistently exceed RV, but OTM calls have expecially large negative average returns (?这里是说OTMcall也很贵的意思吗)

#### Correlation premium in equities and a lesson in the CDO market

The best place to study a <u>correlation risk premium</u> is in the relative pricing of index and single-stock opitons

While index volatilities are lower than single-stock volatilities, index options are more expensive: several studies show that average gap between IV and RV is between 2% ~ 4%, while for single stock the average gap is near zero.

<u>The economic argument for correlation premium</u>: higher correlations hurt diversification opportunities and thus worsen the investment opportunity set — a systematic risk factor that should be priced. High corr coincide with bad times.

Anadrea Buraschi etc. 2010 "When there is no place to hide — Corelation risk ..."

Other studiesshow that correlationrisk is price din the cross-section of equity returns and in time series:

- stock with higher sensitivity to rising corr need to offer higher long-run returns
- aggregate market has hgiher returns following higher average correlations

#### Hedge funds

Hedge fund's strategy of combining and levering up many long—short positions makes them more vulnerable to unexpected correlations spikes

Implicit correlation sellers often include market-neutral and convergence-oriented long—short funds that rely on stable correlations

### 19.4 Theory and Evidence on Skewness Premium

#### Skewness preference: Which sign?

- At first blush, positive skewness preference
- Taleb argues for negative skewness preference, especially fro delegated asset managers. Prefer "blowups" over "bleeding". To underperform peers consistently in normal times is BAD FOR BUSINESS, while outperforming, even by small amounts, helps to gather or maintain AUM.
- What do data say? positive skewness. <u>Note that here "positive skewness" is driven by desir for exceptional upside rather than downside protection</u>. Papers: retail investors overpay for lotteries-like stocks.

#### Empirical evidence on skewness premium

##### stock market

Bali—Cakici—Whitelaw(2010)

proxy for a lottery-ticket-like characteristic: exceptionaly high daily return. Securities with the highest max returns tend to be illiquid small-cap stocks with low prices and high idiosyncratic volatility.

Boyer—Mitton—Vorkink(2009)

expected idiosyncratic skewness. 

Expecte skewness can explain most of the underperformance of high-volatility stocks, intuitively it is clear thath investors are more likely to seek positive skewness than volatility

##### option market

empirical evidence form options markets is consistent with the hockey stick shape.

portfolios of high-strike an high-skew OTM call options — the proverbial lottery ticket — hve lareg negative reurns.

richness of OTM call options relative to ATM options is expecially high in January when lottery seeking is seasonally prevalent

### 19.5 Verdict on Why High-Volatility Assets Fare so Poorly

Explanations for low returns of the most volatile assets **within** each asset class:

- lottery preference
- leverage aversion or constraints

#### leverage

Leverage aversion made return-seeking investors overpay for the riskiest segment in each asset class

flat SML, BAB factor (betting against beta) 

provide positive long-run returns but at the cost of ill-timed losses

#### status seeking

Eric Falkenstein's book, Finding Alpha (2009): average retruns are unrelated to vol except in two extreme cases: overpay for certainty and for hopes and dreams.

### 19.6 Time-Varying Premia for Tail Risk Exposures

overprice or underprice tail risk? time-varying!

ex ante premia for asymmetric risk is outsized just after losses have materialized, gradually receding as investor memories decay, and become low after a long benign period

The implied skews for equity index options only became distinctly asymmetric — emphasizing greater downside risk — after the crash materialized in 1987 (and the same happened to FX carry strategies in 2007~2008)

**market learning** tail risks are particularly well rewarded after realization of pertinnent tail risk everts. One reason is scarcity of speculative capital follwing such adverse events. <u>Eg. Many speculators who began to buy IV in 2005, already then at historical low levels, bled money for two years and may have gone out of business before volatility finanly rose in 2007 and then soared in 2008.</u>










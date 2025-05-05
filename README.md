# imc-prosperity-3

# IMC Prosperity 3

## Leaderboard Ranking

| Round                    | Overall Rank | Manual Rank | Algorithmic Rank | Country (USA) Rank | Profit Manual | Profit Algorithmic | Profit Total |
|-------------------------|---------------|--------------|-------------------|---------------------|----------------|---------------------|----------------|
| 1 (after rerun)         | 386           | 357          | 414               | 104                 | 44,340         | 44,134              | 88,474         |
| 2 (after hardcoding)    | 528           | 708          | 606               | 167                 | 33,087         | 10,444              | 43,531         |
| 3 (after manual update) | 554           | 470          | 615               | 155                 | 53,412         | 56,149              | 109,561        |
| 4                       | 437           | 520          | 481               | 128                 | 51,801         | 28,939              | 80,740         |
| 5                       | 554           | 1057         | 397               | 159                 | -38,227        | 46,814              | 8,587          |



My involvement:
I participated in the 5 round, 15 day long IMC Propserity 3 Trading challenge under the solo team, Zebedee Datsci. I entered the competition with a limited knowledge of trading and trading algorithms, and I believe there is still much room for improvement for my understanding in this space to be able to develop algorithms with optimized PNL return created within shorter periods of time, while also tackling the manual trading optimization problems in more creative ways. My final position was #554 overall and #159 in the United States. In total 13,614 teams registered with 4,213 teams ranked according Jasper's imc 3 leaderboard tool: https://jmerle.github.io/imc-prosperity-3-leaderboard/.

Average time comitted per day: 5.5 hours
Total time spent: 82.5 hours

Areas for improvement:

1. Time management:
I wasted lot of time tuning hyperparameters manually by comparing the results utilizing Jasper's open source IMC propsperity tools and tracking each parameter using an excel spreadsheet. This process could have been streamlined, by writing .py script to autosubmit to Jasper's backtester tool for range of values for a specific parameter then append results for that parameter to dataframe/csv and then continously repeating the process for each parameter for that specific algorithm. Here is an example of what I did for round 1 SQUID_INK which I should have streamlined from round 1 itself instead of doing manually for each round:

![image](https://github.com/user-attachments/assets/441e0d22-e982-4cdd-b951-c9b6e0f530c1)

Also for Time management I should have made it a concrete goal of mine to submit a stable profit algorithm for each product. From the second round onwards I didn't always implement all the new products introduced, the products I specifically had trouble with were the picnic baskets and magnificent macaroons. As a result of this shortcoming, I was less efficient in the later algorithmic trading rounds, as I was trying to implement multiple algorithms that I did not finalize in prior rounds.  

Areas of Improvement: Time Management, Method to improve: Streamline all manual processes for competition like Parameter tuning.

2. Algorithm Development:

This was certainly the most important aspect of this competition, yet even after the first round of this competition my algorithm development process was relatively scatterbrained and close minded. If I were to do this competition again I would adjust my approach to be something like this for the first day of each three day round focus on data analysis of historical price data of the products. On the second day I would look at industry approaches online for the specific product I am trying to implement: volatile price product (mean reversion), options (black scholes), ETF (arbitrage), etc. Then also on that second day I would create three strategy variations of the same type of algorithm and write out the psuedo-code for each variation, so if one strategy fails I can quickly adjust to one of the backups. On the third day create a code implementation of all three strategy variations and compare submissions to website and backtester then tune hyperparmeters using regex automated script system.   

Areas of Improvement: Algorithm Development, Method to improve: Stuctured process for algorithm development that is constant throughout each round so time is not wasted on developing a form of structure.

3. Manual Trading:

This was my most weak aspect throughout the competition, and the only area where I had PNL loss in any of the rounds. Ultimately, I needed to be much more methodical and creative with my approaches in the manual trading rounds of the competition especially in the rounds heavily dependent on the behavior of other competing teams. For future competitons, projects, and initiatives that involve these types of optimization problems I still need to greatly develop myself. 

Round 1 Manual:

Prompt:
You get the chance to do a series of trades in some foreign island currencies. The first trade is a conversion of your SeaShells into a foreign currency, the last trade is a conversion from a foreign currency into SeaShells. Everything in between is up to you. Give some thought to what series of trades you would like to do, as there might be an opportunity to walk away with more shells than you arrived with.

| From \ To           | Snowballs | Pizza | Silicon Nuggets | SeaShells |
| ------------------- | --------- | ----- | --------------- | --------- |
| **Snowballs**       | 1.00      | 1.45  | 0.52            | 0.72      |
| **Pizza**           | 0.70      | 1.00  | 0.31            | 0.48      |
| **Silicon Nuggets** | 1.95      | 3.10  | 1.00            | 1.49      |
| **SeaShells**       | 1.34      | 1.98  | 0.64            | 1.00      |


Round 1 Manual Approach: Trading table trying to optimize for PNL return based on product conversions. Utilized a ipynb from Gabsens repository from previous year competition to check my solution. There was only "one" solution for this problem and it could be brute forced developing a solution by code was also fairly simple. 

![image](https://github.com/user-attachments/assets/23baefca-a68d-4a6f-87a3-0cd3d7434e8f)


Round 1 Trading:
Prompt:
The first three tradable products are introduced: : `Rainforest Resin` , `Kelp`, and `Squid Ink`. The value of the `Rainforest Resin` has been stable throughout the history of the archipelago, the value of `Kelp` has been going up and down over time, and the value of `Squid Ink` can also swing a bit, but some say there is a pattern to be discovered in its prize progression. All algorithms uploaded in the tutorial round will be processed and generate results instantly, so you can experiment with different programs and strategies.

Position limits for the newly introduced products:

- `RAINFOREST_RESIN`: 50
- `KELP`: 50
- `SQUID_INK`: 50

### Hint

Squid Ink can be a very volatile product with price having large swings. Making a two-sided market or carrying position can be risky for such an instrument. However, with large swings comes large reversion. Squid Ink prices show more tendency to revert short term swings in price.

A metric to keep track of the size of deviation/swing from recent average could help in trading profitable positions.

Round 1 Trading Approach: Three Products KELP, RAINFOREST_RESIN, and SQUID_INK. Was able to create a good strategy for KELP and RAINFOREST_RESIN utilizing market making strategy as the historical price behavior of these products were relatively stable. SQUID_INK was more difficult to implement because of its swings and volatile price history, the strategy to utilize here was mean reversion but my implementation was nowhere near optimized when comparing to other teams.

![image](https://github.com/user-attachments/assets/28abd5f6-faba-4731-aa31-48c68cd0558f)


Round 1 Overall:

![image](https://github.com/user-attachments/assets/617de4d7-0fa5-4455-a830-496b8ef759f9)

Round 2 Manual: 
Prompt:
Some shipping containers with valuables inside washed ashore. You get to choose a maximum of two containers to open and receive the valuable contents from. The first container you open is free of charge, but for the second one you will have to pay some SeaShells. Keep in mind that you are not the only one choosing containers and making a claim on its contents. You will have to split the spoils with all others that choose the same container. So, choose carefully. 

Here's a breakdown of how your profit from a container will be computed:
Every container has its **treasure multiplier** (up to 90) and number of **inhabitants** (up to 10) that will be choosing that particular container. The container’s total treasure is the product of the **base treasure** (10 000, same for all containers) and the container’s specific treasure multiplier. However, the resulting amount is then divided by the sum of the inhabitants that choose the same container and the percentage of opening this specific container of the total number of times a container has been opened (by all players). 

For example, if **5 inhabitants** choose a container, and **this container was chosen** **10% of the total number of times a container has been opened** (by all players), the prize you get from that container will be divided by 15. After the division, **costs for opening a container** apply (if there are any), and profit is what remains.

Round 2 Manual approach: 
Choose a spot with a multiplier, multiplier is reduced by percentage of other teams that go there Profit formula looks like this 10,000*((Multiplier)/(Inhabitants (fixed value) + Percentage of teams that choose the same spot (Unknown value)). There were teams that created bots to create Prosperity teams and artifically inflate the percentage of teams that went to specific locations, although some locations were not influenced by this. Ultimately, the locations with low multipliers performed the best in this round (although they were high risk as slight percentage of team increase would have greatly reduced the profit for those chosen locations). I picked I relatively bad choice because of the number of teams that chose the same spot.

![image](https://github.com/user-attachments/assets/02675a2c-4541-49da-8bc8-0a3f503dd32f)


Round 2 Trading:

Prompt:
In this second round, you’ll find that everybody on the archipelago loves to picnic. Therefore, in addition to the products from round one, two Picnic Baskets are now available as a tradable good. 

`PICNIC_BASKET1` contains three products: 

1. Six (6) `CROISSANTS`
2. Three (3) `JAMS`
3. One (1) `DJEMBES`

`PICNIC_BASKET2` contains just two products: 

1. Four (4) `CROISSANTS`
2. Two (2) `JAMS`

Aside from the Picnic Baskets, you can now also trade the three products individually on the island exchange. 

Position limits for the newly introduced products:

- `CROISSANTS`: 250
- `JAMS`: 350
- `DJEMBES`: 60
- `PICNIC_BASKET1`: 60
- `PICNIC_BASKET2`: 100

Round 2 Trading approach: 
5 New products JAMS, DJEMBES, CROISSANTS, PICNIC_BASKET1, PICNIC_BASKET2. PICNIC_BASKET1 is composed of 6 CROISSANTS, 3 JAMS, and 1 DJEMBES, while PICNIC_BASKET2 is composed of 4 CROISSANTS and 2 JAMS so basically the picnic baskets are spread products/ETFs. All these products were relatively voltile but the components price behavior often mirrored the behavior of the baskets. I was not able to implement a profitable strategy for the final submission of this round. I think the trick here is managing the shared components between PICNIC_BASKET1 and PICNIC_BASKET2 then performing an arbitrage strategy and this is what I was trying to implement. However, if I was able to tackle this same products again what I would do is just trade PICNIC_BASKET2 on its own and develop the arbitrage strategy just for PB1. I don't know if this is the best strategy I should have done some more research on ETF type algorithms. 

![image](https://github.com/user-attachments/assets/3040d08b-892e-43cd-a0df-ec50cde8d45e)

Round 2 Overall:

![image](https://github.com/user-attachments/assets/f56d849e-f4af-4794-b7f0-19aa1942e7bc)


Round 3 Manual:

Prompt:
A big group of Sea Turtles is visiting our shores, bringing with them an opportunity to acquire some top grade `FLIPPERS`. You only have two chances to offer a good price. Each one of the Sea Turtles will accept the lowest bid that is over their reserve price. 

The distribution of reserve prices is uniform between 160–200 and 250–320, but none of the Sea Turtles will trade between 200 and 250 due to some ancient superstition.

For your second bid, they also take into account the average of the second bids by other traders in the archipelago. They’ll trade with you when your offer is above the average of all second bids. But if you end up under the average, the probability of a deal decreases rapidly. 

To simulate this probability, the PNL obtained from trading with a fish for which your second bid is under the average of all second bids will be scaled by a factor *p*:
`p = ((320 – average bid) / (320 – your bid))³`

You know there’s a constant desire for Flippers on the archipelago. So, at the end of the round, you’ll be able to sell them for 320 SeaShells ****a piece.

Think hard about how you want to set your two bids, place your feet firmly in the sand and brace yourself, because this could get messy.

Round 3 Manual Approach:
Bidding Flippers to buy from Sea Turtles then reselling. None of the Sea Turtles trade between a certain range. I wrote some code to create simulations for this, but I ended up using gut feeling because the simulations did not allign with my predictions this was my final choice: 

![image](https://github.com/user-attachments/assets/ed673280-f2b7-433f-b07c-e9a5df5e522e)


Round 3 Trading:
Prompt:
Our inhabitants really like volcanic rock. So much even, that they invented a new tradable good, `VOLCANIC ROCK VOUCHERS`. The vouchers will give you the right but not obligation to buy `VOLCANIC ROCK` at a certain price (strike price) at voucher expiry timestamp. These vouchers can be traded as a separate item on the island’s exchange. Of course you will have to pay a premium for these vouchers, but if your strategy is solid as a rock, SeaShells spoils will be waiting for you on the horizon. 

There are five Volcanic Rock Vouchers, each with their own **strike price** and **premium.** 

**At beginning of Round 1, all the Vouchers have 7 trading days to expire. By end of Round 5, vouchers will have 2 trading days left to expire.**

Position limits for the newly introduced products:

- `VOLCANIC_ROCK`: 400

`VOLCANIC_ROCK_VOUCHER_9500` :

- Position Limit: 200
- Strike Price: 9,500 SeaShells
- Expiration deadline: 7 days (1 round = 1 day) starting from round 1

`VOLCANIC_ROCK_VOUCHER_9750` :

- Position Limit: 200
- Strike Price: 9,750 SeaShells
- Expiration deadline: 7 days (1 round = 1 day) starting from round 1

`VOLCANIC_ROCK_VOUCHER_10000` :

- Position Limit: 200
- Strike Price: 10,000 SeaShells
- Expiration deadline: 7 days (1 round = 1 day) starting from round 1

`VOLCANIC_ROCK_VOUCHER_10250` :

- Position Limit: 200
- Strike Price: 10,250 SeaShells
- Expiration deadline: 7 days (1 round = 1 day) starting from round 1

`VOLCANIC_ROCK_VOUCHER_10500` :

- Position Limit: 200
- Strike Price: 10,500 SeaShells
- Expiration deadline: 7 days (1 round = 1 day) starting from round 1

### Hint for Algorithmic Challenge

Hello everyone, hope you're enjoying the VOLCANIC_ROCK vouchers and a variety of trading strategies these new products introduce. While digging for the rock, Archipelago residents found some ancient mathematics sharing insights into VOLCANIC_ROCK voucher trading. Here's what the message with obscure and advanced mathematics read,

Message begins,

I have discovered a strategy which will make ArchiCapital the biggest trading company ever. Here's how my thesis goes,

t: Timestamp
St: Voucher Underlying Price at t
K: Strike
TTE: Remaining Time till expiry at t
Vt: Voucher price of strike K at t

Compute,

m_t = log(K/St)/ sqrt(TTE)
v_t = BlackScholes ImpliedVol(St, Vt, K, TTE)

for each t, plot v_t vs m_t and fit a parabolic curve to filter random noise.

This fitted v_t(m_t) allows me to evaluate opportunities between different strikes. I also call fitted v_t(m_t=0) the base IV and I have identified interesting patterns in timeseries of base IV.

Message ends.

![image](https://github.com/user-attachments/assets/d6e593b4-22ec-4f78-a176-9e81b6c39fb7)

Round 3 Trading Approach: 6 new products VOLCANIC_ROCK, VOLCANIC_ROCK_VOUCHER_9500, VOLCANIC_ROCK_VOUCHER_9750, VOLCANIC_ROCK_VOUCHER_10000, VOLCANIC_ROCK_VOUCHER_10250, VOLCANIC_ROCK_VOUCHER_10500 basically for these products in this round we needed to create options trading strategy. I created black scholes algorithm based off the recommended hint + previous competition approahces with a delta hedging strategy, the strategy ended up being successful and was returning stable profit (non-volatile).

Round 3 Overall:

![image](https://github.com/user-attachments/assets/50e31431-b05b-450d-acd2-5921f12d486f)


Round 4 Manual:
Prompt:
You’re participating in a brand new game show and have the opportunity to open up a maximum of three suitcases with great prizes in them. The whole archipelago is participating, so you’ll have to share the spoils with everyone choosing the same suitcase. Opening one suitcase is free, but for the second and third one you’ll need to pay to get inside. 

Here's a breakdown of how your profit from a suitcase will be computed:
Every suitcase has its **prize multiplier** (up to 100) and number of **inhabitants** (up to 15) that will be choosing that particular suitcase. The suitcase’s total treasure is the product of the **base treasure** (10 000, same for all suitcases) and the suitcase’s specific treasure multiplier. However, the resulting amount is then divided by the sum of the inhabitants that choose the same suitcase and the percentage of opening this specific suitcase of the total number of times a suitcase has been opened (by all players). 

For example, if **5 inhabitants** choose a suitcase, and **this suitcase was chosen** **10% of the total number of times a suitcase has been opened** (by all players), the prize you get from that suitcase will be divided by 15. After the division, **costs for opening a suitcase** apply (if there are any), and profit is what remains.

To help you with your decision making, here's the distribution of player's choices from **Round 2** Manual:

![image](https://github.com/user-attachments/assets/a1dd525b-baa7-41a4-b973-445342e22989)



![image](https://github.com/user-attachments/assets/acf0b7be-55ad-4018-b85f-307d8cc3895a)

Round 4 Manual Approach: Take a sample by surveying family and friends of which choice they would make depending on the prior percentages for shipping container problem from round 2 manual. I made my final decision depending on there choices. However, this was definitely not the most effective method as I believe most indiviudals did not account the prior percentage distributions to make their final choice.


Round 4 Trading:

Prompt:
In this fourth round of Prosperity a new luxury product is introduced: `MAGNIFICENT MACARONS`. `MAGNIFICENT MACARONS` are a delicacy and their value is dependent on all sorts of observable factors like hours of sun light, sugar prices, shipping costs, in- & export tariffs and suitable storage space. Can you find the right connections to optimize your program? 

Position limits for the newly introduced products:

- `MAGNIFICENT_MACARONS`: 75
- Conversion Limit for `MAGNIFICENT_MACARONS` = 10

## Hint - Algo

It was well understood lore in Archipelago that low sunlight index can impact sugar and MACARON production negatively causing prices to rise due to panic among residents. However, ArchiResearchers have identified existence of a CriticalSunlightIndex (CSI).

If sunlightIndex goes below this CSI with an anticipation to remain under this critical level for a long period of time, sugar and MACARON prices can increase by substantial amount with a strong correlation.

When sunlightIndex is above this CSI, Sugar and MACARON prices tend to trade around their respective fair values and demonstrates market supply-demand dynamics.

Can you find this CSI and use it to trade better than ever and make your island prosper? All the best!

## Additional trading microstructure information:

1. ConversionObservation (detailed in “[Writing an Algorithm in Python](https://www.notion.so/Writing-an-Algorithm-in-Python-17be8453a09381988c6ed45b1b597049?pvs=21)” under E-learning center) shows quotes of `MAGNIFICENT_MACARONS` offered by the chefs from Pristine Cuisine
2. To purchase 1 unit of `MAGNIFICENT_MACARONS` from Pristine Cuisine, you will purchase at askPrice, pay `TRANSPORT_FEES` and `IMPORT_TARIFF`
3. To sell 1 unit of `MAGNIFICENT_MACARONS` to Pristine Cuisine, you will sell at bidPrice, pay `TRANSPORT_FEES` and `EXPORT_TARIFF`
4. You can ONLY trade with Pristine Cuisine via the conversion request with applicable conditions as mentioned in the wiki
5. For every 1 unit of `MAGNIFICENT_MACARONS` net long position, storage cost of 0.1 Seashells per timestamp will be applied for the duration that position is held. No storage cost applicable to net short position

Round 4 Trading Approach: New Product MAGNIFICENT_MACAROONS. luxury product timing specific conditions like tariffs, transport fees, sunlight index, and sugar price as indicators for MACAROON price also needed to handle conversions of the luxury product. The most important conditions to time out were sunlight index, sugar price, and import/export tariffs. I ended up finding the Critical Sunlight Index to be 50, I am relatively confident in this value but I don't know if I found the most appropriate value for rebound timesteps when sunlight index returns back to or above CSI value and  drop timesteps for when below sunlight index falls below CSI. In short, I don't think I handled the lag appropriately for CSI which is why algorithm performed well on 100k timestep test submission but failed and was unstable on the 1M timestep actual submission. 

![image](https://github.com/user-attachments/assets/18e3aa26-c24e-4b12-a7a6-b1ead5db83fa)

Round 4 Overall:

![image](https://github.com/user-attachments/assets/eaa8be6a-fbef-4d82-8f28-817a49047056)

Round 5 Manual:
Prompt:
You’ve been invited to trade on the exchange of the West Archipelago for one day only. An exclusive event and perfect opportunity to make some big final profits before the champion is crowned. Benny the Bull has granted you access to his most trusted news source: Goldberg. You’ll find all the information you need right there. Be aware that trading these foreign goods comes at a price. The more you trade in one good, the more expensive it will get. This is the final stretch. Make it count! 

Round 5 Manual Approach: 

Limited Participation due to familial and work obligations. I did not have time to reference old competition materials for this round of the competition and develop a strong foundation of a strategy for this round. I ended up creating a really bad submission for this manual round that ended up in PNL loss. I just read the provided news articles and created a quick judgment call based on what the article said. I was on the fence about the SHEDDIT (hay) and MOONSHINE articles and my guesses ended up being very wrong. I also did not account for how much the fee would influence the Profit for this round. The percentage you invest definitely matters and just trying to split the percentages equally among the products is not the correct approach. Also I used up all the investable amount provided (100%) I believe I should have used a lower percentage 70-80% for much higher returns as it would have incurrred less fees.  

![image](https://github.com/user-attachments/assets/1635297d-35ee-4fb8-9926-2839e4a1eab0)

Round 5 Trading:
Prompt:
The final round of the challenge is already here! And surprise, no new products are introduced for a change. Dull? Probably not, as you do get another treat. The island exchange now discloses to you who the counterparty is you have traded against. This means that the counter_party property of the OwnTrade object is now populated. Perhaps interesting to see if you can leverage this information to make your algorithm even more profitable?

class OwnTrade:
    def __init__(self, symbol: Symbol, price: int, quantity: int, counter_party: UserId = None) -> None:
        self.symbol = symbol
        self.price: int = price
        self.quantity: int = quantity
        self.counter_party = counter_party


Round 5 Trading Approach:
Limited Participation due to familial and work obligations. Submitted previous round algorithm did not account for the main component of this rounds algorithm challenge being the OwnTrade class/other competitor on archipelago.

![image](https://github.com/user-attachments/assets/1c75b74f-30b8-4931-b09a-2e8f0ea0f83c)

Round 5 Overall:

![image](https://github.com/user-attachments/assets/6595e8b1-f2f5-4bc9-b304-0f2948359d32)


## Key Takeaways

### Competition Specific

**Methodologies I would use for "Difficult to Trade" Products:**

Round 1. **SQUID\_INK (Historically Volatile Price):**

   * Apply a **Mean Reversion** strategy.

Round 2. **PICNIC\_BASKET1, PICNIC\_BASKET2, and Component Products:**

   * **Option A:** Arbitrage between both baskets and their components with careful **position limit management**, especially since components are shared between baskets.
   * **Option B:** Run an **arbitrage strategy** for one picnic basket and its corresponding components, and **trade the other picnic basket independently**.

Round 3. **VOLCANIC\_ROCK + VOUCHERS:**

   * Use **Black-Scholes pricing** and implement **Delta Hedging** for managing risk.

Round 4. **Counterparty Trading**

   * Still don't know :)

Round 5. **MAGNIFICENT\_MACAROONS (Timing Multiple Indicators Simultaneously):**

   * Did not participate due to work and family obligations. 


### General

- **Focus on the algorithm challenge:** It is very difficult to find the "optimal" solution for manual rounds, especially when results depend on other teams' behavior and you're not using effective optimization methods.
- **Prioritize stability:** Always try to submit stable profit algorithms. Avoid overfitting to historical price data and ensure your algorithm performs well on both the backtester and the website submission.
- **Cover all products:** Aim to create a stable profit algorithm for every product introduced, even if the profit is relatively low. This prevents needing to revisit products in later rounds.
- **Balance effort:** Spend a balanced amount of time each round to avoid burnout in later stages.
- **Stick to a process:** Develop and adhere to a clear structure for approaching the algorithm challenge each round.
- **Automate manual tasks:** Eliminate repetitive or manual work to save time and reduce errors.
- **Prosperiy Discord:** Lot of teams try to throw competitors off in the discord by sharing misinformation, also be careful sharing your strategies with other competitors.
- **Collaborate when possible:** Work with a team or other competitors if you can — collaboration helps! 😄

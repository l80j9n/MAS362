java cMAS362/462/6053/61017 Financial Mathematics

Lecture Notes1

Sam Marsh

Semester 1, 2023

1basedonnotesbyMotyKatzmanandDimitriosRoxanas

Contents

What is this course about? 5

1. What does “correct price” mean? 5

2. Portfolio Theory 6

Chapter 1. Interest, present value and bonds 9

1. Interest, periodic and continuous compounding 9

2. Present value 11

3. Bonds 13

4. Discount and yield curves 14

5. Forward rates 16

6. Exercises 17

Chapter 2. Forward and Futures Contracts 19

1. Short-selling 19

2. The forward price 20

3. Foreign exchange forward contracts 22

4. Futures contracts 22

5. Exercises 23

Chapter 3. Options 25

1. The payoffs of options 25

2. Elementary inequalities satisfied by option prices 26

3. Optimal exercise for American style options 27

4. Parameters affecting the prices of options 28

5. Exercises 28

Chapter 4. Binomial trees and risk neutral valuation 31

1. A motivating example 31

2. Derivatives in a simple, up-down world 32

3. An example 33

4. A two step process 33

5. An example 34

6. n-step trees 35

7. Example: an American option 36

8. Using binomial trees for approximating values of derivatives - Not examinable 37

9. Exercises 38

Chapter 5. The stochastic process followed by stock prices 39

1. Brownian motion 39

3

4 CONTENTS

2. The Ito integral 40

3. Modelling stock prices 41

4. Ito’s Lemma. 43

5. Exercises 45

Chapter 6. The Black-Scholes pricing formulas 47

1. The Black-Scholes differential equation 47

2. Boundary conditions 48

3. The Black-Scholes pricing formulas 49

4. More exotic derivatives 50

5. The Black-Scholes pricing formulas: the risk neutral valuation approach. 51

6. Volatility 52

7. Exercises 52

Chapter 7. Portfolio Theory 55

1. Axioms satisfied by preferences 55

2. Indifference curves 56

3. Portfolios consisting entirely of risky investments 57

4. The feasible set 58

5. Efficient portfolios 58

6. Different choices of portfolios for different appetites for risk 59

7. Portfolios containing risk-free investments 60

8. Exercises 61

Chapter 8. The Capital Asset Pricing Model 63

1. The market portfolio. 63

2. The market price of risk 64

3. Exercises 65

Solutions 67

Chapter 1 67

Chapter 2 69

Index 71

What is this course about?

In this course you will learn some basic facts about an important component of modern life:

finance. This is a mathematics course hence we will be interested in mathematical ideas used in the

context of finance. Our task is to build a mathematical model of financial securities. A crucial first

stageisconcernedwiththepropertiesofthemathematicalobjectsinvolved. Thisisdonebyspecify-

ing a number of assumptions, the purpose of which is to find a compromise between the complexity

of the real world and the limitations and simplifications of a mathematical model imposed to make

ittractable.1 Theassumptionswearegoingtomakereflectourcurrentpositiononthiscompromise

and will be modified in the future. You may find that some situations look simple based on these

assumptions; however I hope you will see they can be sufficiently interesting to convey the flavour

of the theory to be developed later on.

Specifically, in this course we aim to address two questions:

(1) What is the “correct price” of financial assets?

(2) What are optimal investment strategies?

ThefirstquestionwillleadustotheBlack-Scholespricingformula,whichearnedRobertC.Mer-

ton and Myron S. Scholes the 1997 Nobel prize in Economics. William F. Sharpe and Harry M.

Markowitz received the 1990 Nobel prize in Economics for answering the second question.

1. What does “correct price” mean?

Lets first see an example of an incorrect price. Suppose that a barrel of oil trades at ￡100 (i.e.,

one can buy it for ￡100 and one can sell it for ￡100). I want to start trading in oil, too. Would

￡120 be a correct price? No! Other traders will buy oil in large quantities for ￡100, sell it to me for

￡120. Everyone except me will become rich, I end up with a pile of barrels of oil I can’t sell. Would

￡90 be a correct price? Think about it. (The answer is “no”).

Amoresubtleexample: considerthreemerchantswhoarewillingtobuyandsellbagscontaining

apples and oranges (all of identical size and quality) as follows:

Bag content Price

Merchant A 3 apples, 2 oranges ￡5

Merchant B 2 apples, 3 oranges ￡6

Merchant C 4 apples, 3 oranges ￡8

To see that these prices are incorrect, let me show you how to get rich:

(a) borrow ￡36 for a short while (with negligible interest);

(b) buy 6 bags from merchant A and buy 1 bag from merchant B for a total cost of ￡36;

1Thereisawell-knownrelevantquoteforthis: “Allmodelsarewrong,somemodelsareuseful”.

5

6 WHAT IS THIS COURSE ABOUT?

(c) rearrange the fruit in five bags of 4 apples and 3 oranges each;

(d) sell the five bags to merchant C for ￡40;

(e) return the ￡36 loan and pocket a ￡4 profit.

Repeat this process until you are very rich.

Lots and lots of people would be buying from merchants A and B and selling to merchant C.

WhenthishappensthepricesofbagsAandBwillriseandthoseofbagCwillfall, andthisprocess

will continue until there are no more easy profits to be made.

Notice:

(a) we didn’t assume an intrinsic or objective price of apples and oranges,

(b) correct pricing is an equilibrium price,

(c) we expose incorrect pricing by exhibiting profit-making trading strategies which change

prices.

The making of a certain profit with no investment is called arbitrage. Correct pricing means

setting the unique price which does not introduce arbitrage opportunities. The correct price of bag

Cwouldbe￡36/5asthatistheuniquepriceforwhichthestrategyabove(oritsopposite)doesnot

produce a profit. We call this method of pricing no-arbitrage pricing, which is also known colloqui-

ally as “There is no such thing as a free lunch!”

Thegeneralideaforsucharguments, usedtofindthe“correct”priceofsomething, istousethe

assumptionofnoarbitragetoshowthatthecorrectpricecanbeneitherhighernorlowerthanwhat

weclaimtobetherightone. The guiding principle for such arguments is that if something

has a price that is perceived to be “too low”, we buy it in the hopes that we can sell

it for a higher price and make a profit; similarly, if we think that something is priced

“too high”, we seek to sell it.

No-arbitrage pricing is the most fundamental (and mathematically fruitful) assumption we will

make about the market. It is an assumption that’s close enough to reality. As we will witness our-

selves in this course, arguments based on the no-arbitrage-principle are the main tools of financial

mathematics. Arbitrageopportunitiesrarelyexistinpractice. Thisisreasonable: ifarbitrageexists,

arbitragetradingwilloccurandpriceswillquicklychangetoeliminatethesearbitrageopportunities.

Ifandwhentheydo,thegainsaretypicallyextremelysmallcomparedtothevolumeoftransactions,

makingthembeyondthereachofsmallinvestors. Theycanhoweverarisewhenmarketparticipants

make a “mistake”, but they are usually very subtle, short-lived and difficult to spot.

2. Portfolio Theory

Arethereinvestmentstrategieswhicharebetterthanothers? Andwhatcould“better”meanin

thiscontext? Wearegreedy,i.e.,wewanthighreturns. Butaveragehighreturnsarerisky! Suppose

you are offered to make a bet on the outcome of tossing a fair coin: heads – you lose everything

you own, including your clothes, and are forced to live on the street; tails – you double your wealth.

Would you bet? This is a fair game, i.e., the expected gain is zero, but most people would not

bet. People are not only greedy – they also have an aversion towards risk. Even if a win triples or

quadruples their wealth, most people would not place a bet. If we used a coin which produces tails

with 99% probability some people might choose to place a bet. Now the expected gain may tempt

some, but not others.

2. PORTFOLIO THEORY 7

There is an interplay between expected returns and risk investors are willing to take. So a

“good”waytoinvestisastrategythatcompensatesforitsriskwithanappropriatelyhighexpected

return.

The last part of the course will make this statement precise: we will see that these optimal

investments exist and consist of portfolios 2 of risk-free deposits/bonds and market-index trackers.

2Portfolio: acollectionofassets

CHAPTER 1

Interest, present value and bonds

From our daily experience we understand that ￡100 to be received after one year is worth less

than the same amount today. The main reason is that money due in the future (or locked in a

fixed term account) cannot be spent right away. One would therefore expect to be compensated for

postponed consumption. In addition, prices may rise in the meantime, and in that scenario, this

amount will not have the same purchasing power as it would have in the present. Finally, there is

always a risk, even if a negligible one, that the money will never be received. Whenever a future

paymentisuncertaintosomedegree,itsvaluetodaywillbereducedtocompensatefortherisk. For

now, we shall restrict ourselves to risk-free assets, such as a bank account or a bond (more about

bonds later in this chapter.)

Thewayinwhichmoneychangesitsvalueintimeisacomplexissueoffundamentalimportance

in finance. This topic is often referred to as the time value of money. We will be mainly addressing

the following two questions:

? What is the future value of an amount invested (or borrowed) today ?

? What is the present value of an amount to be paid or received at a certain time in the

future ?

1. Interest, periodic and continuous compounding

Money can be lent and thus earn interest; think of interest as getting paid “rent” for your

money. For what follows, suppose that an amount P is paid into a bank account (you are “lending

thebank”), whereitistoearn(or“accrue”)interest. Thefuture valueofthisinvestmentconsistsof

the original deposit, called the principal, plus all the interest earned since the money was deposited

in the account. We will assume that the principal A is attracting annual interest at a constant rate

r > 0. Interest rates apply for a given period, and interest is often compounded a fixed number

of times in that period. In other words, the interest earned will now be added to the principal

periodically, for example, annually, semi-annually, quarterly, monthly, daily, etc. Subsequently,

interest will be attracted not just by the original deposit, but also by all the interest earned so far.

In such cases, we talk of discrete or periodic compounding.

Example. Let’s consider the case of monthly compounding. The first interest payment of r A

12

willbedueafteronemonth(thisishowmuchinterestouroriginaldepositwillattractinonemonth).

Therefore, now our principal (how much we currently have in the bank) is A+ r A = (1+ r )A.

12 12

This whole amount will now attrack interest in the future. The next interest payment, due after

two months (2 since we started, 1 month since the last payment), will be r (1+ r )A, increasing

12 12

our total capital (what we have in the bank) to (1+ r )2A (check this!). After one year, our capital

12

will have become (1+ r )12A, after m months it will be (1+ r )mA, and after n years it will be

12 12

(1+ r )mnA. The last formula admits n equal to a whole number of months, that is, a multiple of

12

1 .

12

9

10 1. INTEREST, PRESENT VALUE AND BONDS

In general, if m interest payments are made per annum, the time between two consecutive

paymentsmeasuredinyearswillbe 1,thefirstpaymentbeingdueattime 1.Eachinterestpayment

m m

will increase the principal by a factor of 1+ r. Given that the interest rate remains unchanged,

m

after n years the future value of an initial principal A, will become

(cid:16) r (cid:17)mn

(1) V(n)= 1+ A,

m

because there will be nm interest payments during this period. In this formula n nust be a whole

multiple of the period 1. The number (cid:0) 1+ r(cid:1)mn is referred to as the growth factor.

m m

To summarize, an amount A invested for n years at a yearly interest rate r com-

pounded m times a year, yields at the end of this period

A(cid:0)

1+

r(cid:1)mn

.

m

The exact value of the investment may sometimes need to be known at time instants between

interest payments. In particular, this may be so if the account is closed on a day when no inter-

est payment is due. For example, what is the value after 10 days of a deposit of ￡100 subject

to monthly compounding at 10%? One possible answer is ￡100, since the first interest payment

wouldbedueonlyafteronewholemonth. Itishoweverpossibletoextend(1)foralln≥0,notjust

integermultiplesofthecompoundingfrequency,andfromnowthiswillbeastandingassumption.

(Under this assumption, that we allow for any t≥0) formula (1) for the future value at time t

of a principal A attracting interest at a rate r >0 compounded m times a year can be written as

(cid:20)(cid:16)

r

(cid:17)m(cid:21)tr

V(t)= 1+ r A,

m

Now think of a case of periodic compounding with the frequency m is very large (e.g., 1 second or

even milliseconds). In the limit as m→∞, we obtain1

(2) V(t)=etrA,

This is known as continuous compounding (with corresponding growth factor etr). Formula (2) is a

good approximation of the case of periodic compounding when the frequency m is very large. Since

it is a simpler formula, which is easier to manipulate and transform when necessary (as we will see

many times in the course), in this course we want to work with continuously compounded interest

rates (which is also the one most commonly used in practice).

To summarize, an amount A invested for t years accruing a yearly interest of r com-

pounded continuously, yields at the end of this period ￡Aert.

As a closing remark for this section, note that the same payment of interest can be代 写MAS362 、JAVA/C++
代做程序编程语言 described

usingdifferentinterest-compoundingconventions. Forexample,adepositof￡100yieldingabalance

of ￡110 in one year pays

? 10% annual interest compounded yearly,

√

? 2( 1.1?1)≈9.76% annual interest compounded every six months,

? ln1.1≈9.53% annual interest compounded continuously.

(cid:18) 1(cid:19)n

1Recallthat lim 1+ =e.

n→∞ n

2. PRESENT VALUE 11

(Quick Exercise: verify the claims in the above example.)

Unless stated otherwise, we always assume that interest is compounded continu-

ously.

2. Present value

The notion of interest is linked to another important notion: present value.

Definition. The present value of apayment occurring in the future, isthe present price of the

entitlement to that payment.

Suppose that a deposit of ￡A yields ￡B when we withdraw it in t years (with A 1.03?10 for this certificate. We believe that

thispriceis“toohigh”,soaccordingtoourguidingprincipleforsomethingthatispriced“toohigh”,

we issue such a certificate, sign it, and sell it to them for ￡A. Then we deposit A in the bank, and

since the interest rate is 3%, we will collect A×1.0310 > 12 after 10 years (that’s the capital for a

principal deposit of A). At the same time (this is after 10 years), they will come to us and show us

the certificate we issued. We are under the obligation to pay them ￡1, and so we do. But notice:

our capital in the bank after 10 years is A×1.0310, and we have to pay the holder of the certificate

￡1, so we pocket the profit A×1.0310?1>0.

2usingtheassumptionA>1.03?10 andrearranging

12 1. INTEREST, PRESENT VALUE AND BONDS

Case 2: Now assume that people are willing to pay A 0 (collect 1, pay A×1.0310 >0 and

pocket the positive difference.)

In both cases, a guaranteed profit was achieved with no investment whatsoever; a free lunch!

This contradicts our assumption that there are no arbitrage opportunities in the market, which

implies that A=1.03?10 ≈0.74 pounds. Consequently, the present value of ￡1 paid 10 years from

now is 1.03?10.

Example. An annuity is a sequence of finitely many payments of a fixed amount due at equal

time intervals. An example of this can be a mortgage, which is a loan given with some asset held as

a “security” for the loan. If you want to buy a house, you can ask to get a mortgage, which is the

loan to buy the house; if you don’t repay the loan you will lose your house.

Consider a ￡100,000 mortgage paying a fixed annual interest rate of 6% which is compounded

monthly. What are the monthly repayments if the mortgage is to be repaid in 20 years?

The loan will be repaid as a sequence of finitely many payment of a fixed amount every month.

Call this monthly repayment P, which is this number we seek to calculate. We can find the value

of P in two steps.

First, let’s ask ourselves how much is the bank willing to pay you now in order to receive ￡P

in m months? (e.g. ￡P in 3 months; it’s always the same amount P that the bank will receive).

Basically, we are looking for the present value of ￡P in m months. Under monthly periodic com-

pounding at a fixed annual rate of 6%, ￡1 now will be worth ￡(cid:0) 1+ 0.06(cid:1)m in m months4 therefore

12

the present value of ￡P in m months is clearly P ×(cid:0) 1+ 0.06(cid:1)?m .

12

This means in particular, that an amount of ￡P in 1 month has a present value of P ×

(cid:0) 1+ 0.06(cid:1)?1 , an amount of ￡P in 6 months has a present value of P ×(cid:0) 1+ 0.06(cid:1)?6 , etc. In other

12 12

words, the present value is exactly how much the bank is willing to pay now in order to receive ￡P

in m months.

The second step, is to now find the present value of all such monthly payments of ￡P for 20

2 (cid:88)0×12 (cid:18) 0.06(cid:19)?m

years. This is P 1+ and we must have

12

m=1

(cid:88)240 (cid:18) 0.06(cid:19)?m (cid:88)240 (cid:18) 200(cid:19)m

100,000=P 1+ =P

12 201

m=1 m=1

3exactlyasbeforeusetheassumptiononAandrearrange

4thinkofdepositing￡1inthebankandcollectinginterestattheprescribedrate

3. BONDS 13

The latter is a geometric sum that we can explicitly calculate; then solving for P :

100,000 100,000 100,000

P = = = ≈716.43,

(cid:80)240 (cid:0)200(cid:1)m 2001?(200/201)240 200(cid:16) 1?(cid:0)200(cid:1)240(cid:17)

m=1 201 201 1/201 201

which is how much you will be paying the bank every month for the next 20 years.

3. Bonds

The money market consists of risk-free securities. An example is a bond, which is a financial

security promising the holder a sequence of guaranteed future payments. Risk-free here means that

these payments will be delivered with certainty.

Definition. A bond is a contract in which the issuer commits to pay the holder of the bond

payments of certain amounts on certain dates.

Typically, a bond would specify

? a maturity date, which is the date when final payments are made,

? a face value, which is an amount paid on the maturity date, and

? coupons: a sequence of payments by the issuer, their amounts and payment dates.

In effect, the person or institution who buys the bond is lending money to the bond writer.

Bonds are issued mainly by governments and corporations often in auctions, and can be traded

in exchanges (sometimes referred to as secondary markets). There are many kinds of bonds, like

treasurybillsandnotes,mortgageanddebenturebonds,commercialpapers,andotherswithvarious

arrangements concerning the issuing institution, duration, number of payments, embedded rights

and guarantees. 5

Example. Suppose that we have a bond with face value of ￡100, paying 6% annual interest,

with 2 years to maturity and with semi-annual coupons.

This means that the bond pays the holder 6% of the face value (0.06×100=6) in two install-

mentseveryyear(becauseithassemi-annualcoupons),whichmeansthatitpays￡3every6months.

Consequently, this bond entitles its owner to the following payments:

￡3 in 6 months (first coupon payment),

￡3 in 12 months (second coupon payment),

￡3 in 18 months (third coupon payment), and

￡3+100 in 24 months (fourth -and last- coupon payment plus face value since we have reached the

maturity date).

The simplest case of a bond is a zero-coupon bond, which involves just a single payment. (In

practice, this is not very common, but it is useful for theoretical purposes.)

Definition. A zero coupon bond has no coupons, i.e., the issuer makes only one payment: the

face value is paid at the maturity of the bond.

ThepriceP ofa￡1facevaluezerocouponbondwithmaturityintyearsispreciselytheamount

of money you are willing to pay now in order to be receive ￡1 in t years. So P is the present value

of ￡1 paid t years into the future.

5YoucanfinddescriptionsofbondsissuedbytheUKgovernmenthere.

14 1. INTEREST, PRESENT VALUE AND BONDS

Proposition 1. Let P be the price of a zero-coupon bond with face value ￡1 and maturing in

t years. Let r be the (continuously compounded) interest rate for t-year deposits and loans. Then

P =e?rt.

In proving this statement we will make our usual assumption about the world: there are no

arbitrage opportunities. We also assume that everyone can issue bonds, lend and borrow money

under the same terms (these assumptions certainly don’t apply to you and me, but they do apply

approximately to stable governments and large corporations).

Proof. We will consider two cases (higher/lower and argue by contradiction)

If P >e?rt 6,

? issue a zero-coupon bond with face value of ￡1 and maturing in t years, sell it, and collect

its price ￡P,

? deposit ￡P for t years earning a (continuously compounded) interest rate of r,

? wait t years,

? collect the balance of your deposit amounting to Pert,

? pay the owner the face value of the bond you issued amounting to ￡1,

? pocket Pert?1>0.

This strategy, which required no initial investment and produced a certain profit, is an arbitrage

strategy, which we assume cannot exist.

If P

? borrow ￡P for t years; this will earn the lender a (continuously compounded) interest rate

of r,

? use these ￡P to buy a zero-coupon bond with face value of ￡1 and maturing in t years,

? wait t years,

? receive the face value of your bond amounting to ￡1,

? repay the balance of your loan amounting to Pert,

? pocket 1?Pert >0.

This is another arbitrage strategy, which we assume not to exist.

Since both inequalities cannot occur, we are forced to deduce that P =e?rt. □

4. Discount and yield curves

Definition (Discount curves and yield curves). A discount curve is a function of time P(t)

whose value at any t ≥ 0 is the present value of one unit of currency paid in t years. Equivalently,

P(t) is the price of a zero coupon bond with face value 1 maturing in t years.

A yield curve is a function Y(t) whose value at any t > 0 is the interest rate paid on t-year

deposits.

The values of Y(t) are also called spot (interest) rates or yields. 8

6wethinkthisishighsowe“sell”tomakeprofit

7wethinkthisislowsowe“buy”hopingtosellhighertomakeprofit

8YoucancheckwhatisthecurrentUKyieldcurvehere.

4. DISCOUNT AND YIELD CURVES 15

With these definitions, we can rephrase Proposition 1 in the previous section as,

P(t)=e?Y(t)t.

Yield curves are not directly observable – these are constructed by finding interest rates which

fit observed prices of assets whose prices depend on interest rates (e.g., bonds) and obtaining Y(t)

from these interest rates by linear interpolation9. This process is often called the bootstrap method.

So far, we valued bonds under the assumption that their issuers will make the payments they

contracted to make. In real life this is not always the case: e.g., banks go bankrupt 10 and govern-

ments default on their debt. 11 The price of bonds and the rates of deposit reflect this: risky bonds

arecheaper anddepositsinshakybankspayhigher interest. Thesameistrueofsecuredloans,e.g.,

mortgages, compared to non-secured loans.

Henceforth when working with interest rates we will disregard risk. We always assume that for

everycurrencythereexistsarisk-freeinstitutionissuingbondsinthatcurrencyandouryieldcurves

and discount factors will refer to these bonds. We also assume that everyone can both deposit and

borrow any amount of cash for any maturity date at these risk-free rates. (Don’t try to tell that to

your bank manager.)

4.1. Constructing yield curves: the bootstrap method. We now describe a method of

producing yield curves based on the prices of bonds illustrated in the following example.

Consider the following bonds with semi-annual coupons:

Face value (￡) Maturity (years) Annual interest Price

100 0.25 0 98.3

100 0.5 0 96.5

100 1 0 93.7

100 1.5 4 95.5

100 2 6 97.2

The bond in the first line will have no coupon payments (since 0×100/2=0), we can therefore

see it as a zero coupon bond, and so P(t), which is the price of a zero coupon with face value ￡1

maturing in 0.25 years will be P(0.25)=0.983. Since P(t)=e?Y(t)t, we can immediately calculate

the spot rate Y(0.25)=?ln0.983 ≈6.86%.

0.25

Arguing in exactly the same way:

P(0.5)=0.965, Y(0.5)≈7.13%

P(1)=0.937, Y(1)≈6.51%.

After that, it becomes more interesting. Annual interest of 4% and face value ￡100 means that

the owner of the bond is due 0.04 × 100 = 4 every year, and since they are getting 2 coupon

payments per year, every coupon payment produces ￡2, and the owner will get these coupon

payments in 6,12, and 18 months (semi-annual coupons). But a ￡2 in 6 months is worth now

￡2e?r0.5 = 2e?Y(0.5)0.5(present value). This is however nothing but 2P(0.5)12. Similarly, the ￡2-

coupon payment we will get in one year is worth 2P(1) now. At the 18 month mark, which is

9thismeansthatgivenpoints(t1,Y(t1)),(t2,Y(t2))wewillfindthelinethatgoesthroughbothofthemanduse

theequationofthislineastheformulaforY(t)fort∈[t1,t2].

10E.g.,the Icelandbankcrisis.

11E.g., Russiandebtdefault

12formulaconnectingPandY

16 1. INTEREST, PRESENT VALUE AND BONDS

the maturity time for this bond, the owner will get the last coupon payment and the price of

the face value, i.e., ￡102, whose present value is 102e?Y(1.5)1.5 = 102P(1.5). This means that the

price we are willing to pay now in order to get this face value along with the coupon payments is

2P(0.5)+2P(1)+102P(1.5), therefore,

2P(0.5)+2P(1)+102P(1.5)=95.5

and since we have already calculated P(0.5),P(1), solving for P(1.5) we obtain P(1.5) ≈ 0.89898

and Y(1.5)≈7.10%.

We argue in exactly the same way for the bond on the 5th line (now the time to maturity is 2

years and we will get 4 coupon payments):

3P(0.5)+3P(1)+3P(1.5)+103P(2)=97.2 and solving for P(2) we obtain

P(2)≈0.8621073672, Y(2)≈7.42%.

Throughout the previous example we thought of P(t) as both the present value of one unit of

currency paid in t years, and as the price of a zero coupon bond with face value 1 maturing in t

years.

5. Forward rates

Definition. Aforward rate agreement isacontractinwhichonepartyagreestopaytheother

party a pre-specified interest rate on a deposit occurring during a specified period of time in the

future.

The point is that we want to agree now for the rate of a future deposit/loan.

Let’s say that you plan to deposit ￡1 t years from now and to withdraw the balance t years

1 2

from now (t > t ), but you would like to agree now on the interest rate r for this deposit. Of

2 1 12

course,themostnaturalquestionwouldbetoaskwhat this rate r should be. Letthespotinterest

12

rates for t and t year deposits be r and r respectively. One option you have is to deposit your

1 2 1 2

￡1 for t

1

years at r 1; after t

1

years you will have 1×er1t1. You could then deposit your balance at

the pre-agreed rate r

12

for t 2?t

1

years. At the end of t

2

years you will have er1t1er12(t2?t1).

A second option available to you is to just deposit ￡1 for t

2

years; balance =1×er2t2.

Intuitively, we woul         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com

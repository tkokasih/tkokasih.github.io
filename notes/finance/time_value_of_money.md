# Cash Flow Diagram

> **WARNING**: This is **my** mental model with **my own language**. Proceed with care.
> 
> Example: there is no such thing as *distortion field* in finance literature (AFAIK), nor financial instrument == tunnel to send money between past, present and future.

## Basics
* x-axis: time
* Arrow up: money put into the account
* Arrow down: money taken out of the account

## Examples
* Put money $100.00 to a bank account, and take out $120.00 in 5 years:
  ```
  Wallet
  ======
                               120      pv: -100
                               ^        fv: 120
                               |        n : 5
      o----1----2----3----4----5
      |
      v
      100

  Bank Account
  ============ (Note this is the reverse of Wallet account)

      100                                pv: 120
      ^                                  fv: -120
      |                                  n : 5
      o----1----2----3----4----5
                               |
                               v
                               120
  ```

* Put money $100.00 to bank account, per year, for 5 years, starting today; receive $518.74 at year 5
  ```
  Wallet
  ============
                            518.74       pv : 0
                            ^            pmt: -100 (beginning of period, TODO: CHECK this)
                            |            n  : 5
   0----1----2----3----4----5            fv : 518.74
   |    |    |    |    |
   v    v    v    v    v
   100  100  100  100  100  
  ```

* Put money $10,000.00 now and receive $100 for eternity
  ```
  Wallet
  ======
       100  100  100  100  100  100  100  100  100             pv : -10,000
       ^    ^    ^    ^    ^    ^    ^    ^    ^               pmt: 100
       |    |    |    |    |    |    |    |    |               n  : infinity
  0----1----2----3----4----5----6----7----8----9---- ...       fv : :shrug:
  |
  v
  10,000.00
  ```
* Get money today for 1,000. Pay 202 per month for 5 months.
  ```
  Wallet
  ======
  1,000                                  pv : 1,000
   ^                                     pmt: -202
   |                                     n  : 5
   0----1----2----3----4----5            fv : 0
        |    |    |    |    |
        v    v    v    v    v
        202  202  202  202  202
  ```

## Time Value of Money
### Rate
* Moving money from present to future or vice-versa involve a "distortion field" called "rate"
  * depending on context, rate can be inflation, interest, rate of return, etc.
* This is **Time Value of Money**
* Examples:
  * Current money (n=0) of $100 is "equivalent" with $102 in 1 year (n=1) under "distortion field"/rate of 2%
  * Same money (n=0) of $100 is "equivalent" with $108 in 1 year (n=1) under "distortion field"/rate of 8%
  * The following are tables of this "equivalence"
    | n   | rate=2% | rate=3% | rate=5% | rate=8% |
    |-----|---------|---------|---------|---------|
    |   0 |  100.00 |  100.00 |  100.00 |  100.00 |
    |   1 |  102.00 |  103.00 |  105.00 |  108.00 |
    |   2 |  104.04 |  106.09 |  110.25 |  116.64 |
    |   3 |  106.12 |  109.27 |  115.76 |  125.97 |
    |   5 |  110.41 |  115.93 |  127.63 |  146.93 |
    |   8 |  117.17 |  126.68 |  147.75 |  185.09 |
    |  10 |  121.90 |  134.39 |  162.89 |  215.89 |
    |  15 |  134.59 |  155.80 |  207.89 |  317.22 |
    |  20 |  148.59 |  180.61 |  265.33 |  466.10 |
* Financial instruments are like tunnels (with distortion field) to send money between present and future.
  * You have loads of money now that you don't need: send it through a tunnel to receive it in the future, be it in form of cash, savings, stocks, equity, bonds, gold, foreign currency, etc.
  * You need a lot of money to pay for a big expense now and decide that future you will send your future money to now: find a tunnel that can channel your future money: loan, mortgage, etc.
  * There are many tunnels to choose from, with different characteristics (reliability, ability to take out your money mid-flight, guaranteed/constant/variable/pegged-to-something distortion field, etc.)
  * If you are in financial industry, you can create new kind of tunnels with desired characteristics.
    * You can go as weird as inverse distortion field gradient (like [inverse ETF](https://www.investopedia.com/terms/inverse-etf.asp)), or
    * Tranching variable cash flow to achieve more stable constant cash flow and dumping the junk [aka Credit Tranching](https://www.investopedia.com/terms/c/credit-tranche.asp).
    * F*, you can even combine some weird instruments into another instruments,
  like [CDO-Squared](https://en.wikipedia.org/wiki/CDO-Squared),
  [CDO-Cubed](https://www.investopedia.com/terms/c/cdo3.asp) and contribute to global financial meltdown [like 2007-2008](https://en.wikipedia.org/wiki/Financial_crisis_of_2007-2008)
    * Or even buying and selling people's life insurance, e.g. [life insurance secondary market](https://www.google.com/search?q=life+insurance+secondary+market).
    * Instrument to distance a company with some actions, aka [Special Purpose Vehicle](https://en.wikipedia.org/wiki/Special-purpose_entity). (This one can be motivated other than financial, e.g. legal and stuff)
    * Something out of nothing, like [Non Fungible Token, NFT](https://en/wikipedia.org/wiki/Non-fungible_token).
* Anecdotal story
  * If You give me 100, I will give back 120.
    * This statement is missing at least two critical information to decide:
      * **WHEN** the 120 will be returned. If it is immediate, with no risk, that is a "too good to be true", if it is in 100 years, meh.
      * **WHAT** risk is this 120?
# Tutorials

## Compare
Imagine you're looking to buy a house. You'll most likely need to take out a mortgage to be able to afford it, but with so many different firms offering, you're not sure who to go with. Say you want to take out a loan of £100,000, and are looking at paying it back over 25 years, the standard maturity time. Using mortgage.compare we can obtain a comparison of prices from 4 of the top UK banks. First import mortgage:
```python
import mortgage
```
Now we insert our variables in to the compare function of the mortgage library. 'amount', the size of the mortgage we take out is 100000, while 'length', the number of years the mortgage lasts is 25.
```python
mortgage.compare(100000, 25)
```
This should produce 8 different results, 2 for each of the banks we are looking at. The first result isn't important now but will be used a lot later, while the second is the estimated cost to you of the mortgage.

## Cost
Similar to the compare function, mortgage.cost also provides an estimate of the price of mortgage, but this time with 3 variables. cost can be used if, like with compare, you know how much you want to take out, and the time period over which you wish to pay it back. However, cost is used if you are offered a fixed-rate mortgage, i.e. the interest rate doesn't change over the length of the mortgage. Although more rare than the variable rates used in compare, these do exist.

Using the same numbers as before, you may want a £100,000 mortgage over 25 years, but paid back at a rate of 4.5%. 'amount' and 'length' remain at 100000 and 25 respectively, but a third variable 'rate' takes the value of 4.5. Inserting these in to cost should give us an exact price of the mortgage:
```python
mortgage.cost(100000, 25, 4.5)
```
From here on is where the first number from the compare function becomes useful. The first number is what the equivalent rate would be if the mortgage were a fixed-rate rather than variable. For example, if the compare function tells you that Principality will be the cheapest option with a fixed-rate equivalent of 4.5%, all functions from herm this point should take a 'rate' value of 4.5. This is because the calculations would be much more complex if you were to input two different rates, but would still return the same outputs.

## Monthpay
monthpay is very similar to cost in that it takes the same 3 variables, but rather than the overall cost of the mortgage, it returns the average monthly cost of the repayment. While not you will not pay back this exact amount every month, as the rate of repayment varies slightly over the term, this is simply the average.

With the same 3 variables as with the cost function, we will essentially get cost divided by the number of months:
```python
mortgage.monthpay(100000, 25, 4.5)
```

## Available
Similar to available, monthavailable is used to give you an estimate for the maximum mortgage you can take out. However, instead of inputting your aim for total repayment, you input the average amount you are willing to pay back per month, the length of the mortgage you want to take out, and the interest rate. For example if you are willing to pay about(as this value will vary slightly over the length of the term) £550 a month for 25 years at 4.5% you would input 'monthly_budget' as 550, 'length' as 25, and 'rate' as 4.5:
```python
mortgage.monthavailable(550, 25, 4.5)
```

## Remainpay
The remainpay function is a way of letting you know how far along your mortgage repayments you are. For example if you take out a £100000 mortgage for 25 years at 4.5%, and are 2 and a half years in, you would input 'months_paid' as 30 (2 and a half years in months), 'amount' as 100000, 'length' as 25, and 'rate' as 4.5, and remainpay would tell you how much you have left to repay:
```python
mortgage.remainpay(30, 100000, 25, 4.5)
```

## Yearplan
The yearplan function helps give you a schedule of how far along your repayments you will be after every year of your mortgage, i.e. for a 25 year mortgage it will print your remaining repayment at the end of each of the 25 years. In this example we will use 'amount' of 100000, over 25 years, so 'length' is 25, at a 'rate' of 4.5:
```python
mortgage.yearplan(100000,25,4.5)
```

## LTV
The ltv function returns something called the Loan-to-Value of a mortgage. This is the mortgage amount expressed as a percentage of the value of the house, and can affect the interest rate you are offered, with firms sometimes willing to offer a cheaper mortgage if you put a greater down-payment on the house.

For a house worth £12,0000, you may put a down-payment of £20,000, leading to having to take a mortgage of £100,000. For this example you would input the variable 'down_payment' as 20000, and the 'value' as 120000:
```python
mortgage.ltv(20000, 120000)
```

## Fixed_rate
This function is the engine of the *compare* function. Almost all mortgage companies will quote you two separate rates: a fixed initial rate and a separate variable rate. The initial rate is often much lower than the variable, as it only applies for the first two years or so. This benefits the issuer as they've just spent a huge amount of money on the down payment, so keeping interest low is vital. 

However, it is very difficult to compare two different interests over different periods of time. So, this function allows you to input the two separate rates and how long they apply for respectively. This will give you an overall cost of the mortgage after maturity, alongside **one** rate for comparison, which is comprised of the two rates over the contract.
```python
mortgage.fixed_rate(150000,1.6,26,4.99,274)
```
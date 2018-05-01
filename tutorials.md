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
# Mortgage library
A library that helps first time property buyers with their *mortgages*. There are a huge amount of figures, rates, clauses etc. that come with a standard quote for a mortgage. This can often be very daunting to a first time buyer, especially with no knowledge of the housing market. Our library helps these people to understand these figures as much as possible, be it the overall cost of repayment, the suggest maximum mortgage based on a monthly budget estimate, or the LTV of the mortgage. We also provide a service to compare the rates of four of the biggest and most common banking societies in the UK, to give an **unbiased** opinion on which deal is the best for you.

## Usage
- mortgage.**compare**(*mortgage amount*,*length of contract(years)*) - A function that compares a number of mortgage quotes from banking societies, given two separate rates (fixed/variable), giving you strictly the cheapest option.

- mortgage.**cost**(*mortgage amount*,*length of contract(years)*,*mortgage rate*) - A function that returns the overall cost of the mortgage, after interest.

- mortgage.**monthpay**(*mortgage amount*,*length of contract(years)*,*mortgage rate*) - A function that returns the monthly cost of the mortgage payback, dependent on the maturity date of the contract.

- mortgage.**available**(*mortgage amount*,*length of contract(years)*,*mortgage rate*) - A function that tells you how big a mortgage you can afford to take out, given your overall budget and a mortgage rate/maturity.

- mortgage.**monthavailable**(*mortgage amount*,*length of contract(years)*,*mortgage rate*) - A function that tells you how big a mortgage you can afford to take out, given your monthly budget and a mortgage rate/maturity.

- mortgage.**remainpay**(*months paid*,*mortgage amount*,*length of contract*,*mortgage rate*) - A function that tells you how much of the principal you have to pay of your mortgage.

- mortgage.**yearplan**(*mortgage amount*,*length of contract(years)*,*mortgage rate*) - A function that returns a yearly schedule of the principal you have left to pay.

- mortgage.**ltv**(*down payment*,*value of property*) - A function that returns the fixed rate for comparison , based on an initial and then variable mortgage rate, and also the overall cost of the mortgage.

- mortgage.**fixed_rate**(*mortgage amount*,*initial rate*,*length with initial rate(months)*,*second rate*,*length with second rate(months)*) - A function that returns the fixed rate for comparison , based on an initial and then variable mortgage rate, and also the overall cost of the mortgage.

## Examples
(*Before all following functions, ```install mortgage```
 , is required*)

- ```python
    mortgage.compare(300000,24)

        Barclays:     (4.404, '£486489.95')
        HSBC:         (3.834, '£459342.73')
        Principality: (3.685, '£452417.47')
        RBS:          (3.598, '£448391.81')
        RBS
    ```

- ```python
    mortgage.ltv(25000,212000)

        88.21 %
        88.20754716981132 
    ```

- ```python
    mortgage.fixed_rate(220000,1.1,18,5.6,282)
        
        £ 387487.64
        5.043
    ```

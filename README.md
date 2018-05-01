# Mortgage library
A library that helps first time property buyers with their *mortgages*.

## Usage
- mortgage.**compare**(*mortgage amount*,*length of contract*) - A function that compares a number of mortgage quotes from banking societies, given two separate rates (fixed/variable), giving you strictly the cheapest option.

- mortgage.**cost**(*mortgage amount*,*length of contract*,*mortgage rate*) - A function that returns the overall cost of the mortgage, after interest.

- mortgage.**monthpay**(*mortgage amount*,*length of contract*,*mortgage rate*) - A function that returns the monthly cost of the mortgage payback, dependent on the maturity date of the contract.

- mortgage.**available**(*mortgage amount*,*length of contract*,*mortgage rate*) - A function that tells you how big a mortgage you can afford to take out, given your overall budget and a mortgage rate/maturity.

- mortgage.**monthavailable**(*mortgage amount*,*length of contract*,*mortgage rate*) - A function that tells you how big a mortgage you can afford to take out, given your monthly budget and a mortgage rate/maturity.

- mortgage.**remainpay**(*months paid*,*mortgage amount*,*length of contract*,*mortgage rate*) - A function that tells you how much of the principal you have to pay of your mortgage.

- mortgage.**yearplan**(*mortgage amount*,*length of contract*,*mortgage rate*) - A function that returns a yearly schedule of the principal you have left to pay.

- mortgage.**ltv**(*down payment*,*value of property*) - A function that returns the fixed rate for comparison , based on an initial and then variable mortgage rate, and also the overall cost of the mortgage.

- mortgage.**fixed_rate**(*mortgage amount*,*initial rate*,*length with initial rate*,*second rate*,*length with second rate*) - A function that returns the fixed rate for comparison , based on an initial and then variable mortgage rate, and also the overall cost of the mortgage.

## Examples
(*Before all following functions, ```install mortgage```, is required*)

- ```mortgage.compare(300000,24)```
    Barclays:     (4.404, '£486489.95')
    HSBC:         (3.834, '£459342.73')
    Principality: (3.685, '£452417.47')
    RBS:          (3.598, '£448391.81')

    RBS
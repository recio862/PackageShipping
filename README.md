PackageShipping
===============

Process postal shipping packages

===============

Postal Packages

Shipping requirements

    The package weight must not exceed 50 pounds.
    The package must not exceed 3 feet in length, width, or height.
    The girth of the package must not exceed 5 feet. The girth is the circumference around the two smallest sides of the package. If side1, side2, and side3 are the lengths of the three sides, and largest is the largest of the three sides, then the girth can be calculated using:
    girth = 2 * ( side1 + side2 + side3 - largest ) 

For each transaction (package to be shipped), the user should enter the package weight followed by the 3 package dimensions in any order. The weight should be specified as a whole number of pounds and the dimensions are specified as a whole number of inches.

To end the program, the user should enter a weight of -1. When the user enters -1 to end the program, they should not have to enter values for the 3 package dimensions. That is, when the user is ready to end the program, they should only have to enter the weight:


The distribution of shipping charges for weigh goes as follows (maps weight to nearest whole number if number is not specified on the chart)

Weight      Shipping Charge

1           1.50

2           2.10

3           4.00

5           6.75

7           9.90

10          14.95

13          19.40

16          24.20

20          27.30

25          31.90

30          38.50

35          43.50

40          44.80

45          47.40

50          55.20


=======================
Output


For each transaction, it will print:

    the transaction number 
    whether the package was accepted or rejected
    the package weight
    the cost for shipping (if applicable) 

When the program ends, it will print the number of packages accepted for shipping and the number of packages rejected. Transactions that contain invalid input will not be counted.




 

Query the sum of the populations for all Japanese cities in CITY. The COUNTRYCODE for Japan is JPN.

Input Format

The CITY table is described as follows:
       
       |City|
| Field         |  Type            |
| ID            | NUMBER 
| NAME          | VARCHAR2(17)
| COUNTRYCODE   | VARCHAR2(3)
| DISTRICT      | VARCHAR (20)
| POPULATION    | NUMBER

SELECT SUM(POPULATION) FROM CITY WHERE COUNTRYCODE = 'JPN';


Query the difference between the maximum and minimum populations in CITY.

Input Format

The CITY table is described as follows:

      
       |City|
| Field         |  Type            |
| ID            | NUMBER 
| NAME          | VARCHAR2(17)
| COUNTRYCODE   | VARCHAR2(3)
| DISTRICT      | VARCHAR (20)
| POPULATION    | NUMBER

SELECT MAX(POPULATION) - MIN(POPULATION) AS DIFFERENCE FROM CITY;

#NEW QUESTION NAMED BLUNDER

Samantha was tasked with calculating the average monthly salaries for all employees in the EMPLOYEES table, but did not realize her keyboard's  key was broken until after completing the calculation. She wants your help finding the difference between her miscalculation (using salaries with any zeros removed), and the actual average salary.

Write a query calculating the amount of error (i.e.:  average monthly salaries), and round it up to the next integer.

Input Format

The EMPLOYEES table is described as follows:



Note: Salary is per month.

Constraints

.

Sample Input



Sample Output

2061
Explanation

The table below shows the salaries without zeros as they were entered by Samantha:



Samantha computes an average salary of . The actual average salary is .

The resulting error between the two calculations is . Since it is equal to the integer , it does not get rounded up.

select ceil(avg(salary)-avg(replace(salary,0,''))) from EMPLOYEES;
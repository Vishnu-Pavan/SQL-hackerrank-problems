### **[Type of Triangle](https://www.hackerrank.com/challenges/what-type-of-triangle/problem?isFullScreen=true)**

Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. Output one of the following statements for each record in the table:

Equilateral: It's a triangle with 3 sides of equal length.
Isosceles: It's a triangle with 2 sides of equal length.
Scalene: It's a triangle with 3 sides of differing lengths.
Not A Triangle: The given values of A, B, and C don't form a triangle.

Input Format
The TRIANGLES table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/ceed457a-5ad4-4f7a-b404-38cbd54b2c8e)

Each row in the table denotes the lengths of each of a triangle's three sides.

Sample Input

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/fb34c745-3194-4e68-970c-da7ae4ef842b)

Sample Output

Isosceles
Equilateral
Scalene
Not A Triangle

Explanation

Values in the tuple (20,20,23) form an Isosceles triangle, because A=B.
Values in the tuple (20,20,20) form an Equilateral triangle, because A=B=C . Values in the tuple (20,21,22) form a Scalene triangle, because A!= B!= C.
Values in the tuple (13,14,30) cannot form a triangle because the combined value of sides  and  is not larger than that of side C.

**Solution**
```sql
SELECT 
CASE 
    WHEN A+B <= C or B+C<=A or A+C<=B then 'Not A Triangle' 
    WHEN A = B AND B = C THEN 'Equilateral' 
    WHEN A = B or B = C or A = C THEN 'Isosceles' 
    WHEN A!=B AND B!=C THEN 'Scalene' 
END as type 
FROM TRIANGLES;
```

### **[The PADS](https://www.hackerrank.com/challenges/the-pads/problem?isFullScreen=true)**

Generate the following two result sets:

1.Query an alphabetically ordered list of all names in OCCUPATIONS, immediately followed by the first letter of each profession as a parenthetical (i.e.: enclosed in parentheses). For example: AnActorName(A), ADoctorName(D), AProfessorName(P), and ASingerName(S).
2.Query the number of ocurrences of each occupation in OCCUPATIONS. Sort the occurrences in ascending order, and output them in the following format:

There are a total of [occupation_count] [occupation]s.

where [occupation_count] is the number of occurrences of an occupation in OCCUPATIONS and [occupation] is the lowercase occupation name. If more than one Occupation has the same [occupation_count], they should be ordered alphabetically.

Note: There will be at least two entries in the table for each type of occupation.

Input Format

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/82195aea-4371-4698-8866-2b1c37f9b36e)

Occupation will only contain one of the following values: Doctor, Professor, Singer or Actor.

Sample Input

An OCCUPATIONS table that contains the following records:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/24c1d5a8-7de9-4b57-ad4e-6f72818ccc86)

Sample Output

Ashely(P)
Christeen(P)
Jane(A)
Jenny(D)
Julia(A)
Ketty(P)
Maria(A)
Meera(S)
Priya(S)
Samantha(D)
There are a total of 2 doctors.
There are a total of 2 singers.
There are a total of 3 actors.
There are a total of 3 professors.
Explanation

The results of the first query are formatted to the problem description's specifications.
The results of the second query are ascendingly ordered first by number of names corresponding to each profession (2<=2<=3<=3), and then alphabetically by profession (doctors <= singers, and actors <= professors).

**Solution**
```sql
select 
    CONCAT(name,"(",SUBSTRING(occupation, 1, 1),")" ) 
from OCCUPATIONS 
ORDER BY name;

select 
    CONCAT("There are a total of ",count(*)," ",LOWER(occupation),"s.") 
from OCCUPATIONS 
group by occupation
ORDER BY count(*) ASC, occupation;
```

### **[Occupations](https://www.hackerrank.com/challenges/occupations/problem?isFullScreen=true)**

Pivot the Occupation column in OCCUPATIONS so that each Name is sorted alphabetically and displayed underneath its corresponding Occupation. The output column headers should be Doctor, Professor, Singer, and Actor, respectively.

Note: Print NULL when there are no more names corresponding to an occupation.

Input Format

The OCCUPATIONS table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/20fbff55-20c5-4955-9ac1-1043778f3010)

Occupation will only contain one of the following values: Doctor, Professor, Singer or Actor.

Sample Input

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/2b3f4d8a-fc05-4abf-9ce7-23edc32a3330)

Sample Output

Jenny    Ashley     Meera  Jane
Samantha Christeen  Priya  Julia
NULL     Ketty      NULL   Maria
Explanation

The first column is an alphabetically ordered list of Doctor names.
The second column is an alphabetically ordered list of Professor names.
The third column is an alphabetically ordered list of Singer names.
The fourth column is an alphabetically ordered list of Actor names.
The empty cell data for columns with less than the maximum number of names per occupation (in this case, the Professor and Actor columns) are filled with NULL values.

**Solution**
```sql

```

### **[]()**

**Solution**
```sql

```

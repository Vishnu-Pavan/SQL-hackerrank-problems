### **[Revising the Select Query-1](https://www.hackerrank.com/challenges/revising-the-select-query)**
Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.
The CITY table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/906a83c2-19d1-4eaf-b263-2c08b1b535cd)

**Solution**
```sql
Select * from city where countrycode = 'USA' and population >100000;
```

### **[Revising the Select Query II](https://www.hackerrank.com/challenges/revising-the-select-query-2/problem?isFullScreen=true)**
Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.
The CITY table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/19d184dd-77f2-46a5-b30d-de4234b33306)

**Solution**
```sql
Select name from CITY where countrycode = 'USA' and population > 120000;
```

### **[Select All](https://www.hackerrank.com/challenges/select-all-sql/problem?isFullScreen=true)**
Query all columns (attributes) for every row in the CITY table.
The CITY table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/bbd6afb5-9d09-480a-8b7f-d74d18ddbf95)

**Solution**
```sql
Select * from CITY;
```

### **[Select By ID](https://www.hackerrank.com/challenges/select-by-id/problem?isFullScreen=true)**
Query all columns for a city in CITY with the ID 1661.
The CITY table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/2a1e845c-65e3-47f2-bb0e-fdd9e96dd1bc)

**Solution**
```sql
Select * from CITY where ID=1661;
```

### **[Japanese Cities' Attributes](https://www.hackerrank.com/challenges/japanese-cities-attributes/problem?isFullScreen=true)**
Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.
The CITY table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/c6986c1f-344d-4206-a33b-cce1dae17f1d)

**Solution**
```sql
Select * from CITY where countrycode = 'JPN';
```

### **[Japanese Cities' Names](https://www.hackerrank.com/challenges/japanese-cities-name/problem?isFullScreen=true)**
Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.
The CITY table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/684311da-b4bf-4444-9ccf-bbe8a21bce18)

**Solution**
```sql
Select name from CITY where countrycode = 'JPN';
```

### **[Weather Observation Station 1](https://www.hackerrank.com/challenges/weather-observation-station-1/problem?isFullScreen=true)**
Query a list of CITY and STATE from the STATION table.
The STATION table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/dc6492cb-28e5-428a-a202-113ea3e5a5aa)

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
Select CITY , state from STATION;
```

### **[Weather Observation Station 3](https://www.hackerrank.com/challenges/weather-observation-station-3/problem?isFullScreen=true)**
Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.
The STATION table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/f2c67798-5082-42d7-99b7-565ca1ed05c7)

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT DISTINCT CITY FROM STATION WHERE MOD(ID,2)=0 ORDER BY CITY ASC;
```
### **[Weather Observation Station 4]()**
Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.
The STATION table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/5dcdd4cb-5c57-4f4c-afad-27055893d93a)

where LAT_N is the northern latitude and LONG_W is the western longitude.
For example, if there are three records in the table with CITY values 'New York', 'New York', 'Bengalaru', there are 2 different city names: 'New York' and 'Bengalaru'. 
The query returns 1, because total number of city - number of unique city = 3 - 2 = 1.

**Solution**
```sql
select count(city) - count(distinct city) from station;
```

### **[Weather Observation Station 5](https://www.hackerrank.com/challenges/weather-observation-station-5/problem?isFullScreen=true)**
Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.
The STATION table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/9b2f48af-b5d7-40a2-8008-b817977e72c3)

where LAT_N is the northern latitude and LONG_W is the western longitude.

Sample Input
For example, CITY has four entries: DEF, ABC, PQRS and WXY.

Sample Output

ABC 3
PQRS 4

Explanation

When ordered alphabetically, the CITY names are listed as ABC, DEF, PQRS, and WXY, with lengths  and . The longest name is PQRS, but there are  options for shortest named city. Choose ABC, because it comes first alphabetically.

Note
You can write two separate queries to get the desired output. It need not be a single query.

**Solution**
```sql
select city c, length(city) l from station order by l asc,c asc limit 1;
select city c, length(city) l from station order by l desc,c asc limit 1;
```

### **[Weather Observation Station 6](https://www.hackerrank.com/challenges/weather-observation-station-6/problem?isFullScreen=true)**
Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/b81a848e-e271-4670-b1ba-a5ee5b2ffd14)

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
select distinct(city) from station where city like 'A%' or city like 'E%' or city like 'I%' or city like 'O%' or city like 'U%';
```
or
```sql
select distinct(city) from station where substr(city,1,1) in ('A','E','I','O','U');
```

### **[Weather Observation Station 7](https://www.hackerrank.com/challenges/weather-observation-station-7/problem?isFullScreen=true)**
Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/a0c4af75-3897-4a8e-be53-08275b65877b)

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
select distinct(city) from station where city like '%A' or city like '%E' or city like '%I' or city like '%O' or city like '%U';
```

### **[Weather Observation Station 8](https://www.hackerrank.com/challenges/weather-observation-station-8/problem?isFullScreen=true)**
Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/5cb2eaa0-ce8b-4986-aba5-46e2b9691826)

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
select DISTINCT city from station where (city like 'A%' or city like 'E%' or city like 'I%' or city like 'O%' or city like 'U%') and (city like '%A' or city like '%E' or city like '%I' or city like '%O' or city like '%U');
```
or
```SQL
select DISTINCT city from station where left(city,1) in ('a', 'e', 'i', 'o', 'u') and right(city,1) in ('a', 'e', 'i', 'o', 'u');
```

### **[Weather Observation Station 9](https://www.hackerrank.com/challenges/weather-observation-station-9/problem?isFullScreen=true)**
Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/33480ca1-2d7f-40b7-96c7-63a1a90e5555)

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
select DISTINCT city from station where left(city,1) not in ('a', 'e', 'i', 'o', 'u');
```

### **[Weather Observation Station 10](https://www.hackerrank.com/challenges/weather-observation-station-10/problem?isFullScreen=true)**
Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/523db8f0-ff52-4f89-bbbc-927a15d1e7a2)


where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
select DISTINCT city from station where right(city,1) not in ('a', 'e', 'i', 'o', 'u');
```
or
```sql
select DISTINCT city from station where SUBSTR(city, length(city), 1) NOT IN ('A','E','I','O','U');
```
### **[Weather Observation Station 11](https://www.hackerrank.com/challenges/weather-observation-station-11/problem?isFullScreen=true)**
Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/d967a79a-6590-4ac2-91ff-3fd10e1fadb7)

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
select DISTINCT city from station where left(city,1) not in ('a', 'e', 'i', 'o', 'u') or right(city,1) not in ('a', 'e', 'i', 'o', 'u');
```

### **[Weather Observation Station 12](https://www.hackerrank.com/challenges/weather-observation-station-12/problem?isFullScreen=true)**
Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/4f86b3b0-1cec-49c3-b559-550fc33bcd41)

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
select DISTINCT city from station where left(city,1) not in ('a', 'e', 'i', 'o', 'u') and right(city,1) not in ('a', 'e', 'i', 'o', 'u');
```

### **[Higher Than 75 Marks](https://www.hackerrank.com/challenges/more-than-75-marks/problem?isFullScreen=true)**
Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Input Format
The STUDENTS table is described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/aee31aae-ccc1-4582-a632-ba69ecced2ae)

The Name column only contains uppercase (A-Z) and lowercase (a-z) letters.

Sample Input

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/5c2fd7b6-8fc4-4135-9ce8-511e74dc4ca7)

Sample Output

Ashley
Julia
Belvet
Explanation

Only Ashley, Julia, and Belvet have Marks > **75** . If you look at the last three characters of each of their names, there are no duplicates and 'ley' < 'lia' < 'vet'.

**Solution**
```sql
select name from students where marks>75 order by substr(name,length(name)-2,3),id;
```

### **[]()**

**Solution**
```sql

```

### **[]()**

**Solution**
```sql

```

### **[]()**

**Solution**
```sql

```

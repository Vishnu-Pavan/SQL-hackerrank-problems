### **[Population Census](https://www.hackerrank.com/challenges/asian-population/problem?isFullScreen=true)**
Given the CITY and COUNTRY tables, query the sum of the populations of all cities where the CONTINENT is 'Asia'.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

Input Format

The CITY and COUNTRY tables are described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/d5b8563d-d2ad-48ce-a2c5-039e6df0e8be)

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/54fd1535-f908-49ce-9186-b8d3d961ee05)

**Solution**
```sql
SELECT sum(city.population)
FROM city INNER JOIN country 
ON CITY.CountryCode = COUNTRY.Code
WHERE COUNTRY.CONTINENT='Asia';
```

### **[African Cities](https://www.hackerrank.com/challenges/african-cities/problem?isFullScreen=true)**
Given the CITY and COUNTRY tables, query the names of all cities where the CONTINENT is 'Africa'.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

Input Format

The CITY and COUNTRY tables are described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/bbd4ed9d-b766-4a89-9b8a-058e1c055e25)


![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/b5ae768d-eade-49d4-be22-d4c2d2d95b17)

**Solution**
```sql
SELECT city.name
FROM city INNER JOIN country 
ON CITY.CountryCode = COUNTRY.Code
WHERE COUNTRY.CONTINENT='Africa';
```

### **[Average Population of Each Continent](https://www.hackerrank.com/challenges/average-population-of-each-continent/problem?isFullScreen=true)**
Given the CITY and COUNTRY tables, query the names of all the continents (COUNTRY.Continent) and their respective average city populations (CITY.Population) rounded down to the nearest integer.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

Input Format

The CITY and COUNTRY tables are described as follows:

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/661e7b02-dd0e-4d5a-aa20-9b6adf4554b8)

![image](https://github.com/Vishnu-Pavan/SQL-hackerrank-problems/assets/83069735/2b5cdc71-6ad5-4e66-8f73-b98f9891f028)

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

# Introduction to SQL

1.  What makes SQL a nonprocedural language?
    It determines what should be done, but not how it should be done.
 
2.  How can you tell whether a database is truly relational?
    By applying Dr.Codd's 12 (there are 13) rules

3.  What can you do with SQL?
    With SQL you can select, insert, modify, and delete the information in a database. Set user permission on tables and databases and perform system security functions. Within an application, you can handle the online transaction process. Transfer data between different databases. 

4.  Name the process that separates data into distinct, unique sets.
    Normalization reduces how much repetition and the complexity of the structure of the previous level.

5.  Do the following statements return the same or different output:

    SELECT * FROM ARRESTS;
    select * from arrests;

In the syntax of SQL, case sensitivity is normally not a factor. Thus, there is no difference between them. However, when dealing with data, you should be mindful of capitalization.

1.  None of the following queries work. Why not?

    select *;
    The FROM clause is missing.

    Select * from checks
    The semicolon is missing, which identifies the end of the SQL statement.

    Select amount name payee FROM checks;
    A comma is needed between each column name: Select amount, name, payee FROM checks;

1.  Which of the following SQL statements will work?

    select * 
    from checks;
    select * from checks;
    select * from checks
    /
      All of the above work.

Given the following table description for the arrests table: 

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="left" />

<col  class="left" />

<col  class="left" />
</colgroup>
<tbody>
<tr>
<td class="left">nysid</td>
<td class="left">officerId</td>
<td class="left">topCharge</td>
</tr>
</tbody>
</table>

Do the following:

1.  Write a query to return just the check officerId and the topCharge.
     SELECT officerId, topCharge FROM arrests;

2.  Rewrite the query from exercise 1 so that the topCharge will appear
    as the first column in your query results.
    SELECT topCharge, officerId FROM arrests;

3.  Using the arrests table, write a query to return all the unique topCharges.
    SELECT DISTINCT topCharge FROM arrests;

Use the doubleAgents table to answer the following questions.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="left" />

<col  class="left" />

<col  class="right" />

<col  class="right" />

<col  class="left" />

<col  class="right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="left">LASTNAME</th>
<th scope="col" class="left">FIRSTNAME</th>
<th scope="col" class="right">AREACODE</th>
<th scope="col" class="right">PHONE</th>
<th scope="col" class="left">ST</th>
<th scope="col" class="right">ZIP</th>
</tr>
</thead>

<tbody>
<tr>
<td class="left">BUNDY</td>
<td class="left">AL</td>
<td class="right">100</td>
<td class="right">555-1111</td>
<td class="left">IL</td>
<td class="right">22333</td>
</tr>


<tr>
<td class="left">MEZA</td>
<td class="left">AL</td>
<td class="right">200</td>
<td class="right">555-2222</td>
<td class="left">UK</td>
<td class="right">&#xa0;</td>
</tr>


<tr>
<td class="left">MERRICK</td>
<td class="left">BUD</td>
<td class="right">300</td>
<td class="right">555-6666</td>
<td class="left">CO</td>
<td class="right">80212</td>
</tr>


<tr>
<td class="left">MAST</td>
<td class="left">JD</td>
<td class="right">381</td>
<td class="right">555-6767</td>
<td class="left">LA</td>
<td class="right">23456</td>
</tr>


<tr>
<td class="left">BULHER</td>
<td class="left">FERRIS</td>
<td class="right">345</td>
<td class="right">555-3223</td>
<td class="left">IL</td>
<td class="right">23332</td>
</tr>


<tr>
<td class="left">PERKINS</td>
<td class="left">ALTON</td>
<td class="right">911</td>
<td class="right">555-3116</td>
<td class="left">CA</td>
<td class="right">95633</td>
</tr>


<tr>
<td class="left">BOSS</td>
<td class="left">SIR</td>
<td class="right">204</td>
<td class="right">555-2345</td>
<td class="left">CT</td>
<td class="right">95633</td>
</tr>
</tbody>
</table>

1.  Write a query that returns everyone in the database whose last name begins with M.
     SELECT * FROM doubleAgents WHERE LASTNAME LIKE 'M%';

2.  Write a query that returns everyone who lives in Illinois with a first name of AL.
    SELECT * FROM doubleAgents
    WHERE STATE = 'IL'
    AND FIRSTNAME = 'AL';

3.  What shorthand could you use instead of WHERE a >= 10 AND a <=30?
    WHERE a BETWEEn 10 and 30;

4.  What will this query return?

    SELECT FIRSTNAME
    FROM DOUBLE_AGENTS
    WHERE FIRSTNAME = 'AL'
      AND LASTNAME = 'BULHER';
   Nothing will be returned, as both conditions are false.

1.  Using the DOUBLE<sub>AGENTS</sub> table, write a query that returns the following:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="left" />

<col  class="left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="left">NAME</th>
<th scope="col" class="left">ST</th>
</tr>
</thead>

<tbody>
<tr>
<td class="left">AL             FROM</td>
<td class="left">IL</td>
</tr>
</tbody>
</table>
   INPUT:
   SQL > SELECT (FIRSTNAME || 'FROM') NAME, STATE
     2   FROM FRIENDS
     3   WHERE STATE = 'IL'
     4   AND
     5   LASNAME = 'BUNDY';
    
1.  Using the DOUBLE<sub>AGENTS</sub> table, write a query that returns the following:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="left" />

<col  class="right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="left">NAME</th>
<th scope="col" class="right">PHONE</th>
</tr>
</thead>

<tbody>
<tr>
<td class="left">MERRICK, BUD</td>
<td class="right">300-555-6666</td>
</tr>


<tr>
<td class="left">MAST, JD</td>
<td class="right">381-555-6767</td>
</tr>


<tr>
<td class="left">BULHER, FERRIS</td>
<td class="right">345-555-3223</td>
</tr>
</tbody>
</table>
    INPUT:
    SQL > SELECT LASTNAME || ',' || FIRSTNAME NAME,
      2          AREACODE || '-' || PHONE PHONE
      3   FROM   doubleAgents
      4   WHERE AREACODE BETWEEN 300 and 400;

1.  Which function capitalizes the first letter of a character string and makes the rest lowercase?
    INITCAP

2.  Which functions are also known by the *same* name?
    Group functions and aggregate functions are the same thing.

3.  Will this query work?

    SELECT COUNT(LASTNAME) FROM CHARACTERS;
     Yes, it will return the total of rows.
1.  How about this one?

    SELECT SUM(LASTNAME) FROM CHARACTERS
    No, because LASTNAME is a character field.

1.  Assuming that they are separate columns, which function(s) would
    splice together FIRSTNAME and LASTNAME?
    The CONCAT function and the || symbol.

1.  What does the answer 37 mean from the following SELECT?

    SELECT COUNT(*) FROM drone_strikes;
    37 is the number of records in the table. 

1.  Will the following statement work? (Hint: look up substr)

    SELECT SUBSTR LASTNAME,1,5 FROM NAME_TBL;
    No, the () is missing around LASTNAME, 1, 5. The statement should look like: SQL> SELECT SUBSTR(LASTNAME,1,5) NAME FROM NAME_TBL;

Marksmanship table:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="left" />

<col  class="left" />

<col  class="left" />

<col  class="left" />

<col  class="left" />
</colgroup>
<tbody>
<tr>
<td class="left">officerId</td>
<td class="left">FirstName</td>
<td class="left">LastName</td>
<td class="left">hits</td>
<td class="left">shotsTaken</td>
</tr>
</tbody>
</table>

1.  Using a table called SHOOTSTATS table, write a query to determine who is are on target less than .25.
    SQL> SELECT NAME FROM SHOOTSTATS
      2  WHERE (HITS/SHOTSTAKEN) < .25;

2.  Using today's OFFICERS table, write a query that will return the following:

officers table

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="left" />

<col  class="left" />

<col  class="left" />

<col  class="right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="left">First</th>
<th scope="col" class="left">Middle</th>
<th scope="col" class="left">Last</th>
<th scope="col" class="right">BadgeID</th>
</tr>
</thead>

<tbody>
<tr>
<td class="left">Kevin</td>
<td class="left">Anthony</td>
<td class="left">Petrone</td>
<td class="right">32</td>
</tr>
</tbody>
</table>

OUTPUT:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="left" />

<col  class="right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="left">INITIALS</th>
<th scope="col" class="right">CODE</th>
</tr>
</thead>

<tbody>
<tr>
<td class="left">K.A.P.</td>
<td class="right">32</td>
</tr>
</tbody>
</table>
  INPUT:
    SQL> SELECT SUBSTR(FIRSTNAME,1,1)||'.'||
                SUBSTR(MIDDLENAME,1,1)||'.'||
                SUBSTR(LASTNAME,1,1)||'.' INITIALS, code
         FROM OFFICERS
         WHERE code = 32;

1.  Which clause works just like LIKE(<exp>%)? (HINT: Look it up on google.)
    STARTING WITH

2.  What is the function of the GROUP BY clause, and what other clause does it act like?
    The GROUP BY clause groups data result sets that have been manipulated by various functions. The GROUP BY clause acts like the ORDER BY clause in that it orders the results of the query in the order the columns are listed in the GROUP BY.

3.  Will this SELECT work?

    NAME, AVG(SALARY), DEPARTMENT
        FROM PAY_TBL
        WHERE DEPARTMENT = 'SWAT'
        ORDER BY NAME
        GROUP BY DEPARTMENT, SALARY;
   No, the syntax is not correct. The GROUP BY has to come before ORDER BY. The selected columns must also be listed in GROUP BY.

1.  When using the HAVING clause, do you always have to use a GROUP BY also?
    Yes

2.  Can you use ORDER BY on a column that is not one of the columns in the SELECT statement?
    Yes, the SELECT statement is not necessary on a column that is put in the ORDER BY clause.

1.  Using the ORGCHART table from the following examples, find out how many people on each team have 30 or more days of sick leave.
   
Here is your baseline that shows how many folks are on each team.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="right" />

<col  class="left" />

<col  class="left" />

<col  class="left" />

<col  class="right" />
</colgroup>
<tbody>
<tr>
<td class="right">empId</td>
<td class="left">First</td>
<td class="left">Last</td>
<td class="left">Team</td>
<td class="right">Sickleave</td>
</tr>


<tr>
<td class="right">1</td>
<td class="left">Alan</td>
<td class="left">Turing</td>
<td class="left">Algebra</td>
<td class="right">31</td>
</tr>


<tr>
<td class="right">2</td>
<td class="left">John</td>
<td class="left">Von Neuman</td>
<td class="left">PDE</td>
<td class="right">32</td>
</tr>


<tr>
<td class="right">3</td>
<td class="left">Robert</td>
<td class="left">Oppenhiemer</td>
<td class="left">Physics</td>
<td class="right">27</td>
</tr>


<tr>
<td class="right">4</td>
<td class="left">Enrico</td>
<td class="left">Fermi</td>
<td class="left">Physics</td>
<td class="right">24</td>
</tr>


<tr>
<td class="right">5</td>
<td class="left">Leo</td>
<td class="left">Szilard</td>
<td class="left">Physics</td>
<td class="right">37</td>
</tr>


<tr>
<td class="right">6</td>
<td class="left">George</td>
<td class="left">Danzig</td>
<td class="left">Operations</td>
<td class="right">22</td>
</tr>


<tr>
<td class="right">7</td>
<td class="left">Eric</td>
<td class="left">Djkstra</td>
<td class="left">CS</td>
<td class="right">21</td>
</tr>


<tr>
<td class="right">8</td>
<td class="left">Linus</td>
<td class="left">Torvals</td>
<td class="left">CS</td>
<td class="right">36</td>
</tr>


<tr>
<td class="right">9</td>
<td class="left">Richard</td>
<td class="left">Stallman</td>
<td class="left">CS</td>
<td class="right">40</td>
</tr>
</tbody>
</table>

Compare it to the query that solves the question:
INPUT:

    SELECT TEAM, COUNT(TEAM)
    FROM ORGCHART
    WHERE SICKLEAVE >=30
    GROUP BY TEAM;

The output shows the number of people in each TEAM with a SICKLEAVE balance of 30 or more days. 

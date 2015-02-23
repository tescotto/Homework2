# Introduction to SQL

1.  What makes SQL a nonprocedural language?
2.  How can you tell whether a database is truly relational?
3.  What can you do with SQL?
4.  Name the process that separates data into distinct, unique sets.
5.  Do the following statements return the same or different output:

    SELECT * FROM ARRESTS;
    select * from arrests;

1.  None of the following queries work. Why not?

    select *;
    Select * from checks
    Select amount name payee FROM checks;

1.  Which of the following SQL statements will work?

    select * 
    from checks;
    select * from checks;
    select * from checks
    /

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

2.  Rewrite the query from exercise 1 so that the topCharge will appear
    as the first column in your query results.

3.  Using the arrests table, write a query to return all the unique topCharges.

Use the double<sub>agents</sub> table to answer the following questions.

LASTNAME        FIRSTNAME        AREACODE PHONE    ST ZIP
&#x2014;&#x2014;&#x2014;&#x2014;&#x2014; -&#x2014;&#x2014;&#x2014;&#x2014;&#x2014; &#x2013;&#x2014;&#x2014; &#x2013;&#x2014;&#x2014; &#x2013; &#x2014;&#x2014;
BUNDY           AL                    100 555-1111 IL 22333
MEZA            AL                    200 555-2222 UK
MERRICK         BUD                   300 555-6666 CO 80212
MAST            JD                    381 555-6767 LA 23456
BULHER          FERRIS                345 555-3223 IL 23332
PERKINS         ALTON                 911 555-3116 CA 95633
BOSS            SIR                   204 555-2345 CT 95633

1.  Write a query that returns everyone in the database whose last name begins with M.
2.  Write a query that returns everyone who lives in Illinois with a first name of AL.
3.  What shorthand could you use instead of WHERE a >= 10 AND a <=30?
4.  What will this query return?

    SELECT FIRSTNAME
    FROM DOUBLE_AGENTS
    WHERE FIRSTNAME = 'AL'
      AND LASTNAME = 'BULHER';

1.  Using the DOUBLE<sub>AGENTS</sub> table, write a query that returns the following:

NAME                ST
-&#x2014;&#x2014;&#x2014;&#x2014;&#x2014;&#x2014; &#x2013;
AL             FROM IL


1.  Using the DOUBLE<sub>AGENTS</sub> table, write a query that returns the following:

NAME                       PHONE
&#x2013;&#x2014;&#x2014;&#x2014;&#x2014;&#x2014;&#x2014;&#x2014;&#x2014; &#x2014;&#x2014;&#x2014;&#x2014;
MERRICK, BUD               300-555-6666
MAST, JD                   381-555-6767
BULHER, FERRIS             345-555-3223
INPUT:

1.  Which function capitalizes the first letter of a character string and makes the rest lowercase?
2.  Which functions are also known by the *same* name?
3.  Will this query work?

    SELECT COUNT(LASTNAME) FROM CHARACTERS;

1.  How about this one?

    SELECT SUM(LASTNAME) FROM CHARACTERS

1.  Assuming that they are separate columns, which function(s) would
    splice together FIRSTNAME and LASTNAME?

1.  What does the answer 37 mean from the following SELECT?

    SELECT COUNT(*) FROM drone_strikes;

1.  Will the following statement work? (Hint: look up substr)

    SELECT SUBSTR LASTNAME,1,5 FROM NAME_TBL;

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

2.  Using today's OFFICERS table, write a query that will return the following:

officers table

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="left" />

<col  class="left" />

<col  class="left" />

<col  class="right" />
</colgroup>
<tbody>
<tr>
<td class="left">First</td>
<td class="left">Middle</td>
<td class="left">Last</td>
<td class="right">BadgeID</td>
</tr>


<tr>
<td class="left">Kevin</td>
<td class="left">Anthony</td>
<td class="left">Petrone</td>
<td class="right">32</td>
</tr>
</tbody>
</table>

OUTPUT:

INITIALS\_\_\_\_\_\_\_\_\_<sub>CODE</sub>
K.A.P.              32

1.  Which clause works just like LIKE(<exp>%)? (HINT: Look it up on google.)

2.  What is the function of the GROUP BY clause, and what other clause does it act like?

3.  Will this SELECT work?

    NAME, AVG(SALARY), DEPARTMENT
        FROM PAY_TBL
        WHERE DEPARTMENT = 'SWAT'
        ORDER BY NAME
        GROUP BY DEPARTMENT, SALARY;

1.  When using the HAVING clause, do you always have to use a GROUP BY also?

2.  Can you use ORDER BY on a column that is not one of the columns in the SELECT statement?

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
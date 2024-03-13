## Interview ask Q

```
1. Create Emp table containing a Sal column with the following sample data:-
EMP
------
SAL
------
8000
7000
6000
5000
10000
9000
4000
8000
7000
Write a SELECT statement to display the Overall 5th largest Sal.
Assuming the above data, the Overall 5th largest Sal would be 6000. Do not make use
of Rownum.

```

# Answer 1

```
1== select distinct sal from Q1 q
       where 4 =(
        select count(distinct sal) from Q1 w
        where w.sal>q.sal
      );


KD3_SHAMGIRHE_83602=>select distinct sal from Q1 q
    ->        where 4 =(
    ->         select count(distinct sal) from Q1 w
    ->         where w.sal>q.sal
    ->       );
+------+
| sal  |
+------+
| 6000 |
+------+
1 row in set (0.01 sec)

```

# Or

```
select distinct sal from Q1
order by sal desc
limit 4,1;

KD3_SHAMGIRHE_83602=>select distinct sal from Q1
    -> order by sal desc
    -> limit 4,1;
+------+
| sal  |
+------+
| 6000 |
+------+
1 row in set (0.01 sec)

```

```

2. For the above table, write a SELECT statement to display the Largest and Second
largest Sals (next to each other). Your output should be as below:-

FIRST     SECOND
-------- ------------
10000     9000

```

# Answer 2

```
  select max(s.sal) as 'First Max', max(d.sal) as 'Second Max' from Q1 s, Q1 d where d.sal<s.sal;

  KD3_SHAMGIRHE_83602=>select max(s.sal) as 'First Max', max(d.sal) as 'Second Max' from Q1 s, Q1 d where d.sal<s.sal;
+-----------+------------+
| First Max | Second Max |
+-----------+------------+
|     10000 |       9000 |
+-----------+------------+
1 row in set (0.00 sec)


```

```
3. Create Emp table containing an Empno column with the following sample data:-
EMP
-------
EMPNO
-----------
5
9
1
14
25
20
Write a SELECT statement to display the range of missing numbers. Your output
should be as follows:-
 MISSING
 ------------
 2 – 4
 6 – 8
 10 – 13
 15 – 19
 21 – 24

```

# Answer 3

```
select concat((empno+1)-4,"-",(empno-1)) as series from Q4;

KD3_SHAMGIRHE_83602=>select concat((empno+1)-4,"-",(empno-1)) as series from Q4;
+--------+
| series |
+--------+
| 2-4    |
| 6-8    |
| 11-13  |
| 22-24  |
| 17-19  |
+--------+
5 rows in set (0.00 sec)


```

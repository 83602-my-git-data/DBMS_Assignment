## DataBase_Assignments

# Assignments 1

```
1.
create table orders ( onum int (4),amt float (7,2),odate date , cnum int (4),snum int (4));
insert into orders values (3001,18.69,'1990-10-03',2008,1007);
insert into orders values (3003,767.19,'1990-10-03',2001,1001);
insert into orders values (3002,1900.10,'1990-10-03',2007,1004);
insert into orders values (3005,5160.45,'1990-10-03',2003,1002);
insert into orders values (3006,1098.16,'1990-10-03',2008,1007);
insert into orders values (3009,1713.23,'1990-10-04',2002,1003);
insert into orders values (3007,75.75,'1990-10-04',2004,1002);
insert into orders values (3008,4723.00,'1990-10-05',2006,1001);
insert into orders values (3010,1309.95,'1990-10-06',2004,1002);
insert into orders values (3011,9891.88,'1990-10-06',2006,1001);

2.
create table customers ( cnum int (4),cname varchar (10),city varchar (10),rating int (4),snum int (4));

insert into customers values (2001,'hoffman','london',100,1001);
insert into customers values (2002,'giovanni','rome',200,1003);
insert into customers values (2003,'liu','san jose',200,1002);
insert into customers values (2004,'grass','berlin',300,1002);
insert into customers values (2006,'clemens','london',100,1001);
insert into customers values (2008,'cisneros','san jose',300,1007);
insert into customers values (2007,'pereira','rome',100,1004);

3.
create table salespeople ( snum int (4), sname varchar (10),city varchar (10),comm float (3,2));

insert into salespeople values (1001,'peel','london',.12);
insert into salespeople values (1002,'serres','san joes',.13);
insert into salespeople values (1004,'motika','london',.11);
insert into salespeople values (1007,'rifkin','barcelona',.15);
insert into salespeople values (1003,'axelrod','new york',.10);

select *from orders;
select * from salespeople;
select *from customers;
```

# Answers

```
  KD3_SHAM_83602>select *from orders;
+------+---------+------------+------+------+
| onum | amt     | odate      | cnum | snum |
+------+---------+------------+------+------+
| 3001 |   18.69 | 1990-10-03 | 2008 | 1007 |
| 3003 |  767.19 | 1990-10-03 | 2001 | 1001 |
| 3002 | 1900.10 | 1990-10-03 | 2007 | 1004 |
| 3005 | 5160.45 | 1990-10-03 | 2003 | 1002 |
| 3006 | 1098.16 | 1990-10-03 | 2008 | 1007 |
| 3009 | 1713.23 | 1990-10-04 | 2002 | 1003 |
| 3007 |   75.75 | 1990-10-04 | 2004 | 1002 |
| 3008 | 4723.00 | 1990-10-05 | 2006 | 1001 |
| 3010 | 1309.95 | 1990-10-06 | 2004 | 1002 |
| 3011 | 9891.88 | 1990-10-06 | 2006 | 1001 |
+------+---------+------------+------+------+
10 rows in set (0.00 sec)

KD3_SHAM_83602>select * from salespeople;
+------+---------+-----------+------+
| snum | sname   | city      | comm |
+------+---------+-----------+------+
| 1001 | peel    | london    | 0.12 |
| 1002 | serres  | san joes  | 0.13 |
| 1004 | motika  | london    | 0.11 |
| 1007 | rifkin  | barcelona | 0.15 |
| 1003 | axelrod | new york  | 0.10 |
+------+---------+-----------+------+
5 rows in set (0.00 sec)

KD3_SHAM_83602>select *from customers;
+------+----------+----------+--------+------+
| cnum | cname    | city     | rating | snum |
+------+----------+----------+--------+------+
| 2001 | hoffman  | london   |    100 | 1001 |
| 2002 | giovanni | rome     |    200 | 1003 |
| 2003 | liu      | san jose |    200 | 1002 |
| 2004 | grass    | berlin   |    300 | 1002 |
| 2006 | clemens  | london   |    100 | 1001 |
| 2008 | cisneros | san jose |    300 | 1007 |
| 2007 | pereira  | rome     |    100 | 1004 |
+------+----------+----------+--------+------+
7 rows in set (0.00 sec)
```

# Assignments 2

```
Q.1 Which field of the customer table is primary key ?

Q.2 What is the 4th column of customer table?
Ans. Rating

Q.3 What is another word for row and column?
Ans. Row is also called as tuple, entity, opportinity Column is also called as attributes, methods , keys

Q.4 Why isnt it possible to see 1st 5 rows of a table?
Ans. The rows are stored at diffrent places in a server HDD in a file format. And they
are called sequentially as per there address. No specific location is given to the rows.
Thats why it is not possible to see 1st 5 rows of the table.
```

# Assignments 3

```
Q.1 Does ANSI recognise the data type DATE?
Ans : ANSI dosent recognise the date datatype.

Q.2 Which subdivison of SQL is used to insert values in tables?
Ans : INSERT into is used
It is a DML command
```

# Assignments 4

```
1.select onum,amt,odate from orders;
2.select * from customers where snum = 1001;
3.select city,sname,snum,comm from salespeople;
4.select rating,cname from customers where city='san jose';
```

# Answers

```
KD3_SHAM_83602>select onum,amt,odate from orders;
+------+---------+------------+
| onum | amt     | odate      |
+------+---------+------------+
| 3001 |   18.69 | 1990-10-03 |
| 3003 |  767.19 | 1990-10-03 |
| 3002 | 1900.10 | 1990-10-03 |
| 3005 | 5160.45 | 1990-10-03 |
| 3006 | 1098.16 | 1990-10-03 |
| 3009 | 1713.23 | 1990-10-04 |
| 3007 |   75.75 | 1990-10-04 |
| 3008 | 4723.00 | 1990-10-05 |
| 3010 | 1309.95 | 1990-10-06 |
| 3011 | 9891.88 | 1990-10-06 |
+------+---------+------------+
10 rows in set (0.00 sec)

KD3_SHAM_83602>select * from customers where snum = 1001;
+------+---------+--------+--------+------+
| cnum | cname   | city   | rating | snum |
+------+---------+--------+--------+------+
| 2001 | hoffman | london |    100 | 1001 |
| 2006 | clemens | london |    100 | 1001 |
+------+---------+--------+--------+------+
2 rows in set (0.00 sec)

KD3_SHAM_83602>select city,sname,snum,comm from salespeople;
+-----------+---------+------+------+
| city      | sname   | snum | comm |
+-----------+---------+------+------+
| london    | peel    | 1001 | 0.12 |
| san joes  | serres  | 1002 | 0.13 |
| london    | motika  | 1004 | 0.11 |
| barcelona | rifkin  | 1007 | 0.15 |
| new york  | axelrod | 1003 | 0.10 |
+-----------+---------+------+------+
5 rows in set (0.00 sec)

KD3_SHAM_83602>select rating,cname from customers where city='san jose';
+--------+----------+
| rating | cname    |
+--------+----------+
|    200 | liu      |
|    300 | cisneros |
+--------+----------+
2 rows in set (0.00 sec)

```

# Assignments 5

```
1.select * from orders where amt > 1000;
2.select sname , city from salespeople where comm > .10 and city = 'london';
3.select *from customers where rating <= 100 and city != 'rome';
4.select *from orders where (amt < 1000 or not (odate = '1990-10-03' and cnum > 2003));
5.select *from orders where not ((odate = '1990-10-03' or snum>1006) and amt >= 1500);
6.select snum , sname , city , comm from salespeople where (comm > .12 or comm < .14);
```

# Answers

```
KD3_SHAM_83602>select * from orders where amt > 1000;
+------+---------+------------+------+------+
| onum | amt     | odate      | cnum | snum |
+------+---------+------------+------+------+
| 3002 | 1900.10 | 1990-10-03 | 2007 | 1004 |
| 3005 | 5160.45 | 1990-10-03 | 2003 | 1002 |
| 3006 | 1098.16 | 1990-10-03 | 2008 | 1007 |
| 3009 | 1713.23 | 1990-10-04 | 2002 | 1003 |
| 3008 | 4723.00 | 1990-10-05 | 2006 | 1001 |
| 3010 | 1309.95 | 1990-10-06 | 2004 | 1002 |
| 3011 | 9891.88 | 1990-10-06 | 2006 | 1001 |
+------+---------+------------+------+------+
7 rows in set (0.01 sec)

KD3_SHAM_83602>select sname , city from salespeople where comm > .10 and city = 'london';
+--------+--------+
| sname  | city   |
+--------+--------+
| peel   | london |
| motika | london |
+--------+--------+
2 rows in set (0.00 sec)

KD3_SHAM_83602>select *from customers where rating <= 100 and city != 'rome';
+------+---------+--------+--------+------+
| cnum | cname   | city   | rating | snum |
+------+---------+--------+--------+------+
| 2001 | hoffman | london |    100 | 1001 |
| 2006 | clemens | london |    100 | 1001 |
+------+---------+--------+--------+------+
2 rows in set (0.00 sec)

KD3_SHAM_83602>select *from orders where (amt < 1000 or not (odate = '1990-10-03' and cnum > 2003));
+------+---------+------------+------+------+
| onum | amt     | odate      | cnum | snum |
+------+---------+------------+------+------+
| 3001 |   18.69 | 1990-10-03 | 2008 | 1007 |
| 3003 |  767.19 | 1990-10-03 | 2001 | 1001 |
| 3005 | 5160.45 | 1990-10-03 | 2003 | 1002 |
| 3009 | 1713.23 | 1990-10-04 | 2002 | 1003 |
| 3007 |   75.75 | 1990-10-04 | 2004 | 1002 |
| 3008 | 4723.00 | 1990-10-05 | 2006 | 1001 |
| 3010 | 1309.95 | 1990-10-06 | 2004 | 1002 |
| 3011 | 9891.88 | 1990-10-06 | 2006 | 1001 |
+------+---------+------------+------+------+
8 rows in set (0.00 sec)

KD3_SHAM_83602>select *from orders where not ((odate = '1990-10-03' or snum>1006) and amt >= 1500);
+------+---------+------------+------+------+
| onum | amt     | odate      | cnum | snum |
+------+---------+------------+------+------+
| 3001 |   18.69 | 1990-10-03 | 2008 | 1007 |
| 3003 |  767.19 | 1990-10-03 | 2001 | 1001 |
| 3006 | 1098.16 | 1990-10-03 | 2008 | 1007 |
| 3009 | 1713.23 | 1990-10-04 | 2002 | 1003 |
| 3007 |   75.75 | 1990-10-04 | 2004 | 1002 |
| 3008 | 4723.00 | 1990-10-05 | 2006 | 1001 |
| 3010 | 1309.95 | 1990-10-06 | 2004 | 1002 |
| 3011 | 9891.88 | 1990-10-06 | 2006 | 1001 |
+------+---------+------------+------+------+
8 rows in set (0.00 sec)

KD3_SHAM_83602>select snum , sname , city , comm from salespeople where (comm > .12 or comm < .14);
+------+---------+-----------+------+
| snum | sname   | city      | comm |
+------+---------+-----------+------+
| 1001 | peel    | london    | 0.12 |
| 1002 | serres  | san joes  | 0.13 |
| 1004 | motika  | london    | 0.11 |
| 1007 | rifkin  | barcelona | 0.15 |
| 1003 | axelrod | new york  | 0.10 |
+------+---------+-----------+------+
5 rows in set (0.00 sec)
```

# Assignments 6

```
1.select * from orders where odate between '1990-10-03' and '1990-10-04';
2.select * from orders where odate >= '1990-10-03' and odate <= '1990-10-04';
3.select * from customers where snum in (select snum from salespeople where sname in ('peel' , 'motika'));
4.select cname,sname from salespeople,customers where salespeople.snum =customers.snum having sname='peel' or sname='motika';
5.select * from customers where cname >= 'A' and cname <= 'H';
6.select * from customers where cname like 'C%';
7.select * from orders where amt != '0' OR amt != NULL ;
```

# Answers

```
  KD3_SHAM_83602>select * from orders where odate between '1990-10-03' and '1990-10-04';
+------+---------+------------+------+------+
| onum | amt     | odate      | cnum | snum |
+------+---------+------------+------+------+
| 3001 |   18.69 | 1990-10-03 | 2008 | 1007 |
| 3003 |  767.19 | 1990-10-03 | 2001 | 1001 |
| 3002 | 1900.10 | 1990-10-03 | 2007 | 1004 |
| 3005 | 5160.45 | 1990-10-03 | 2003 | 1002 |
| 3006 | 1098.16 | 1990-10-03 | 2008 | 1007 |
| 3009 | 1713.23 | 1990-10-04 | 2002 | 1003 |
| 3007 |   75.75 | 1990-10-04 | 2004 | 1002 |
+------+---------+------------+------+------+
7 rows in set (0.00 sec)

KD3_SHAM_83602>select * from orders where odate >= '1990-10-03' and odate <= '1990-10-04';
+------+---------+------------+------+------+
| onum | amt     | odate      | cnum | snum |
+------+---------+------------+------+------+
| 3001 |   18.69 | 1990-10-03 | 2008 | 1007 |
| 3003 |  767.19 | 1990-10-03 | 2001 | 1001 |
| 3002 | 1900.10 | 1990-10-03 | 2007 | 1004 |
| 3005 | 5160.45 | 1990-10-03 | 2003 | 1002 |
| 3006 | 1098.16 | 1990-10-03 | 2008 | 1007 |
| 3009 | 1713.23 | 1990-10-04 | 2002 | 1003 |
| 3007 |   75.75 | 1990-10-04 | 2004 | 1002 |
+------+---------+------------+------+------+
7 rows in set (0.00 sec)

KD3_SHAM_83602>select * from customers where snum in (select snum from salespeople where sname in ('peel' , 'motika'));
+------+---------+--------+--------+------+
| cnum | cname   | city   | rating | snum |
+------+---------+--------+--------+------+
| 2001 | hoffman | london |    100 | 1001 |
| 2006 | clemens | london |    100 | 1001 |
| 2007 | pereira | rome   |    100 | 1004 |
+------+---------+--------+--------+------+
3 rows in set (0.00 sec)

KD3_SHAM_83602>select cname,sname from salespeople,customers where salespeople.snum =customers.snum having sname='peel' or sname='motika';
+---------+--------+
| cname   | sname  |
+---------+--------+
| hoffman | peel   |
| clemens | peel   |
| pereira | motika |
+---------+--------+
3 rows in set (0.00 sec)

KD3_SHAM_83602>select * from customers where cname >= 'A' and cname <= 'H';
+------+----------+----------+--------+------+
| cnum | cname    | city     | rating | snum |
+------+----------+----------+--------+------+
| 2002 | giovanni | rome     |    200 | 1003 |
| 2004 | grass    | berlin   |    300 | 1002 |
| 2006 | clemens  | london   |    100 | 1001 |
| 2008 | cisneros | san jose |    300 | 1007 |
+------+----------+----------+--------+------+
4 rows in set (0.00 sec)

KD3_SHAM_83602>select * from customers where cname like 'C%';
+------+----------+----------+--------+------+
| cnum | cname    | city     | rating | snum |
+------+----------+----------+--------+------+
| 2006 | clemens  | london   |    100 | 1001 |
| 2008 | cisneros | san jose |    300 | 1007 |
+------+----------+----------+--------+------+
2 rows in set (0.00 sec)

KD3_SHAM_83602>select * from orders where amt != '0' OR amt != NULL ;
+------+---------+------------+------+------+
| onum | amt     | odate      | cnum | snum |
+------+---------+------------+------+------+
| 3001 |   18.69 | 1990-10-03 | 2008 | 1007 |
| 3003 |  767.19 | 1990-10-03 | 2001 | 1001 |
| 3002 | 1900.10 | 1990-10-03 | 2007 | 1004 |
| 3005 | 5160.45 | 1990-10-03 | 2003 | 1002 |
| 3006 | 1098.16 | 1990-10-03 | 2008 | 1007 |
| 3009 | 1713.23 | 1990-10-04 | 2002 | 1003 |
| 3007 |   75.75 | 1990-10-04 | 2004 | 1002 |
| 3008 | 4723.00 | 1990-10-05 | 2006 | 1001 |
| 3010 | 1309.95 | 1990-10-06 | 2004 | 1002 |
| 3011 | 9891.88 | 1990-10-06 | 2006 | 1001 |
+------+---------+------------+------+------+
10 rows in set (0.00 sec)

```

# Assignments 7

```
1.select count(odate) from orders where odate='1990-10-03';
2.select count(city) from customers where city is not null;
3.select min(amt),cname from customers,orders where customers.snum=orders.snum group by 4.cname;
4.select cname from customers where cname like 'g%' limit 1;
5.select max(rating) from customers group by city;
6.select odate, count(distinct snum) from orders group by odate;
or
select odate, count(distinct o.snum) from orders o, salespeople S where o.snum=S.snum group by odate;
```

# Answers

```
  KD3_SHAM_83602>select count(odate) from orders where odate='1990-10-03';
+--------------+
| count(odate) |
+--------------+
|            5 |
+--------------+
1 row in set (0.00 sec)

KD3_SHAM_83602>select count(city) from customers where city is not null;
+-------------+
| count(city) |
+-------------+
|           7 |
+-------------+
1 row in set (0.00 sec)

KD3_SHAM_83602>select min(amt),cname from customers,orders where customers.snum=orders.snum group by cname;
+----------+----------+
| min(amt) | cname    |
+----------+----------+
|    18.69 | cisneros |
|   767.19 | clemens  |
|   767.19 | hoffman  |
|  1900.10 | pereira  |
|    75.75 | grass    |
|    75.75 | liu      |
|  1713.23 | giovanni |
+----------+----------+
7 rows in set (0.00 sec)

KD3_SHAM_83602>select cname from customers where cname like 'g%' limit 1;
+----------+
| cname    |
+----------+
| giovanni |
+----------+
1 row in set (0.00 sec)

KD3_SHAM_83602>select max(rating) from customers group by city;
+-------------+
| max(rating) |
+-------------+
|         100 |
|         200 |
|         300 |
|         300 |
+-------------+
4 rows in set (0.00 sec)

KD3_SHAM_83602>select odate, count(distinct snum) from orders group by odate;
+------------+----------------------+
| odate      | count(distinct snum) |
+------------+----------------------+
| 1990-10-03 |                    4 |
| 1990-10-04 |                    2 |
| 1990-10-05 |                    1 |
| 1990-10-06 |                    2 |
+------------+----------------------+
4 rows in set (0.00 sec)

KD3_SHAM_83602>select odate, count(distinct o.snum) from orders o, salespeople S where o.snum=S.snum group by odate;
+------------+------------------------+
| odate      | count(distinct o.snum) |
+------------+------------------------+
| 1990-10-03 |                      4 |
| 1990-10-04 |                      2 |
| 1990-10-05 |                      1 |
| 1990-10-06 |                      2 |
+------------+------------------------+
4 rows in set (0.00 sec)
```

# Assignments 8

```
1.select onum, s.snum, amt+amt*0.12 as commission from salespeople s, orders o where s.snum=o.snum;
2.select concat('for the ',city,' the heightest rating is : ',max(rating)) as 'Highest Rating' from customers group by city;
3.select rating ,cname,cnum from customers order by rating desc;
4.select odate , count(onum) from orders group by odate order by 2 desc;
```

# Answers

```
KD3_SHAM_83602>select onum, s.snum, amt+amt*0.12 as commission from salespeople s, orders o where s.snum=o.snum;
+------+------+------------+
| onum | snum | commission |
+------+------+------------+
| 3001 | 1007 |      20.93 |
| 3003 | 1001 |     859.25 |
| 3002 | 1004 |    2128.11 |
| 3005 | 1002 |    5779.70 |
| 3006 | 1007 |    1229.94 |
| 3009 | 1003 |    1918.82 |
| 3007 | 1002 |      84.84 |
| 3008 | 1001 |    5289.76 |
| 3010 | 1002 |    1467.14 |
| 3011 | 1001 |   11078.91 |
+------+------+------------+
10 rows in set (0.01 sec)

KD3_SHAM_83602>select concat('for the ',city,' the heightest rating is : ',max(rating)) as 'Highest Rating' from customers group by city;
+------------------------------------------------+
| Highest Rating                                 |
+------------------------------------------------+
| for the london the heightest rating is : 100   |
| for the rome the heightest rating is : 200     |
| for the san jose the heightest rating is : 300 |
| for the berlin the heightest rating is : 300   |
+------------------------------------------------+
4 rows in set (0.00 sec)

KD3_SHAM_83602>select rating ,cname,cnum from customers order by rating desc;
+--------+----------+------+
| rating | cname    | cnum |
+--------+----------+------+
|    300 | grass    | 2004 |
|    300 | cisneros | 2008 |
|    200 | giovanni | 2002 |
|    200 | liu      | 2003 |
|    100 | hoffman  | 2001 |
|    100 | clemens  | 2006 |
|    100 | pereira  | 2007 |
+--------+----------+------+
7 rows in set (0.00 sec)

KD3_SHAM_83602>select odate , count(onum) from orders group by odate order by 2 desc;
+------------+-------------+
| odate      | count(onum) |
+------------+-------------+
| 1990-10-03 |           5 |
| 1990-10-04 |           2 |
| 1990-10-06 |           2 |
| 1990-10-05 |           1 |
+------------+-------------+
4 rows in set (0.00 sec)

KD3_SHAM_83602>

```

# Assignments 9

```
1.select onum,cname from orders o, customers c where c.cnum = o.cnum;

2.select sname , cname , onum from orders o,
customers c, salespeople p
where o.snum = p.snum and o.cnum = c.cnum;

3.select cname, sname,comm from salespeople s , customers c
where c.snum = s.snum
having comm >0.12;

4.select amt * comm ,rating commissions
from salespeople s , customers c , orders o
where o.snum=c.snum and o.snum=s.snum
having rating>100;
```

# Answers

```
KD3_SHAM_83602>select onum,cname from orders o, customers c where c.cnum = o.cnum;
+------+----------+
| onum | cname    |
+------+----------+
| 3001 | cisneros |
| 3003 | hoffman  |
| 3002 | pereira  |
| 3005 | liu      |
| 3006 | cisneros |
| 3009 | giovanni |
| 3007 | grass    |
| 3008 | clemens  |
| 3010 | grass    |
| 3011 | clemens  |
+------+----------+
10 rows in set (0.00 sec)

KD3_SHAM_83602>select sname , cname , onum from orders o,
    -> customers c, salespeople p
    -> where o.snum = p.snum and o.cnum = c.cnum;
+---------+----------+------+
| sname   | cname    | onum |
+---------+----------+------+
| peel    | hoffman  | 3003 |
| axelrod | giovanni | 3009 |
| serres  | liu      | 3005 |
| serres  | grass    | 3010 |
| serres  | grass    | 3007 |
| peel    | clemens  | 3011 |
| peel    | clemens  | 3008 |
| rifkin  | cisneros | 3006 |
| rifkin  | cisneros | 3001 |
| motika  | pereira  | 3002 |
+---------+----------+------+
10 rows in set (0.00 sec)

KD3_SHAM_83602>select cname, sname,comm from salespeople s , customers c
    -> where c.snum = s.snum
    -> having comm >0.12;
+----------+--------+------+
| cname    | sname  | comm |
+----------+--------+------+
| liu      | serres | 0.13 |
| grass    | serres | 0.13 |
| cisneros | rifkin | 0.15 |
+----------+--------+------+
3 rows in set (0.00 sec)

KD3_SHAM_83602>select amt * comm ,rating commissions
    -> from salespeople s , customers c , orders o
    -> where o.snum=c.snum and o.snum=s.snum
    -> having rating>100;
+------------+-------------+
| amt * comm | commissions |
+------------+-------------+
|       2.80 |         300 |
|     670.86 |         300 |
|     670.86 |         200 |
|     164.72 |         300 |
|     171.32 |         200 |
|       9.85 |         300 |
|       9.85 |         200 |
|     170.29 |         300 |
|     170.29 |         200 |
+------------+-------------+
9 rows in set (0.00 sec)

KD3_SHAM_83602>

```

# Assignments 10

```
1.select s.sname , s.city , sp.sname from salespeople s , salespeople sp
 where sp.city=s.city and s.snum< sp.snum;

2.select cname , city from customers
where rating = (
select rating from customers where
cname = 'hoffman'
);
or
select c.cname, c.city from customers c, customers d
 where d.rating = c.rating
 having cname = 'hoffman';
```

# answers

```
 KD3_SHAM_83602>select s.sname , s.city , sp.sname from salespeople s , salespeople sp
    ->  where sp.city=s.city and s.snum< sp.snum;
+-------+--------+--------+
| sname | city   | sname  |
+-------+--------+--------+
| peel  | london | motika |
+-------+--------+--------+
1 row in set (0.00 sec)

KD3_SHAM_83602>
KD3_SHAM_83602>select cname , city from customers
    -> where rating = (
    -> select rating from customers where
    -> cname = 'hoffman'
    -> );
+---------+--------+
| cname   | city   |
+---------+--------+
| hoffman | london |
| clemens | london |
| pereira | rome   |
+---------+--------+
3 rows in set (0.00 sec)

KD3_SHAM_83602>select c.cname, c.city from customers c, customers d
    ->  where d.rating = c.rating
    ->  having cname = 'hoffman';
+---------+--------+
| cname   | city   |
+---------+--------+
| hoffman | london |
| hoffman | london |
| hoffman | london |
+---------+--------+
3 rows in set (0.00 sec)

KD3_SHAM_83602>
```

# Assignments 11

```
select * from orders
 where cnum = (
 select cnum from customers where cname = 'cisneros');

 SELECT c.cname, c.rating
FROM customers c
WHERE c.cnum IN (
    SELECT o.cnum
    FROM orders o
    GROUP BY o.cnum
    HAVING AVG(o.amt) > (
        SELECT AVG(amt)
        FROM orders
    )
);

3.select total from (select snum , sum(amt) as total from orders group by snum) as totals
where total > (select max(amt) from orders);
```

# Answers

```
KD3_SHAM_83602>select * from orders
   ->  where cnum = (
   ->  select cnum from customers where cname = 'cisneros');
+------+---------+------------+------+------+
| onum | amt     | odate      | cnum | snum |
+------+---------+------------+------+------+
| 3001 |   18.69 | 1990-10-03 | 2008 | 1007 |
| 3006 | 1098.16 | 1990-10-03 | 2008 | 1007 |
+------+---------+------------+------+------+
2 rows in set (0.00 sec)

KD3_SHAM_83602> SELECT c.cname, c.rating
   -> FROM customers c
   -> WHERE c.cnum IN (
   ->     SELECT o.cnum
   ->     FROM orders o
   ->     GROUP BY o.cnum
   ->     HAVING AVG(o.amt) > (
   ->         SELECT AVG(amt)
   ->         FROM orders
   ->     )
   -> );
+---------+--------+
| cname   | rating |
+---------+--------+
| liu     |    200 |
| clemens |    100 |
+---------+--------+
2 rows in set (0.00 sec)

KD3_SHAM_83602>select total from (select snum , sum(amt) as total from orders group by snum) as totals
   -> where total > (select max(amt) from orders);
+----------+
| total    |
+----------+
| 15382.07 |
+----------+
1 row in set (0.00 sec)
```

# Assignments 12

```
select * from customers
    where rating >= any(select c.rating from customers c, salespeople s where s.snum=c.snum);
select * from salespeople
     s where s.city not in (select c.city from customers c where c.snum=s.snum and c.city=s.city);
select * from orders
     where amt > any(select o.amt from orders o ,customers c where c.cnum=o.cnum and c.city='london');
select * from orders
  where amt >(select min(o.amt) from orders o ,customers c where c.cnum=o.cnum and c.city='london');
select * from orders
     where amt <(select max(o.amt) from orders o ,customers c where c.cnum=o.cnum and c.city='london');
```
# answer
```
KD3_SHAM_83602>select * from customers
    ->     where rating >= any(select c.rating from customers c, salespeople s where s.snum=c.snum);
+------+----------+----------+--------+------+
| cnum | cname    | city     | rating | snum |
+------+----------+----------+--------+------+
| 2001 | hoffman  | london   |    100 | 1001 |
| 2002 | giovanni | rome     |    200 | 1003 |
| 2003 | liu      | san jose |    200 | 1002 |
| 2004 | grass    | berlin   |    300 | 1002 |
| 2006 | clemens  | london   |    100 | 1001 |
| 2008 | cisneros | san jose |    300 | 1007 |
| 2007 | pereira  | rome     |    100 | 1004 |
+------+----------+----------+--------+------+
7 rows in set (0.00 sec)

KD3_SHAM_83602>select * from salespeople
    ->      s where s.city not in (select c.city from customers c where c.snum=s.snum and c.city=s.city);
+------+---------+-----------+------+
| snum | sname   | city      | comm |
+------+---------+-----------+------+
| 1002 | serres  | san joes  | 0.13 |
| 1004 | motika  | london    | 0.11 |
| 1007 | rifkin  | barcelona | 0.15 |
| 1003 | axelrod | new york  | 0.10 |
+------+---------+-----------+------+
4 rows in set (0.00 sec)

KD3_SHAM_83602>select * from orders
    ->      where amt > any(select o.amt from orders o ,customers c where c.cnum=o.cnum and c.city='london');
+------+---------+------------+------+------+
| onum | amt     | odate      | cnum | snum |
+------+---------+------------+------+------+
| 3002 | 1900.10 | 1990-10-03 | 2007 | 1004 |
| 3005 | 5160.45 | 1990-10-03 | 2003 | 1002 |
| 3006 | 1098.16 | 1990-10-03 | 2008 | 1007 |
| 3009 | 1713.23 | 1990-10-04 | 2002 | 1003 |
| 3008 | 4723.00 | 1990-10-05 | 2006 | 1001 |
| 3010 | 1309.95 | 1990-10-06 | 2004 | 1002 |
| 3011 | 9891.88 | 1990-10-06 | 2006 | 1001 |
+------+---------+------------+------+------+
7 rows in set (0.00 sec)

KD3_SHAM_83602>select * from orders
    ->   where amt >(select min(o.amt) from orders o ,customers c where c.cnum=o.cnum and c.city='london');
+------+---------+------------+------+------+
| onum | amt     | odate      | cnum | snum |
+------+---------+------------+------+------+
| 3002 | 1900.10 | 1990-10-03 | 2007 | 1004 |
| 3005 | 5160.45 | 1990-10-03 | 2003 | 1002 |
| 3006 | 1098.16 | 1990-10-03 | 2008 | 1007 |
| 3009 | 1713.23 | 1990-10-04 | 2002 | 1003 |
| 3008 | 4723.00 | 1990-10-05 | 2006 | 1001 |
| 3010 | 1309.95 | 1990-10-06 | 2004 | 1002 |
| 3011 | 9891.88 | 1990-10-06 | 2006 | 1001 |
+------+---------+------------+------+------+
7 rows in set (0.00 sec)

KD3_SHAM_83602>select * from orders
    ->      where amt <(select max(o.amt) from orders o ,customers c where c.cnum=o.cnum and c.city='london');
+------+---------+------------+------+------+
| onum | amt     | odate      | cnum | snum |
+------+---------+------------+------+------+
| 3001 |   18.69 | 1990-10-03 | 2008 | 1007 |
| 3003 |  767.19 | 1990-10-03 | 2001 | 1001 |
| 3002 | 1900.10 | 1990-10-03 | 2007 | 1004 |
| 3005 | 5160.45 | 1990-10-03 | 2003 | 1002 |
| 3006 | 1098.16 | 1990-10-03 | 2008 | 1007 |
| 3009 | 1713.23 | 1990-10-04 | 2002 | 1003 |
| 3007 |   75.75 | 1990-10-04 | 2004 | 1002 |
| 3008 | 4723.00 | 1990-10-05 | 2006 | 1001 |
| 3010 | 1309.95 | 1990-10-06 | 2004 | 1002 |
+------+---------+------------+------+------+
9 rows in set (0.00 sec)
```


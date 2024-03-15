# Assignments 1

**1.Write a program that computes the perimeter and the area of a rectangle. Define
your own values for the length and width. (Assuming that L and W are the length
and width of the rectangle, Perimeter = 2*(L+W) and Area = L*W. )**

```
delimiter //
create procedure abc( in l int,in w int,out perimeter int,out area int)
begin
set perimeter = 2*(l+w);
set area = l*w;
end; //
delimiter ;

 set @perimeter = 0;
Query OK, 0 rows affected (0.01 sec)

mysql> set @area = 0;
Query OK, 0 rows affected (0.00 sec)

mysql> call abc(5,10,@perimeter,@area);
Query OK, 0 rows affected (0.01 sec)

mysql> select @perimeter, @area from dual;
+------------+-------+
| @perimeter | @area |
+------------+-------+
|         30 |    50 |
+------------+-------+
```

**2.Write a program that declares an integer variable called num, assigns a value to it,
and computes and inserts into the tempp table the value of the variable itself, its
square, and its cube.**

```
delimiter //
create procedure Q2()
begin
declare num int;
set num = 2;
insert into temp values(num,num*num,num*num*num);
end; //
delimiter ;

KD3_SHAM_83602=>create table temp(num int, square int, numcube int);
Query OK, 0 rows affected (0.02 sec)

KD3_SHAM_83602=>delimiter //
KD3_SHAM_83602=>create procedure Q2()
    -> begin
    -> declare num int;
    -> set num = 2;
    -> insert into temp values(num,num*num,num*num*num);
    -> end; //
Query OK, 0 rows affected (0.01 sec)

KD3_SHAM_83602=>delimiter ;
KD3_SHAM_83602=>call Q2();
Query OK, 1 row affected (0.01 sec)

KD3_SHAM_83602=>select * from temp;
+------+--------+---------+
| num  | square | numcube |
+------+--------+---------+
|    2 |      4 |       8 |
+------+--------+---------+
1 row in set (0.00 sec)
```

**3.Convert a temperature in Fahrenheit (F) to its equivalent in Celsius (C) and vice
versa. The required formulae are:- C= (F-32)*5/9
F= 9/5*C + 32**

```
delimiter //
create procedure Q3(in fahrenheit float,out celsius float)
begin
set celsius = round(((fahrenheit-32)*5/9),2);
end; //
delimiter ;
set @celsius=0;
call Q3(50.00,@celsius);
select @celsius from dual;
drop procedure Q3;
set @celsius=null;

KD3_SHAM_83602=>delimiter //
KD3_SHAM_83602=>create procedure Q3(in fahrenheit float,out celsius float)
    -> begin
    -> set celsius = round(((fahrenheit-32)*5/9),2);
    -> end; //
Query OK, 0 rows affected (0.01 sec)

KD3_SHAM_83602=>delimiter ;
KD3_SHAM_83602=>set @celsius=0;
Query OK, 0 rows affected (0.00 sec)

KD3_SHAM_83602=>call Q3(50.00,@celsius);
Query OK, 0 rows affected (0.00 sec)

KD3_SHAM_83602=>select @celsius from dual;
+----------+
| @celsius |
+----------+
|       10 |
+----------+
1 row in set (0.00 sec)
```

**4.Convert a number of inches into yards, feet, and inches. For example, 124 inches
equals 3 yards, 1 foot, and 4 inches**

```
delimiter //
create procedure Q4(inout inches float , out yards float , out foot float)
begin
 set yards = round(inches/36,0);
 set foot = round(((inches/36) - yards)*10,0);
 set inches = CEILING((((inches/36) - yards)*10)-foot);
end//
delimiter ;
set @inches = 124;
call Q4(@inches,@yards,@foot);
 select @yards,@foot,@inches from dual;

 mysql> delimiter //
mysql> create procedure Q4(inout inches float , out yards float , out foot float)
    -> begin
    ->  set yards = round(inches/36,0);
    ->  set foot = round(((inches/36) - yards)*10,0);
    ->  set inches = CEILING((((inches/36) - yards)*10)-foot);
    -> end//
Query OK, 0 rows affected (0.01 sec)

mysql> delimiter ;
mysql> set @inches = 124;
Query OK, 0 rows affected (0.00 sec)

mysql> call Q4(@inches,@yards,@foot);
Query OK, 0 rows affected (0.00 sec)

mysql>  select @yards,@foot,@inches from dual;
+--------+-------+---------+
| @yards | @foot | @inches |
+--------+-------+---------+
|      3 |     4 |       1 |
+--------+-------+---------+
1 row in set (0.00 sec)
```

**5. Write a program that enables a user to input an integer. The program should then
state whether the integer is evenly divisible by 5.**
delimiter //

```
create procedure Q5(in value int , out output varchar(100))
begin
    if mod(value, 5) = 0 then
        set output = concat(value, ' is divisible by 5.');
    else
        set output = concat(value, ' is not divisible by 5.');
    end if;
end //
delimiter ;

set @value = 124;
set @output = "";
call Q5(@value, @output);

select @output from dual;

KD3_sham_93602=>delimiter //
KD3_sham_93602=>
KD3_sham_93602=>create procedure Q5(in value int , out output varchar(100))
    -> begin
    ->     if mod(value, 5) = 0 then
    ->         set output = concat(value, ' is divisible by 5.');
    ->     else
    ->         set output = concat(value, ' is not divisible by 5.');
    ->     end if;
    -> end //
Query OK, 0 rows affected (0.01 sec)

KD3_sham_93602=>delimiter ;
KD3_sham_93602=>set @value = 124;
Query OK, 0 rows affected (0.00 sec)

KD3_sham_93602=>set @output = "";
Query OK, 0 rows affected (0.00 sec)

KD3_sham_93602=>call Q5(@value, @output);
Query OK, 0 rows affected (0.01 sec)

KD3_sham_93602=>
KD3_sham_93602=>select @output from dual;
+----------------------------+
| @output                    |
+----------------------------+
| 124 is not divisible by 5. |
+----------------------------+
1 row in set (0.00 sec)

```

**6. Your block should read in two real numbers and tell whether the product of the two
numbers is equal to or greater than 100.**

```
delimiter //
create procedure Q6(in  first int , in second int)
begin
declare x int;
set x=first*second;
if x>100 then
   insert into ans values(first, second,"product is greater than 100");
elseif x<100 then
    insert into ans values(first, second,"product is less than 100");
else
    insert into ans values(first, second,"product is equal to the 100");
end if;
end //
delimiter ;

create table ans ( first int, second int, answer varchar(255));

delimiter //
KD3_sham_93602=>create procedure Q6(in  first int , in second int)
    -> begin
    -> declare x int;
    -> set x=first*second;
    -> if x>100 then
    ->    insert into ans values(first, second,"product is greater than 100");
    -> elseif x<100 then
    ->     insert into ans values(first, second,"product is less than 100");
    -> else
    ->     insert into ans values(first, second,"product is equal to the 100");
    -> end if;
    -> end //
Query OK, 0 rows affected (0.01 sec)

KD3_sham_93602=>delimiter ;
KD3_sham_93602=>call Q6(50,2);
Query OK, 1 row affected (0.01 sec)

KD3_sham_93602=>call Q6(50,4);
Query OK, 1 row affected (0.01 sec)

KD3_sham_93602=>call Q6(20,4);
Query OK, 1 row affected (0.01 sec)

KD3_sham_93602=>select * from ans;
+-------+--------+-----------------------------+
| first | second | answer                      |
+-------+--------+-----------------------------+
|    50 |      2 | product is equal to the 100 |
|    50 |      4 | product is greater than 100 |
|    20 |      4 | product is less than 100    |
+-------+--------+-----------------------------+
3 rows in set (0.00 sec)
```

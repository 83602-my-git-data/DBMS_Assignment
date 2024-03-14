# Assignments

```
1.Write a program that computes the perimeter and the area of a rectangle. Define
your own values for the length and width. (Assuming that L and W are the length
and width of the rectangle, Perimeter = 2*(L+W) and Area = L*W. )

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

2.Write a program that declares an integer variable called num, assigns a value to it,
and computes and inserts into the tempp table the value of the variable itself, its
square, and its cube.

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

3.Convert a temperature in Fahrenheit (F) to its equivalent in Celsius (C) and vice
versa. The required formulae are:- C= (F-32)*5/9
F= 9/5*C + 32

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

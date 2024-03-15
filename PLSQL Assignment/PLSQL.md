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
 set @area = 0;
call abc(5,10,@perimeter,@area);
select @perimeter, @area from dual;
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

create table temp(num int, square int, numcube int);
call Q2();
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
set @celsius=0;
call Q3(50.00,@celsius);
select @celsius from dual;
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
call Q6(50,2);
call Q6(50,4);
call Q6(20,4);
select * from ans;
```

# Assignments 2

**2.Select from any table three positive integers representing the sides of a triangle, and
determine whether they form a valid triangle. Hint: In a triangle, the sum of any two
sides must always be greater than the third side.**

```
delimiter //

create procedure q2()
begin
declare output varchar(50);
declare firstSide int;
declare secondSide int;
declare thirdSide int;

    select deptno into firstSide from dept where dname = 'ACCOUNTING';
    select empno into secondSide from emp where ename='SCOTT';
    select mgr into thirdSide from emp where empno=7934;

    if firstSide + secondSide > thirdSide and firstSide + thirdSide > secondSide and secondSide + thirdSide > firstSide then
        set output = "Valid triangle";
    else
        set output = "Invalid triangle";
    end if;

    select output;

end //

delimiter ;

call q2();
```

**3.Check if a given a year is a leap year. The condition is:- year should be (divisible by 4
and not divisible by 100) or (divisible by 4 and divisible by 400.). The year should be
Selected from some table.**

```
delimiter //
create procedure q3()
begin
declare years int;
declare output varchar(50);
select year(hire) into years from emp where empno =7876;

if (mod(years,4)=0 and mod(years,100)!=0) or (mod(years,400)=0)
then
set output= concat(years,' is Leap Year.');
else set output= concat(years,' is not a Leap Year.');
end if;

select output;

end; //
delimiter ;
call q3();
```

**4. Write a program that Selects from any table two character strings. Your program should
then determine if one character string exists inside another character string.**

```
delimiter //
create procedure Q4(in string1 varchar(50),in string2 varchar(50))
begin
    declare output varchar(50);

    if instr(string1, string2) > 0 then
        set output = concat("'", string2, "' exists inside '", string1, "'.");
    else
        set output = concat("'", string2, "' does not exist inside '", string1, "'.");
    end if;

    select output;
end;//
delimiter ;
call q4('radhekrishana','krishana');
```

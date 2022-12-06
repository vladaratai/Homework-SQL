# Homework-SQL
+ [1](#1)
+ [2](#2)
+ [3](#3)
+ [4](#4)
+ [5](#5)
+ [6](#6)
+ [7](#7)
+ [8](#8)
+ [9](#9)
+ [10](#10)
+ [11](#11)
+ [12](#12)
+ [13](#13)
+ [14](#14)
+ [15](#15)
+ [16](#16)
+ [17](#17)
+ [18](#18)
+ [19](#19)
+ [20](#20)
+ [21](#21)
+ [22](#22)
+ [23](#23)
+ [24](#24)




## №1
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=1">Условие</a>

```sql
Select model , speed, hd  From pc 
Where price < 500
```

## №2
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=2">Условие</a>

```sql
Select maker  from  product 
Where product.type = 'printer' Group by maker
```

## №3
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=3">Условие</a>

```sql
select model, ram, screen From laptop Where price > 1000
```

## №4
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=4">Условие</a>

```sql
select * from printer where color = 'y'
```

## №5
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=5">Условие</a>

```sql
Select model ,speed , hd  From pc 
Where (cd = '12x' or cd = '24x') and price < 600
```

## №6
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=6">Условие</a>

```sql
Select distinct Product.maker, Laptop.speed
From Product 
Join Laptop 
On Product.model = Laptop.model
Where hd >= 10
```

## №7
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=7">Условие</a>

```sql
Select distinct product.model, pc.price
From Product Join pc On product.model = pc.model Where maker = 'B'
Union
Select distinct product.model, laptop.price
From product Join laptop On product.model=laptop.model Where maker='B'
Union
Select distinct product.model, printer.price
From product Join printer On product.model=printer.model Where maker='B'
```

## №8
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=8">Условие</a>

```sql
SELECT DISTINCT maker
FROM Product
WHERE type = 'PC'
EXCEPT
SELECT DISTINCT prduct.maker
FROM Product
WHERE type = 'Laptop'
```

## №9
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=9">Условие</a>

```sql
SELECT DISTINCT Maker
FROM Product 
JOIN PC ON PC.model = Product.model
WHERE PC.speed >= 450
```

## №10
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=10">Условие</a>

```sql
SELECT model, price
FROM Printer
WHERE price = (SELECT MAX(price) 
 FROM Printer)
```

## №11
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=11">Условие</a>

```sql
SELECT AVG(speed)
FROM PC
```

## №12
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=12">Условие</a>

```sql
SELECT AVG(speed)
FROM Laptop
WHERE price > 1000
```

## №13
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=13">Условие</a>

```sql
Select sum(pc.speed) / count(*)
From pc
Where pc.model in (select product.model From product
Where product.maker = 'A')

```

## №14
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=14">Условие</a>

```sql
SELECT ships.class, ships.name, country FROM Ships 
JOIN classes on classes.class = ships.class
WHERE numGuns >= 10
```

## №15
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=15">Условие</a>

```sql
Select hd From pc
Group by hd having count(*) >= 2
```

## №16
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=16">Условие</a>

```sql
SELECT DISTINCT pc_1.model, pc_2.model, pc_1.speed, pc_1.ram FROM pc pc_1, pc pc_2 
WHERE pc_1.speed=pc_2.speed AND pc_1.ram=pc_2.ram
and pc_1.model>pc_2.model
```
## №17
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=17">Условие</a>

```sql
SELECT DISTINCT product.type, laptop.model, laptop.speed
FROM laptop, product, pc
WHERE laptop.model = product.model AND
      laptop.speed < (SELECT min(pc.speed) FROM pc)
```
## №18
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=18">Условие</a>

```sql
SELECT
DISTINCT Pt.maker, price
FROM
Printer AS Pr
JOIN
Product AS Pt
ON Pr.model = Pt.model
WHERE
price = (SELECT MIN(price)  FROM Printer WHERE color = 'y')
AND color = 'y'
```
## №19
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=19">Условие</a>

```sql
select maker, AVG(screen) from laptop 
Join product on product.model = laptop.model 
group by maker
```
## №20
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=20">Условие</a>

```sql
Select maker, count(model) from product 
where type = 'PC' group by maker 
having count(model) >= 3
```
## №21
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=21">Условие</a>

```sql
Select maker, MAX(price) max_price FROM pc
Join product on product.model = pc.model 
Group by maker
```
## №22
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=22">Условие</a>

```sql
Select, AVG(price) avg_price
From pc
Where speed > 699 And speed In (Select speed From pc Where > 600) Group By speed
```
## №23
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=23">Условие</a>

```sql
Select maker 
From pc
Join product On product.model = pc.model
Where speed >= 750 
Intersect
Select maker From laptop Join product on product.model = laptop.model Where speed >=750
```
## №24
<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=24">Условие</a>

```sql
Select model From (
Select model, price From pc
Union
Select model, price From laptop
Union 
Select model, price From printer
) this_table Where price = (
Select MAX(price) From(
Select model, price From pc
Union 
Select model,price From laptop
Union
Select model,price From printer
) this_table_2
)
```

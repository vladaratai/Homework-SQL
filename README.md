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

<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=1">Условие</a>


```sql
SELECT AVG(speed)
FROM PC
```

## №12

<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=1">Условие</a>

```sql
SELECT AVG(speed)
FROM Laptop
WHERE price > 1000
```

## №13

<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=1">Условие</a>

```sql
SELECT AVG(speed)
FROM PC JOIN
Product ON Product.model = PC.model
WHERE Product.maker = 'A'
```
## №14

<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=1">Условие</a>

```sql
SELECT Ships.class, name, country
FROM Ships JOIN
Classes ON Classes.class = Ships.class
WHERE Classes.numGuns >= 10
```

## 15

<a taget="blanc" href="https://sql-ex.ru/learn_exercises.php?LN=1">Условие</a>


```sql
SELECT hd
FROM PC
GROUP BY hd
HAVING COUNT(hd) >= 2
```

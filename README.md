# Домашнее задание к занятию "`SQL. Часть 1`" - `Воронин Алексей`

### Задание 1

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

### Решение

```
SELECT DISTINCT district FROM address
WHERE district LIKE 'K%a' AND district NOT LIKE '% %' ;
```
![Скриншот-1](https://github.com/ZetIxzet/sdb-12-02/blob/main/132126.png)

### Задание 2

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года **включительно** и стоимость которых превышает 10.00.

### Решение

```
SELECT * FROM payment
WHERE CAST(payment_date AS DATE) BETWEEN '2005-06-15' AND '2005-06-18' AND amount > 10.00;
```
![Скриншот-2](https://github.com/ZetIxzet/sdb-12-02/blob/main/132126.png)

### Задание 3

Получите последние пять аренд фильмов.

### Решение

```
SELECT * FROM rental
ORDER BY rental_date DESC, rental_id desc LIMIT 5;
```
![Скриншот-3](https://github.com/ZetIxzet/sdb-12-02/blob/main/132126.png)


### Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie. 

Сформируйте вывод в результат таким образом:
- все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
- замените буквы 'll' в именах на 'pp'.

### Решение

```
SELECT REPLACE(LOWER(first_name), 'll', 'pp') , LOWER(last_name) 
FROM customer
WHERE first_name LIKE 'Kelly' OR first_name LIKE 'Willie' ;
```
![Скриншот-4](https://github.com/ZetIxzet/sdb-12-02/blob/main/132126.png)


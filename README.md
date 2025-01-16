# 12-03
12-03 «SQL. Часть 1» Васяева Ирина
# Задание 1
```
SELECT DISTINCT district
FROM addresses
WHERE district LIKE 'K%'       
  AND district LIKE '%a'       
  AND district NOT LIKE '% %';
```
Пояснения по запросу:  
`SELECT DISTINCT district`: выбирает уникальные значения из столбца district.  
`FROM addresses`: указывает, что выборка происходит из таблицы addresses.  
`WHERE district LIKE 'K%'`: фильтрует названия, начинающиеся с буквы "K".  
`AND district LIKE '%a'`: дополнительно фильтрует названия, заканчивающиеся на букву "a".  
`AND district NOT LIKE '% %'`: исключает записи с пробелами в названиях районов.  
# Задание 2
```
SELECT *
FROM rental_payments
WHERE payment_date BETWEEN '2005-06-15' AND '2005-06-18'   
  AND amount > 10.00;                                    
```
Пояснения по запросу:  
`SELECT *`: выбирает все столбцы из таблицы. Вы можете вместо * указать конкретные столбцы, если это необходимо.  
`FROM rental_payments`: указывает, что запрос выполняется на таблице rental_payments.  
`WHERE payment_date BETWEEN '2005-06-15' AND '2005-06-18'`: фильтрует платежи по датам - выбираются только те, которые попадают в указанный диапазон, включая обе даты.  
`AND amount > 10.00`: добавляет условие, что сумма платежа должна превышать 10.00.  
# Задание 3
```
SELECT *
FROM rental_records
ORDER BY rental_date DESC   
LIMIT 5;                    
```
Пояснения по запросу:  
`SELECT *`: выбирает все столбцы из таблицы. При необходимости вы можете указать конкретные столбцы.  
`FROM rental_records`: указывает имя таблицы, где хранятся записи об арендах.  
`ORDER BY rental_date DESC`: сортирует записи по дате аренды в порядке убывания, чтобы последние аренды были первыми.  
`LIMIT 5`: ограничивает результат до пяти самых последних записей.  
# Задание 4
```
SELECT 
    LOWER(REPLACE(first_name, 'll', 'pp')) AS first_name,
    LOWER(REPLACE(last_name, 'll', 'pp')) AS last_name
FROM 
    customers
WHERE 
    (first_name = 'Kelly' OR first_name = 'Willie')
    AND status = 'active';  
```
Пояснения по запросу:  
`LOWER(...)`: приводит строку к нижнему регистру.  
`REPLACE(..., 'll', 'pp')`: заменяет все вхождения букв 'll' на 'pp' в строке.  
`FROM customers`: указывает на таблицу клиентов.  
`WHERE (first_name = 'Kelly' OR first_name = 'Willie')`: фильтр для выбора только тех клиентов, которые имеют имя «Kelly» или «Willie».  
`AND status = 'active'`: дополнительно фильтрует клиентов, чтобы оставить только активных покупателей.  

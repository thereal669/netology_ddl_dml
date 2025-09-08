# Домашнее задание к занятию 1 "`Работа с данными (DDL/DML)`" - `Хавилов Виталий`

## Задание 1

### 1.1. Поднимите чистый инстанс MySQL версии 8.0+ 

```bash
docker run --name mysql -e MYSQL_ROOT_PASSWORD=root -d -p 3306:3306 mysql:8.0.41-debian
```

### 1.2. Создайте учётную запись `sys_temp` 

```sql
CREATE USER 'sys_temp'@'localhost' IDENTIFIED BY 'password';
```

### 1.3. Выполните запрос на получение списка пользователей в базе данных 

```sql
SELECT user FROM mysql.user;
```

Скриншот результата:

![Задание 1.3](https://raw.githubusercontent.com/thereal669/netology_ddl_dml/main/pics/1.png)

### 1.4. Дайте все права для пользователя `sys_temp` 

```sql
GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'localhost';
FLUSH PRIVILEGES;
```

### 1.5. Выполните запрос на получение списка прав для пользователя `sys_temp` 

```sql
SHOW GRANTS FOR 'sys_temp'@'localhost';
```

Скриншот результата:

![Задание 1.5](https://raw.githubusercontent.com/thereal669/netology_ddl_dml/main/pics/2.png)

### 1.6. Переподключитесь к базе данных от имени `sys_temp` 

```bash
mysql -u sys_temp -p
```

### 1.7. Восстановите дамп в базу данных

```bash
mysql -u sys_temp -p < sakila-schema.sql
mysql -u sys_temp -p < sakila-data.sql
```

### 1.8. Сформируйте ER-диаграмму или получите список таблиц

Скриншот результата:

![Задание 1.8](https://raw.githubusercontent.com/thereal669/netology_ddl_dml/main/pics/3.png)

---

## Задание 2

### Таблица с названиями таблиц в БД и их первичными ключами 

| Название таблицы | Название первичного ключа |
|------------------|--------------------------|
| actor            | actor_id                 |
| address          | address_id               |
| category         | category_id              |
| city             | city_id                  |
| country          | country_id               |
| customer         | customer_id              |
| film             | film_id                  |
| film_actor       | actor_id, film_id        |
| film_category    | film_id, category_id     |
| film_text        | film_id                  |
| inventory        | inventory_id             |
| language         | language_id              |
| payment          | payment_id               |
| rental           | rental_id                |
| staff            | staff_id                 |
| store            | store_id                 |

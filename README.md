# Домашнее задание к занятию 12-01 «Базы данных» - Савин Алексей

### Задание 1  
Опишите не менее семи таблиц, из которых состоит база данных:  

- какие данные хранятся в этих таблицах;
- какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.  
Приведите решение к следующему виду:  

Сотрудники (

- идентификатор, первичный ключ, serial,
- фамилия varchar(50),
- ...
- идентификатор структурного подразделения, внешний ключ, integer).

---

  ***Решение***
  База состоит из таблиц (отношений):

1. Сотрудник:
- Идентификатор (первичный ключ serial)
- имя CHAR 50
- фамилия CHAR 50
- дата приёма на работу UnixTimeStamp
- ссылка на ForeignKey таблицы 'Должность'
- ссылка на ForeignKey таблицы 'Оклад'
- ссылка на ForeignKey таблицы 'Структурное подразделение'
- отношение ManyToMany с таблицей 'Проект'
  
2. Должность:  
- Идентификатор (первичный ключ serial)
- название должности CHAR 50
3. Структурное подразделение:
- Идентификатор (первичный ключ serial)
- название подразделения CHAR 50
- ссылка на ForeignKey таблицы 'Тип структурного подразделения'
- ссылка на ForeignKey таблицы 'Адрес филиала'
  
4. Тип структурного подразделения:
- Идентификатор (первичный ключ serial)
- название типа CHAR 50
5. Адрес филиала:
- Идентификатор (первичный ключ serial)
- адрес CHAR 50
6. Проект:
- Идентификатор (первичный ключ serial)
- название проекта CHAR 50
7. Оклад:
- Идентификатор (первичный ключ serial)
- размер оклада NUMERIC или PositiveSmallInteger
- ссылка на ForeignKey таблицы 'Проект'
- ссылка на ForeignKey таблицы 'Должность'
8. Промежуточные таблицы:
- Идентификатор (первичный ключ serial)
- Сотрудник-проект.  

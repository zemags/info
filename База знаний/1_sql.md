**sql**
##### create
```
create user 'username'@'localhost' identified by 'password';
grant all privileges on database_name.* to 'username'@'localhost'; 
create database if not exists database_name;
create table table_1 (id int auto_increment primary key, column_1 varchar(10) not null);
```
##### alter
```
alter table old_name rename to new_name;
alter table new_name add new_column int;
alter talbe new_name drop column new_column;
alter table new_name change column_old_name column_new_name varchar(10) not null;
```
##### drop
```
drop table table_name;
```
##### truncate (clean table, but save table)
```
truncate table table_name;
```
##### constraints (ограничения)
```
default
auto_increment
not null
unique (unique(country, boss_name)) - for one field or combination of fields (country+boss_name)
primary key = unique+nit null
check (age int check(age)>50) or (check(column_1 > 0 and column_1 >= column_2))
```
##### foreign key
```
create table table_1 (id int auto_increment primary key, column_1 varchar(10));
create table table_2 (id int auto_increment primary key, column_2 int, **foreign key** (column_2) references table_1(id));
```
##### insert
```
insert into table_1 (column_1) values ("blabla"), ("blabla2");
insert into table_1 (column_1) select column_2 from table_2;
```
##### update
```
update table_1 set column_1 = "blabla3";
update table_1 set column_1 = "blabla3" where column_2 = "notblabla";
```
##### delete
```
delete from table_1;
delete from table_1 where column_1 = "blabla";
```
##### group by
```
select column_1, max(column_2) from table_1 **group by** column_1;
```
##### having
```
select column_1, max(column_2) from table_1 **group by** column_1 **having** count(*) > 3;
```
##### union
```
без дублей (или со всеми дублями)
select * from table_1 **union [all]** select * from table_2;
```
##### intersect - find all from table_2 who in table_1
```
select column_1 from table_1 **intersect** select column_1 from table_2; (column_1 the same)
```
##### minus - find all from table_2 who not in table_1
```
select column_1 from table_1 **minus** select column_1 from table_2; (column_1 the same)
```
##### views
```
create view view_name(column_1, column_2)
as
select column_1, column_2
from table_1;

create view view_name(column_1, column_2)
as
select column_1, column_2
from table_1 where column_2 > 10
**with check option**;  (if you want to insert to this view values > 10 in column_2 it can't be possible)

create view view_name_2(column_1, column_2)
as
select column_1, column_2
from **view_name** where column_2 > 10
**with local check option**;

with cascaded check option – проверяет запросы на всех уровнях вложенности;
with local check option – проверяет только "верхний" запрос.

drop view view_name;
```
##### index
```
create index index_name on table_name(column_1, column_2);
```
##### trigger - процедуры, которые автоматически запускаются при выполнении определенной операции
##### (insert, update, delete) до (before) или после (after)
```
delimiter $$
create or modify trigger trigger_name
**before** insert on table_1
for each row begin
set new.column_1 = new.column_1 + 12345;
end$$

drop trigger trigger_name;
```

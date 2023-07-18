## Homework #1

### **Таблица employees**

### 1. Создать таблицу employees
- id. serial,  primary key,
- employee_name. Varchar(50), not null
```
create table employees(
	id serial primary key,
	employee_name varchar(50) not null
	);
```

### 2. Наполнить таблицу employee 70 строками
```
insert into employees (employee_name)
values ('Zach Sears'), ('Finnian Douglas'), ('Roman Schultz'), ('Ernest Cobb'), ('Rhodri Bowen'),
	('Tommy-Lee Mcgee'), ('Albert Orozco'), ('Eryn Klein'), ('Maia Nicholson'), ('Mohsin Gonzalez'),
	('Esme Hancock'), ('Yousef Li'), ('Ellis Oliver'), ('Jane Nguyen'), ('Raymond Freeman'),
	('Penny Adkins'), ('Jaydon Shelton'), ('Yuvraj Curtis'), ('Safaa Nolan'), ('Arran Leon'),
	('Henry Bass'), ('Ayla Wilcox'), ('Nevaeh Valdez'), ('Lawrence Myers'), ('Rico Haines'), 
	('Isobelle Cannon'), ('Wayne Campbell'), ('Cordelia Everett'), ('Preston Petersen'), ('Chad Knox'),
	('Valentina King'), ('Myla Farley'), ('Lawson Porter'), ('Lukas Roberts'), ('Uzair Camacho'), 
	('Wilbur Boyer'), ('Claudia Atkinson'), ('Suzanne Trujillo'), ('Isabelle Rhodes'), ('Tiffany Howe'),
	('Fatimah Phelps'), ('Junaid Matthews'), ('Wyatt Saunders'), ('Dominik Oneal'),
	('Esmee Cameron'), ('Katie Roach'), ('Paula Miller'), ('Justin Harrell'), ('Damon Larson'), 
	('Elise Shah'), ('Malaika Dunlap'), ('Alannah Reilly'), ('Mari Cochran'), ('Salman Holder'), 
	('Elliot Holt'), ('Selina Taylor'), ('Gertrude Gutierrez'), ('Alexia Donaldson'), ('Tara Lin'), 
	('Lina Jackson'), ('Keanu Hamilton'), ('Annabel Daugherty'), ('Abdur Lawson'), ('Saif Nielsen'), 
	('Sami Meza'), ('Zackary Kennedy'), ('Jemima Quinn'), ('Diana Melendez'), ('Dan Wood'), ('Elisa Henderson');
```

### Таблица salary

### 3. Создать таблицу salary
- id. Serial  primary key,
- monthly_salary. Int, not null
```
create table salary(
	id serial primary key,
	monthly_salary int not null
	);
```

### 4. Наполнить таблицу salary 15 строками
```
insert into salary (monthly_salary) 
values (1000), (1100), (1200), 
	(1300), (1400), (1500), 
	(1600), (1700), (1800), 
	(1900), (2000), (2100), 
	(2200), (2300), (2400), (2500);
```

### Таблица employee_salary

### 5. Создать таблицу employee_salary
- id. Serial  primary key,
- employee_id. Int, not null, unique
- salary_id. Int, not null
```
create table employee_salary(
	id serial primary key,
	employee_id int not null unique,
	salary_id int not null
	);
```

### 6. Наполнить таблицу employee_salary 40 строками (в 10 строк из 40 вставить несуществующие employee_id)
```
insert into employee_salary (employee_id, salary_id)
values (1, 1), (22, 2), (45, 3), (36, 4), (57, 5),
	(8, 6), (17, 7), (11, 8), (21, 9), (32, 10),
	(5, 11), (9, 12), (10, 13), (65, 14), (38, 15),
	(71, 1), (72, 2), (73, 3), (74, 4), (75, 5),
	(4, 6), (39, 7), (19, 8), (27, 9), (12, 10),
	(76, 11), (77, 12), (78, 13), (79, 14), (80, 15),
	(52, 1), (40, 2), (51, 3), (3, 4), (70, 5),
	(24, 6), (54, 7), (48, 8), (61, 9), (30, 10);
```

### Таблица roles

### 7. Создать таблицу roles
- id. Serial  primary key,
- role_name. int, not null, unique
```
create table roles(
	id serial primary key,
	role_name int not null unique
	);
```

### 8. Поменять тип столба role_name с int на varchar(30)
```
alter table roles
alter column role_name type varchar(30);
```

### 9. Наполнить таблицу roles 20 строками
```
insert into roles (role_name)
values ('Junior Python developer'), ('Middle Python developer'), ('Senior Python developer'),
  ('Junior Java developer'), ('Middle Java developer'), ('Senior Java developer'),
  ('Junior JavaScript developer'), ('Middle JavaScript developer'), ('Senior JavaScript developer'),
  ('Junior Manual QA engineer'), ('Middle Manual QA engineer'), ('Senior Manual QA engineer'),
  ('Project Manager'), ('Designer'), ('HR'), ('CEO'), ('Sales manager'),
  ('Junior Automation QA engineer'), ('Middle Automation QA engineer'), ('Senior Automation QA engineer');
```

### Таблица roles_employee

### 10. Создать таблицу roles_employee
- id. Serial  primary key,
- employee_id. Int, not null, unique (внешний ключ для таблицы employees, поле id)
- role_id. Int, not null (внешний ключ для таблицы roles, поле id)
```
create table roles_employee(
	id serial primary key,
	employee_id int not null unique references employees (id),
	role_id int not null references roles (id));
```

### 11. Наполнить таблицу roles_employee 40 строками:
```
insert into roles_employee (employee_id, role_id)
values (1, 1), (22, 2), (45, 3), (36, 4), (57, 5),
	(8, 6), (17, 7), (11, 8), (21, 9), (32, 10),
	(5, 11), (9, 12), (10, 13), (65, 14), (38, 15),
	(71, 1), (72, 2), (73, 3), (74, 4), (75, 5),
	(4, 6), (39, 7), (19, 8), (27, 9), (12, 10),
	(76, 11), (77, 12), (78, 13), (79, 14), (80, 15),
	(52, 16), (40, 17), (51, 18), (3, 19), (70, 20),
	(24, 16), (54, 17), (48, 18), (61, 19), (30, 20);
```

# Hive_basic_homework

### Create a hive database `hive_odev` and load this data https://raw.githubusercontent.com/erkansirin78/datasets/master/Wine.csv into `wine` table.

 ```bash  
CREATE DATABASE hive_odev;

CREATE TABLE hive odev.wine (
Alcohol FLOAT,
Malic Acid FLOAT,
Ash FLOAT,
Ash_Alcanity FLOAT,
Magnesium INT,
Total Phenols FLOAT,
Flavanoids FLOAT, Hue FLOAT, 0D280 FLOAT,
Nonflavanoid_Phenols FLOAT,
Proanthocyanins FLOAT,
Color_Intensity FLOAT,
Proline INT,
Customer_Segment INT
)
ROW FORMAT DELIMITED
FIELDS TERMINATED BY
LINES TERMINATED BY '\n'
STORED AS TEXTFILE;


load data local inpath '/Wine.csv' into table hive_odev.wine;
```

### 2.In `wine` table filter records that `Alcohol`greater than 13.00 then insert these records into `wine_alc_gt_13` table.

```bash
create table hive_odev.wine_alc_gt_13 as select * from wine where Alcohol>13; 
 ```


### 3.  Drop `hive_odev` database including underlying tables in a single command.
```bash
drop database hive_odev cascade;
```


### 4.Load this https://raw.githubusercontent.com/erkansirin78/datasets/master/hive/employee.txt into table `employee` in `company` database. 
```bash
CREATE DATABASE company;

CREATE TABLE company.employee (
name STRING,
work_place ARRAY<STRING>,
gender_age STRUCT<gender: STRING, age: INT>,
skills_score MAP<STRING, INT>
)
ROW FORMAT DELIMITED
FIELDS TERMINATED BY ''
COLLECTION ITEMS TERMINATED BY','
MAP KEYS TERMINATED BY ':'
STORED AS TEXTFILE
TBLPROPERTIES ('skip.header.line.count'='1');
```

### 5. Write a query that returns the employees whose Python skill is greater than 70.
```bash
select * from employee where employee.skills["Python"]>70;
```
  

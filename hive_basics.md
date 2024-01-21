# Apache Hive ile Tablo İşlemleri ve Veri Manipülasyonu


### Create a hive database `hive_odev` and load this data https://raw.githubusercontent.com/erkansirin78/datasets/master/Wine.csv into `wine` table.

 ```bash  
CREATE DATABASE hive_odev;


create table if not exists wine(Wine int,
Alcohol float,
Malicacid float,
Ash float,
Acl int,
Mg float,
Phenols float,
Flavanoids float,
Nonflavanoidphenols float,
Proanth float,
Color.int float,
Hue float,
OD float,
Proline int)

ROW FORMAT DELIMITED
FIELDS TERMINATED BY
LINES TERMINATED BY '\n'
STORED AS TEXTFILE
tblproperties('skip.header.line.count'='1');



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

![Ekran görüntüsü 2024-01-21 144900](https://github.com/irem6142/Open_Source_Big_Data_Basics/assets/83772404/e93eca8c-e21c-40c3-9a93-8836fe7c23ed)


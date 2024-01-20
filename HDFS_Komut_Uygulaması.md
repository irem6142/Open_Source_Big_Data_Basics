#  HDFS Komut Uygulaması

### 1. wine.csv dosyasını hdfs/user/train/hdfs_odev klasörüne aktarınız
```
 hdfs dfs -mkdir  /tmp/hdfs/odev

 hdfs dfs -mkdir  /user/train/hdfs_odev

 hdfs dfs -put wine.csv /user/train/hdfs_odev

```
### 2.HDFS'te bulunan /user/train/hdfs_odev/Wine.csv dosyasını /tmp/hdfs_odev klasörüne kopyalayınız
```
 hdfs dfs -cp  /user/train/hdfs_odev/wine.csv  /tmp/hdfs_odev
```

### 3. HDFS'te bulunan /tmp/hdfs_odev klasörünü geri dönüşümü atlayarak siliniz
```
hdfs dfs -rm -r -skipTrash /tmp/hdfs_odev

```


### 4 /user/train/hdfs_odev/Wine.csv dosyasını HDFS web ara yüzünden listeleyiniz
```
http://localhost:9870/explorer.html#/user/train/hdfs_odev
```
![Ekran görüntüsü 2024-01-20 235601](https://github.com/irem6142/Open_Source_Big_Data_Basics/assets/83772404/dc4735d3-f7e0-4971-86e5-0a34c0dc819c)

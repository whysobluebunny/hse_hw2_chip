# Для исследования была выбрана клеточная линия HeLa-S3 и гистоновая метка H3K27ac.
## [Collab](https://colab.research.google.com/drive/1l7UA337chu7f1U688NHymSyIday1OENJ?usp=sharing)
# Анализ выдачи FastQC
## Реплика 1: ENCFF000BBY
![image](https://user-images.githubusercontent.com/43317906/222156204-878df1f1-733f-4d84-8ff8-573f9ab956da.png)
![image](https://user-images.githubusercontent.com/43317906/222156287-fa4efef3-09be-4d61-8bd2-8edf85fb10e5.png)
![image](https://user-images.githubusercontent.com/43317906/222156317-c539bd31-ab6e-46fd-bd72-2cb5a5f7530b.png)
![image](https://user-images.githubusercontent.com/43317906/222156396-9b9f30cd-f293-4e61-b8da-49677572331a.png)

#### Видим, что в отчете нет графиков, непрошедших качество, поэтому не делаем фильтрацию и подрезание чтений.
## Реплика 2: ENCFF000BBZ
![image](https://user-images.githubusercontent.com/43317906/222156455-1ed9c9da-15e8-4db1-90cb-2196fcb1d4b4.png)
#### Такое качество не подходит, поэтому воспользуемся trimmomatic
![image](https://user-images.githubusercontent.com/43317906/222156708-06fb73c8-7574-4a2a-83fa-f3a2338ea8a5.png)
![image](https://user-images.githubusercontent.com/43317906/222156767-747489d3-9e71-499a-a56c-6e58d83638ef.png)
![image](https://user-images.githubusercontent.com/43317906/222156803-81af6011-6c7a-4423-b1e5-6e1cb2e1bbdd.png)
![image](https://user-images.githubusercontent.com/43317906/222156864-86d0a480-fcbc-40b9-b537-3638b193993e.png)
#### Качество чтений улучшилось. В отчете нет графиков, непрошедших качество.
## Контроль ENCFF000BAO
![image](https://user-images.githubusercontent.com/43317906/222157765-9184315d-0b2c-4a4a-b783-da343e5ec12b.png)
![image](https://user-images.githubusercontent.com/43317906/222157903-c4be0dcd-ba35-410d-a56d-ce99fbfa4c44.png)
![image](https://user-images.githubusercontent.com/43317906/222157985-a3257879-d846-4264-b272-239391030227.png)
![image](https://user-images.githubusercontent.com/43317906/222158091-fc2e607c-f4fd-4db4-b1e6-ffd73fb1aa86.png)
В отчете нет графиков, непрошедших качество.
# Выравнивание на 21 хромосому
|                       |**всего ридов**|**выровненные 0 раз**|**выровненные ровно 1 раз**|**выровненные более 1 раза**|
|-----------------------|---------------|---------------------|---------------------------|----------------------------|
|ENCFF000BBY (реплика 1)|25066121|22082449 (88.10%)|587337 (2.34%)|2396335 (9.56%)|
|ENCFF000BBZ (реплика 2)|18049872|15708094 (87.03%)|475211 (2.63%)|1866567 (10.34%)|
|ENCFF000AOB (контроль) |44138120|38054247 (86.22%)|1303329 (2.95%)|4780544 (10.83%)|
#### Итого доля уникальных выравниваний оказалась в районе 2.5%, поскольку выравнивание происходило только по одной хромосоме
# Диаграммы Венна
## Реплика 1: ENCFF000BBY
![image](https://user-images.githubusercontent.com/43317906/222200914-33715d09-c160-4c41-abd7-3fc9f212a790.png)
![image](https://user-images.githubusercontent.com/43317906/222201022-3e6de257-5344-4d1d-a7ab-a87f60a7bedc.png)

## Реплика 2: ENCFF000BBZ
![image](https://user-images.githubusercontent.com/43317906/222201122-6e6b4325-817e-4f18-a99e-2c94ee567704.png)
![image](https://user-images.githubusercontent.com/43317906/222201258-ed13e9ac-0303-4241-836e-2346cfc7bc56.png)
#### Пересечение достаточно небольшое, но стоит учитывать, что в нашем случае выравнивание происходило только по одной хромосоме, а так же, вероятно, могли использоваться инструменты отличные от тех, что использовались в сравниваемом образце.

# Доп часть
![image](https://user-images.githubusercontent.com/43317906/222259623-48c016a1-e54b-4152-aadc-9fd9b67a886f.png)
#### После 3 с лишним часом скрипт вычисления матрицы успешно свалился с эксепшеном, с чем себя я и поздравляю
#### как-то так вышло, что мой bigWig файл в 10 раз больше того, что был в примере
#### просто делюсь болью, спасибо

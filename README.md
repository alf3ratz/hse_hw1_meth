# hse_hw1_meth  
Ссылка на коллаб: [тык](https://colab.research.google.com/drive/1vAPpML5hLf_LxAgX2YQBcddD2EExCZ88?usp=sharing)  

# FastQC
## Basic Statistics
**BS-seq**  
![image](https://user-images.githubusercontent.com/49417479/155021915-3075eb63-cee1-4dcc-a680-2941df9f3581.png)  
**РНК**  
![image](https://user-images.githubusercontent.com/49417479/155022130-efe49474-377b-4393-bb9a-0508b9196221.png)  
Можно заметить, что процент GC для рнк, как минимум больше, а для некоторых последовательностей больше в несколько раз.   

## Per sequence GC content
**BS-seq**  
![image](https://user-images.githubusercontent.com/49417479/155022749-35764c0e-4a1f-4592-869a-8f6873800f3d.png)  
**РНК**  
![image](https://user-images.githubusercontent.com/49417479/155022812-1a55f7c8-a799-47cc-b4fb-b67a99e47088.png)  

**В случае рнк имеем нормально распределение, в случае с bs-seq график представляет из себя что-то непонтное (для меня) с перепадами значений**  

# Работа с bam файлами  
- Числом ридов, закартированных на участки
  - 11347700-11367700
    - 8cell: 1090
    - epiblast: 2328
    - icm: 1456
  - 40185800-40195800
    - 8cell: 464
    - epiblast: 1062
    - icm: 630
# Процент дедупликации  
- 8cell: ~82%
- epiblast: ~97%
- icm: ~91%

# Скрипт
```shell
!ls *pe.bam | xargs -P 4 -tI{} deduplicate_bismark  --bam  --paired  -o s_{} {}
```

# Метелирование
### SRR5836473  
![image](https://user-images.githubusercontent.com/49417479/155021216-75d63157-3a7c-4717-9af0-932f71501a5e.png)  
![image](https://user-images.githubusercontent.com/49417479/155021240-9911a59f-13c3-4cbc-a9ee-da4626b24260.png)  


### SRR3824222
![image](https://user-images.githubusercontent.com/49417479/155021275-92f9f0b6-e5c1-404f-843b-79172cbc6e84.png)
![image](https://user-images.githubusercontent.com/49417479/155021299-48066e14-c339-49fd-8ac6-6cb6be682d0f.png)


### SRR5836475
![image](https://user-images.githubusercontent.com/49417479/155020968-8fcd2485-6327-4394-b12b-e72f0a4ecf8e.png)
![image](https://user-images.githubusercontent.com/49417479/155020987-231fa3f1-6768-4284-9b48-224a79515fb7.png)

# Гистограммы распределения метилирования цитозинов по хромосоме
![image](https://user-images.githubusercontent.com/49417479/155021515-6a6f09e8-c08f-4e87-82ef-0cdf59a78ffc.png)
![image](https://user-images.githubusercontent.com/49417479/155021537-cd01b16b-7b25-4106-b1bf-5e0f3d3ea961.png)
![image](https://user-images.githubusercontent.com/49417479/155021568-1b674fb7-9b3d-49f2-8ad2-d4f2a68cb7b2.png)

# Визуализация уровня метилирования и покрытия
![image_meth](https://user-images.githubusercontent.com/49417479/155021682-735d415a-eb89-404e-9ac6-18f1ac8bbbfd.png)
**Покрытие 8cell**
![image_cov_SRR5836473](https://user-images.githubusercontent.com/49417479/155021757-5930e2e3-7d0a-47f6-9d3f-df318caa4932.png)
**Покрытие epiblast**
![image_cov_epiblast (1)](https://user-images.githubusercontent.com/49417479/155021801-c2e18610-902b-422e-999f-a29bc444927a.png)

**Покрытие icm**
![image_cov_icm](https://user-images.githubusercontent.com/49417479/155021730-df550da4-2c23-410d-aa33-7486520dbc8a.png)


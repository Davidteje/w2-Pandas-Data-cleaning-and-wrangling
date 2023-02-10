# -Shark-attacks-David-Tejedor

![image](https://user-images.githubusercontent.com/115221622/199080090-ff51c0e1-ff5e-4580-82d0-6859aaa2ee7e.png)

### DATA SET ORIGINAL: attacks.csv

### INDICACIONES RECIBIDAS:
- Para borrar columnas deben tener almenos 80% valores nulos.
- Al menos deben quedar 6000 filas.
- Mismo tipo de dato por columna.

### PLAZO DEL PROYECTO
2 días

### CONSIDERACIONES ADOPTADAS DURANTE EL PROYECTO:
- Durante el proceso de limpieza del df se ha dado prioridad a las siguientes columnas de datos, ya que son las que permitirán obtener unas primeras estadísticas más significativas:
    - Year
    - Type
    - Country
    - Sex
    - Age
    - Fatal(y/n)
    - Time
    - Species

### PROCESO DE LIMPIEZA REALIZADO:
- Se importan las librerías Numpy y Pandas
- Se importa el fichero csv y se realiza una copia del df original.
- Se realiza una exploración inicial del df.
    - Dimensiones originales: (25723, 24)
    - Nº columnas = 22 ['Case Number', 'Date', 'Year', 'Type', 'Country', 'Area', 'Location',
       'Activity', 'Name', 'Sex ', 'Age', 'Injury', 'Fatal (Y/N)', 'Time',
       'Species ', 'Investigator or Source', 'pdf', 'href formula', 'href',
       'Case Number.1', 'Case Number.2', 'original order', 'Unnamed: 22',
       'Unnamed: 23']
    - Información de memoria, valores nulos y tipo de datos por columna. (memory usage: 22.8 MB)
- Se clasifican las columnas en numéricas (2) y categóricas (20)
- Se identifican los valores nulos en el df, totales y en %.
    - Exsiten 5 columnas con +80% de valores nulos: ['Age', 'Time', 'Species ', 'Unnamed: 22', 'Unnamed: 23']
    - En el resto de columnas el % de valores nulos es alto también, sin superar el 80%.
    - Se realiza gráfico de nulos en el df.
        - Se aprecia que más de 2/3 de las filas son nulas
            - Se borran las filas que sean completamente nulas
- Se borran las filas duplicadas.
- Se realiza copia del df (data1) y de las dimensiones actuales (data1_dim) tras el borrado realizado. 
- Se realiza la exploración de valores nulos por columnas numéricas y categóricas:
    - Se borran las columnas 'Unnamed: 22' y 'Unnamed: 23' por tener casi el 100% de valores nulos.
- Se realiza un renombrado de columnas.
- Se exploran los valores nulos por columnas y se realiza revisión de valores inconsistentes:
    - Para la mayoría de columnas se han indicado 'unknowns' si no era posible obtener el dato faltante por la información de otras columnas.
    - Se ha creado una nueva columna 'time_2' donde se identifica la etapa del día en la que se registró el ataque en la columna 'time'.
    - Se ha creado una nueva columna 'species_2' donde se agrupan las especies de la columna 'sepcies'.
- Se ha detectado que existen valores "invalid" en las columnas species (103) y type (547). 103 en ambas columnas. Se realizará un Check antes de proceder a borrarlas.
- Se han calculado datos estadísticos (moda, media, mediana, desviación estándar, máx, mín) de las columnas que se han considerado como significativas.
- Se ha revisado y optimizado la memoria utilizada mediante la conversión de las columnas de objeto a categóricas y reducir el tipo de dato de las numéricas. (optimización memory usage: de 10,4 MB a 7,5 MB)

##### TÉCNICAS DE DATA CLEANING UTILIZADAS:
- null values
- columns drop 
- duplicated data 
- string manipulation
- apply fn
- categorize
- otras

### Entregables:
- carpeta src con el jupyter notebook utilizado (clean.ypynb) un otro jupyter notebook (funciones.ypnb) con las funciones utilizadas
- carpeta data:
    - fichero csv 'attacks_clean' tras la limpieza realizada
    - fichero excel 'attacks_clean_con gráficos_basico' con algunos gráficos muy básicos y datos concluyentes más relevantes
- carpeta ppt:
    - presentación muy básica del proyecto realizado



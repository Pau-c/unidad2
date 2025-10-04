# Presentación
<img width="1024" height="520" alt="Copia de Cheers!" src="https://github.com/user-attachments/assets/bc04834d-28b5-401d-a99a-4737208591eb" />



---

## Integrantes

| Nombre                        | Correo Electrónico             | Usuario Github |
|-------------------------------|--------------------------------|----------------|
| Ariel Omar Leche              | ariel.leche@gmail.com          | ARielleche     |
| Diego Ariel Gutierrez         | dgutierrez.m79@gmail.com       | Diego-wert89   |
| José Alberto Rubio            | rubiojosealberto@gmail.com     | rubiojar       |
| Maria Paula Coba              | mpcobas@gmail.com              | Pau-c          |
| Mauro Ruben De Natale         | maurodenatale@gmail.com        | M3T30R0-dev    |



> [!TIP]
> [Live Demo](https://deepnote.com/workspace/test-a96860ea-b228-4e9e-a13d-9edd20f60d93/project/MP-Cs-Untitled-project-a2cd30de-aa34-492f-bd7f-baf47d78ec21/notebook/ej3u2-47c02c388b264ca69ce0f37ecfdb9215?utm_content=a2cd30de-aa34-492f-bd7f-baf47d78ec21)

## Descripción

En este proyecto de python se analizan las tendencias musicales en streaming medida por Billboard desde el año 2013 hasta 2025.
Se  guarda el dataset en Supabase, se lo recupera en un dataframe y se lo trabaja en un notebook de Jupyter para su exploración y visualización.

## Instrucciones 
### - Bajar dataset, nos vamos a centrar en el archivo `streaming_songs.csv`
>[Dataset original](https://www.kaggle.com/datasets/ludmin/billboard?resource=download)

## PROCESO ETL 

      ##Proceso exploratorio

            Nombre de archivo CVS descargado= streaming_songs.csv
            Cantidad de columnas: 8
            Date,Song,Artist,Rank,Last Week,Peak Position,Weeks in Charts,Image URL
            Cantidad de registros:33050
            Diccionario de dataset (función de cada columna y tipo de dato) 
            Limpieza ( se borra última columna  “ image URL” )   
            Cantidad de registros (null o faltantes) por columna  
                    Date(100% ok),Song,Artist(100% ok),Rank(100% ok),Last Week(100% ok),Peak Position(100% ok),Weeks in Charts(100% ok)

``` 
      
      # DICCIONARIO DE DATOS DEL DATASET
            
                    1-Date: Tipo: Fecha (formato yyyy/mm/dd) Descripción: Fecha en la que se registró el ranking de la canción.
                    2-Song: Tipo: Texto (string) Descripción: Nombre de la canción en el ranking.
                    3-Artist: Tipo: Texto (string) Descripción: Nombre del artista o grupo musical (puede incluir “Featuring” sí hay colaboraciones).
                    4-Rank: Tipo: Numérico entero Descripción: Posición actual de la canción en el ranking (1 = primer lugar).
                    5-Last_Week:Tipo: Numérico entero  Descripción: Posición que ocupaba la canción en la semana anterior.
                    6-Peak_Position:Tipo: Numérico entero  Descripción: Mejor posición alcanzada por la canción en el ranking hasta la fecha.
                    7-Weeks_in_Charts:Tipo: Numérico entero Descripción: Número de semanas que la canción lleva en el ranking.

              
```	
      ##   Proceso de Transformación 
		    Nota: usar cualquier herramienta de edición o código.
		    Limpieza ( se borra última columna  “ image URL”)
		    Editar CSV  creando  columna ID (tabulación “Id,”)
			                        ID,Date,Song,Artist,Rank,Last Week,Peak_Position,Weeks_in_Charts
		    Editar campos null o con “-” (guiòn) con número 0
		    Nombre de columnas colocar “_” en sus nombres de las columnas
                                    ID,Date,Song,Artist,Rank,Last Week,Peak_Position,Weeks_in_Charts
            Generar nuevo archivo .CSV con nombre= dataset_artistas_CSV_PARA_BD.csv

     
---
## Base de datos en Supabase 
- crear nuevo proyecto: elegir region y password (generar password, copiarlo y guardarlo)
- Ir a la barra de la izq, table editor, crear nueva tabla, elegir nombre: `Dataset_Ranking`, click en boton importar data de .CSV -> elegir archivo `dataset_artistas_CSV` y guardar.
- En barra lateral ir a `project settings` -> api keys y copiar la de anon public
- En barra lateral ir a `data api`: copiar direccion de project url para usar en los siguientes pasos.
- Para que se tenga acceso a la tabla en la barra lateral ir a authentication -> policies y `Enable read access for all users`
  Nota: se encuentra scrip de creacion de tabla e insert de los 33050 registros en repositorio=> unidad2\archivos\Creacion_e_insert_Dataset_Ranking_full.sql , podria usar la consola de supabase de 1000 regristros para insert manualmente.

  En el repo puede encontrar el data dataset original, el transformado en csv a cargar en supabase y el scrip para crear tabla e insert de registros.
  archivos/
│   ├── Creacion_e_insert_Dataset_Ranking_full.sql
│   ├── dataset_artistas_CSV.csv
│   └── streaming_songs_original.csv
---
``` 
## ⚙️ Estructura del Repositorio

UNIDAD2/
├── .github/
├── .ipynb_checkpoints/
│   └── ej3u2-checkpoint.ipynb
├── .venv/
│   ├── etc/
│   ├── Lib/
│   ├── Scripts/
│   └── share/
├── .lock
├── pyvenv.cfg
├── archivos/
│   ├── Creacion_e_insert_Dataset_Ranking_full.sql
│   ├── dataset_artistas_CSV.csv
│   └── streaming_songs_original.csv
├── unidad2/
├── .env
├── .gitignore
├── .python-version
├── ej3u2.ipynb
├── pyproject.toml
├── README.md
└── uv.lock


``` 
## 🛠️ Requisitos e Instalación

<!-- PROJECT SHIELDS -->
[![deepnoteBadge][deepnote-shield]][deepnote-url]
[![pythonBadge][python-shield]][python-url]
[![pandasBadge][pandas-shield]][pandas-url]
[![plotlyBadge][plotly-shield]][plotly-url]
[![uvBadge][uv-shield]][uv-url]
[![supabaseBadge][supabase-shield]][supabase-url]
[![jupyterBadge][jupyter-shield]][jupyter-url]
[![dotenvBadge][dotenv-shield]][dotenv-url]
<!-- PROJECT SHIELDS -->

***************************************************************************************************************
PASOS PARA USAR IDE con UV y COMENZAR DESA
****************************************************************************************************************

### - Instalar uv en la pc si es necesario (en terminal de Windows):

   Abrir un pront CMD en win  o temrinal ID, ver el pront con PS:>    y ejecutar
```
 powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```
### - Instalar uv en la pc si es necesario (en terminal de Linux):

Abrir una temrinal y ejecutar

# Instalar curl si no lo tienes
sudo apt update
sudo apt install curl

# Descargar e instalar uv
curl -LsSf https://astral.sh/uv/install.sh | sh

# Recargar el profile 
source ~/.bashrc  # Para Bash
# o
source ~/.zshrc   # Para Zsh
```

### - Clonar repo:
```
git clone https://github.com/Pau-c/unidad2.git
```


### - Abrir proyecto en un IDE
### - Crear un archivo en la raíz del proyecto llamado .env
- Dentro pegar la url y la key de supabase que se copiaron antes siguiendo este formato (sin espacios ni comillas):
>SUPABASE_URL=https://nbctuthbio.supabase.co

>SUPABASE_KEY=eyJhbGciOiJIUzI1NiIsInR5cCI6I

### - Crear entorno virtual:
Si todavía no se instaló uv en el sistema como en el primer paso, en terminal: `pip install uv` y luego  ejecutar:
```
uv venv
```

### - Sincronizar entorno virtual al instalar el proyecto y luego de cada cambio en el .toml
```
uv sync
```

### -Elegir kernel
>Para que el código del notebook funcione,  indicarle a VS Code que utilice el Python >que está dentro del nuevo entorno. Esto se hace dentro de la interfaz del notebook:

> [!IMPORTANT]
> Abrir el archivo `.ipynb` en VS Code.
> 1. Hacer clic en el selector del kernel (la esquina superior derecha).
> 2. Seleccionar otro kernel.
> 3. Elegir el kernel que tenga el nombre del proyecto.


#### asegurarse estar en el etorno correcto y activado: De ser necesario correr en terminal: `.venv\Scripts\activate` .venv/Scripts/activate
#### en linux el comando es `source .venv/bin/activate`

## correr archivo en terminal con:

```
 uv run --env-file .env jupyter lab
```

> - Una vez abierto el notebook .ipynb en el browser, en la esquina superior derecha Hacer clic en `ipkernel` y elegir `start python kernel -Python 3`. de ser necesario ir al menú: run -> `restart kernel and run all cells`


<!-- PROJECT SHIELDS VARIABLES-->
[deepnote-shield]:https://img.shields.io/badge/Live-Deepnote-black?style=flat&labelColor=%23808080k&color=de6d40&logo=deepnote&logoColor=white
[deepnote-url]: https://deepnote.com/
[dotenv-shield]:https://img.shields.io/badge/env-dotenv-black?style=flat&labelColor=%23808080k&color=fec260&logo=dotenv&logoColor=white
[dotenv-url]:https://pypi.org/project/python-dotenv/
[pandas-shield]:https://img.shields.io/badge/Data_analysis-Pandas-black?style=flat&labelColor=%23808080k&color=453076&logo=pandas
[pandas-url]:https://pandas.pydata.org/
[python-shield]:https://img.shields.io/badge/Language-Python-black?style=flat&labelColor=%23808080k&color=2a0944&logo=python&logoColor=white
[python-url]: https://www.python.org/
[plotly-shield]:https://img.shields.io/badge/Data_Viz-Plotly-black?style=flat&labelColor=%23808080k&color=9ABF80&logo=plotly&logoColor=white
[plotly-url]: https://plotly.com/python/
[uv-shield]:https://img.shields.io/badge/Dependencias-UV-black?style=flat&labelColor=%23808080k&color=2a0944&logo=uv&logoColor=white
[uv-url]: https://github.com/astral-sh/uv
[supabase-shield]:https://img.shields.io/badge/DB-supabase-black?style=flat&labelColor=%23808080k&color=166866&logo=supabase&logoColor=white
[supabase-url]: https://supabase.com/
[jupyter-shield]:https://img.shields.io/badge/Notebook-jupyter-black?style=flat&labelColor=%23808080k&color=fec260&logo=Jupyter&logoColor=white
[jupyter-url]: https://jupyter.org/



## 🔄 Flujo de Trabajo del Proyecto

Este diagrama ilustra el proceso completo, desde la obtención de datos hasta la visualización final.

1. **DATOS FUENTE**
   - Descarga del archivo `streaming_songs.csv` (Kaggle).

2. **PROCESO ETL (Transformación)**
   - **Limpieza de Datos:** Eliminar columnas y normalizar nombres.
   - **Creación de ID:** Añadir columna de identificador único.
   - **Manejo de Nulos:** Reemplazar valores faltantes (`-` o `null`) por `0`.
   - **Resultado:** Generación del archivo limpio `dataset_artistas_CSV_PARA_BD.csv`.

3. **CARGA A LA BASE DE DATOS**
   - Importación del CSV limpio para crear la tabla `Dataset_Ranking` en **Supabase**.

4. **CONFIGURACIÓN DEL ENTORNO DE DESARROLLO**
   - Clonar el repositorio y configurar las credenciales en el archivo **`.env`**.
   - Crear y sincronizar el entorno virtual con **`uv venv`** y **`uv sync`**.

5. **ANÁLISIS Y EXPLORACIÓN (JUPYTER)**
   - La Notebook (`ej3u2.ipynb`) se conecta a Supabase (usando el `.env`).
   - Se recuperan los datos en un DataFrame de Pandas.
   - Se realiza el Análisis, Exploración y **Visualización con Plotly**.

6. **VISUALIZACIÓN Y PRODUCCIÓN**
   - **Pruebas Locales:** Ejecución con `uv run jupyter lab`.
   - **Demo en Nube:** Demostración final en **Deepnote.com**.

---


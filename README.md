# Presentación
<img width="1024" height="520" alt="Copia de Cheers!" src="https://github.com/user-attachments/assets/bc04834d-28b5-401d-a99a-4737208591eb" />



#######################################################################################


## Integrantes

- ARIEL OMAR LECHE
- DIEGO ARIEL GUTIERREZ MIRANDA
- JOSE ALBERTO RUBIO
- MARIA PAULA COBAS
- MAURO RUBEN DE NATALE

> [!TIP]
> [Live Demo](https://deepnote.com/workspace/test-a96860ea-b228-4e9e-a13d-9edd20f60d93/project/MP-Cs-Untitled-project-a2cd30de-aa34-492f-bd7f-baf47d78ec21/notebook/ej3u2-47c02c388b264ca69ce0f37ecfdb9215?utm_content=a2cd30de-aa34-492f-bd7f-baf47d78ec21)

## Instrucciones 
### - Bajar dataset, nos vamos a centrar en el archivo `streaming_songs.csv'
[Dataset original](https://www.kaggle.com/datasets/ludmin/billboard?resource=download)

#PROCESO ETL 

	Proceso exploratorio
            Nombre de archivo CVS descargado= streaming_songs.csv
            Cantidad de columnas: 8
            Date,Song,Artist,Rank,Last Week,Peak Position,Weeks in Charts,Image URL
            Cantidad de registros:33050
            Diccionario de dataset (función de cada columna y tipo de dato) 
            Limpieza ( se borra última columna  “ image URL”    
            Cantidad de registros (null o faltantes) por columna  
                    Date(100% ok),Song,Artist(100% ok),Rank(100% ok),Last Week(100% ok),Peak Position(100% ok),Weeks in Charts(100% ok)


                ######################-DICCIONARIO DE DATOS DEL DATASET-########### 

                    1-Date: Tipo: Fecha (formato yyyy/mm/dd) Descripción: Fecha en la que se registró el ranking de la canción.
                    2-Song: Tipo: Texto (string) Descripción: Nombre de la canción en el ranking.
                    3-Artist: Tipo: Texto (string) Descripción: Nombre del artista o grupo musical (puede incluir “Featuring” sí hay colaboraciones).
                    4-Rank: Tipo: Numérico entero Descripción: Posición actual de la canción en el ranking (1 = primer lugar).
                    5-Last_Week:Tipo: Numérico entero  Descripción: Posición que ocupaba la canción en la semana anterior.
                    6-Peak_Position:Tipo: Numérico entero  Descripción: Mejor posición alcanzada por la canción en el ranking hasta la fecha.
                    7-Weeks_in_Charts:Tipo: Numérico entero Descripción: Número de semanas que la canción lleva en el ranking.

                ######################################################################
		
    Proceso de Transformación 
		    Nota: usar cualquier herramienta de edición o código.
		    Limpieza ( se borra última columna  “ image URL”
		    Editar CSV  creando  columna ID (tabulación “Id,”)
			                        ID,Date,Song,Artist,Rank,Last Week,Peak_Position,Weeks_in_Charts
		    Editar campos null o con “-” (guiòn) con número 0
		    Nombre de columnas colocar “_” en sus nombres de las columnas
                                    ID,Date,Song,Artist,Rank,Last Week,Peak_Position,Weeks_in_Charts
            Generar nuevo archivo .CSV con nombre= dataset_artistas_CSV_PARA_BD.csv

     Proceso de migración a BD ( corregir que hacemos con el tema del scrip)
		    importar CVS directo a BD



## 🛠️ Requisitos e Instalación
Ariel propone : aca poner resumen de librerias, softowre / programas con sus versiones, link y version de github, notebook y su version,


### - Instalar uv en la pc si es necesario

### - Clonar repo:
>git clone https://github.com/Pau-c/unidad2.git
## ⚙️ Estructura del Repositorio

ariel Propone: aca detallar cada rama y que funcion cumple cada item



### - Crear entorno virtual:
>uv venv


### - Sincronizar entorno virtual al instalar el proyecto y luego de cada cambio en el .toml
>uv sync


### -Elegir kernel


```
Para que el código del notebook funcione,  indicarle a VS Code que utilice el Python que está dentro del nuevo entorno. Esto se hace dentro de la interfaz del notebook:
```



> [!IMPORTANT]
> Abrir el archivo `.ipynb` en VS Code.
> 1. Hacer clic en el selector del kernel (la esquina superior derecha).
> 2. Seleccionar otro kernel.
> 3. Elegir el kernel que tenga el nombre del proyecto.


#### asegurarse estar en el etorno correcto y activado: De ser necesario correr en terminal: `.venv\Scripts\activate`

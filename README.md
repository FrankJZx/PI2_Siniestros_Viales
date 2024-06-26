# Análisis de Homicidios por Siniestros Viales en la Ciudad Autónoma de Buenos Aires, Argentina

![Imagen](imagenes/imagen_1.jpg)

# Presentación

En este proyecto, nos adentramos en el rol de un Analista de Datos dentro del equipo de consultoría de una empresa dedicada al estudio de la movilidad y la seguridad vial. Colaboramos con el Observatorio de Movilidad y Seguridad Vial (OMSV) bajo la Secretaría de Transporte del Gobierno de la Ciudad Autónoma de Buenos Aires (CABA), con el fin de analizar datos relacionados con homicidios en accidentes de tráfico ocurridos en la ciudad entre los años 2016 y 2021.

El propósito principal de esta iniciativa es brindar información valiosa que contribuya a la toma de decisiones por parte de las autoridades locales, enfocadas en la reducción de la cantidad de víctimas fatales en accidentes viales. Este proyecto abarcará un detallado informe que describirá las tareas realizadas, las metodologías empleadas y las conclusiones más relevantes obtenidas a partir del análisis de datos. Asi mismo, se desarrollará un tablero interactivo que facilitará la visualización y comprensión de los datos recopilados.

# Marco Contextual

Los incidentes viales, siniestros viales o accidentes de tráfico, constituyen eventos donde vehículos se ven implicados en espacios públicos. Estos sucesos pueden originarse por múltiples razones, como colisiones entre automóviles, motocicletas, bicicletas o peatones, atropellos, impactos contra objetos fijos e incluso volcaduras de vehículos. Las repercusiones de estos eventos abarcan desde daños materiales hasta lesiones graves o, lamentablemente, pérdidas fatales para los involucrados.

En la Ciudad Autónoma de Buenos Aires (CABA), los siniestros viales representan una preocupación significativa debido al intenso flujo de tráfico y la alta densidad poblacional. Según el último censo realizado en 2022, la población de CABA se estima en 3,120,612 habitantes, distribuidos en una superficie de 200 km². Esta realidad subraya la importancia de abordar de manera efectiva las medidas de seguridad vial en la región.

# Datos y Tecnologías Utilizadas

En este proyecto, se trabajó con la Base de Víctimas Fatales en Siniestros Viales en formato Excel, que contiene dos pestañas de datos: ["Hechos"](datasets\homicidios.xlsx)  y ["Victimas"](datasets\homicidios.xlsx). Estas incluyen información sobre los eventos, víctimas, edad, sexo, modo de desplazamiento, etc.

El análisis se basó en la exploración y limpieza de datos utilizando Python y las bibliotecas Pandas, Numpy, Datetime, Matplotlib, Seaborn y Folium. Python y Pandas se emplearon para la extracción, transformación y carga [Etl](ETL.ipynb)  de datos. Para el análisis exploratorio de datos [Eda](EDA.ipynb), se utilizaron librerías como Seaborn, Matplotlib, Numpy, Pandas y Folium. Finalmente, para la creación del dashboard, se utilizó PowerBI.
<br><br>

# Proceso de trabajo

### ETL y EDA

Se realizó un exhaustivo proceso ETL para estandarizar nombres de variables, analizar nulos y duplicados, y eliminar columnas redundantes. Posteriormente, se llevó a cabo un análisis exploratorio para identificar patrones y tendencias que ayuden a tomar medidas preventivas.

![Imagen](imagenes/imagen_readme_01.png)

### Análisis de los Datos

El análisis integral de los datos sobre siniestros viales en la Ciudad Autónoma de Buenos Aires (CABA) revela patrones y tendencias significativas:

**Datos Generales:**
- El conjunto de datos cuenta con 696 registros y 21 columnas, proporcionando información detallada sobre accidentes, víctimas, ubicación y detalles temporales.

**Características Temporales:**
- Los accidentes parecen distribuirse de manera relativamente uniforme a lo largo de los años, meses y días, con una decrecion exagerada en el año 2020. Analizando cada año en particular el 2020 fue un año donde disminuyo mucho la tasa de siniestros viales, esto puede ser consecuencia de la cuarentena impuesta por las autoridades en base a la pandemia de COVID-19.

**Ubicación y Franja Horaria:**
- La mayoría de los accidentes ocurren en las franjas horarias de 6:00 a 12:00, mas concretamente en las horas 6 y 7 AM
- La ubicacion mas notorias en cuanto a mayor concentracion de accidentes fueron en las comunas 1, 4, 7, 8 y 9

**Edad:**
- El rango de edad con mas presencia es entre los 18 y los 59
- Se encontro una tendencia en cuanto a la edad de los participantes del genero masculino y la hora. Muy probable fueran clientes de bares o boliches.

**Género:**
- El 77% de las víctimas son masculinas, siendo este género predominante en todos los roles, ya sea conductor, pasajero o peatón.

**Distribución Espacial:**
- La alta frecuencia de accidentes en avenidas en la mayoría de las comunas de la Ciudad Autónoma de Buenos Aires indica posibles áreas críticas con alto flujo vehicular y, por ende, mayores riesgos de siniestros viales.


## KPI

En función de lo analizado en el punto anterior, se plantearon tres objetivos en relación a la disminución de la cantidad de víctimas fatales de los siniestros viales, desde los cuales se proponen tres indicadores de rendimiento clave o KPI.

* *Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior*

    Las tasas de mortalidad relacionadas con siniestros viales suelen ser un indicador crítico de la seguridad vial en una región. Se define como **Tasa de homicidios en siniestros viales** al número de víctimas fatales en accidentes de tránsito por cada 100,000 habitantes en un área geográfica durante un período de tiempo específico, en este caso se toman 6 meses. Su fórmula es:

    $\text{Tasa de homicidios en siniestros viales} = \frac{\text{Número de homicidios en siniestros viales}}{\text{Población total}}·100,000$

    Como *Población Total* se calculó la población para el año 2021 a partir de los censos poblacionales del año 2010 y 2022.

    En este caso, para el año 2021, la *Tasa de homicidios en siniestros viales* fue de 1.77 lo que significa que, durante los primeros 6 meses del año 2021, hubo aproximadamente 1.77 homicidios en accidentes de tránsito por cada 100,000 habitantes. Ahora, el objetivo planteado es reducir esta tasa para el siguiente semestre de 2021 en un 10%, esto es **1.60**. Cuando se calcula el KPI para este período se obtiene que la *Tasa de homicidios en siniestros viales* fue de **1.35**, lo que significa que para el segundo semestre de 2021 se cumple con el objetivo propuesto.

* *Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior*

    Como se vio en el análisis exploratorio, el 42% de las víctimas mortales se transportaban en moto al momento del hecho. Por lo que se consideró importante proponer el monitoreo de la cantidad de accidentes mortales en este tipo de conductor. Para ello se define a la **Cantidad de accidentes mortales de motociclistas** como el número absoluto de accidentes fatales en los que estuvieron involucradas víctimas que viajaban en moto en un determinado periodo temporal. La fórmula para medir la evolución de los accidentes mortales con víctimas en moto es:

    $\text{Cantidad de accidentes mortales de motociclistas} = -\frac{\text{Víctimas moto año anterior - Víctimas moto año actual}}{\text{Víctimas moto año anterior}}·100$

    Donde:
    - $\text{Víctimas moto año anterior}$: Número de accidentes mortales con víctimas en moto en el año anterior
    - $\text{Víctimas moto año actual}$: Número de accidentes mortales con víctimas en moto en el año actual 

    Para este caso, se toma como año actual al año 2021 y como año anterior al año 2020. En primer lugar, se calculó la *Cantidad de accidentes mortales de motociclistas* para el año 2020, el cual resultó de -46.00, de esta manera el objetivo a cumplir es de **-42.78** (es decir, la reducción del 7% de la cantidad de accidentes para 2020). El calcular la *Cantidad de accidentes mortales de motociclistas* para el año 2021 resultó de **70.37** lo que significa que aumentó un 70% la cantidad de muertes de conductores de motociclistas.

* *Reducir en un 10% la tasa de homicidios en las avenidas en el último año, en CABA, respecto al año anterior*

    Como se vio en el análisis exploratorio, la mayoría de las víctimas mortales transitaban por avenidas al momento del hecho. Se define a la **Tasa de homicidios en las avenidas** al número de víctimas fatales en accidentes de tránsito en avenidas por cada 100,000 habitantes en un área geográfica durante un período de tiempo específico, en este caso anual. Su fórmula es:

    $\text{Tasa de homicidios en las avenidas} = \frac{\text{Número de accidentes mortales con víctimas ocurridas en avenidas}}{\text{Total de la población}}·100000$

    **Resultado**:El objetivo de reducir en un 10% la tasa de homicidios en las avenidas no se cumplió. La tasa de homicidios aumentó en el año 2021, alcanzando **2.27**, lo que representa un aumento respecto al valor del año anterior. Este resultado destaca la importancia de revisar y fortalecer las medidas de seguridad específicas para las avenidas en la Ciudad Autónoma de Buenos Aires.
    

![Imagen](imagenes/imagen_readme_02.png)


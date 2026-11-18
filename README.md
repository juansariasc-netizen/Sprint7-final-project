# Sprint7-final-project
Objetivo: Analizar de manera integral el comportamiento de uso real de los clientes por edades en la empresa ConnectaTel respecto a sus llamadas y mensajes utilizando técnicas de ciencia de datos y estadística descriptiva, con el fin de optimizar la oferta comercial, diseñar nuevos planes, reducir la tasa de cancelación y mejorar la experiencia general del usuario.
El análisis se compone de tres fuentes de datos principales que se cruzan para obtener una visión completa del negocio: 
**plans.csv**: Catálogo de planes actuales de la compañía (precio mensual, minutos incluidos, GB incluidos y costos por excedentes o servicios adicionales).
**users_latam.csv**: Información demográfica y de gestión de los clientes (ID, nombre, edad, ciudad, fecha de registro, plan contratado y fecha de cancelación).
**usage.csv**: Registro detallado de la actividad real de los usuarios (tipo de evento, fecha, duración de llamadas en minutos y longitud de mensajes de texto).
El desarrollo del analisis siguió un flujo estructurado de pensamiento y análisis de datos:
1. **Carga y Exploración Inicial:** Importación de librerías (*pandas*, *seaborn*, *matplotlib*) y revisión de la estructura, dimensiones y tipos de datos de los tres datasets.
2. **Identificación de Problemas de Calidad:** Detección de valores nulos, registros faltantes (como el 11.7% de datos faltantes en `city` registrados como `?` y el 88.3% en `churn_date` para clientes activos), y *sentinels* numéricos (como `-999` en la edad).
3. **Limpieza y Estandarización de Datos:** Corrección de sentinels de edad sustituyéndolos por la mediana, conversión de formatos de fecha a tipo `datetime`, validación de nulos estructurales (*Missing At Random* o *MAR* en la duración de llamadas y longitud de mensajes), y manejo seguro de nulos geográficos.
4. **Agregación y Resumen Estadístico:** Creación de una tabla consolidada por usuario (`user_profile`) que resume su consumo histórico (total de llamadas, minutos y mensajes), calculando métricas descriptivas clave (media, mediana, cuartiles).
5. **Visualización y Detección de Outliers:** Generación de histogramas y diagramas de caja (*boxplots*) para identificar la distribución demográfica por edad y la presencia de *outliers* extremos en el volumen de llamadas.
6. **Segmentación de Clientes:** Clasificación de la base de usuarios según su nivel de consumo (bajo, medio y alto) y cruce con variables de edad y plan contratado para descubrir oportunidades comerciales.
7. **Insights Ejecutivos y Conclusiones:** Formulación de recomendaciones estratégicas basadas en los datos (como la justificación de introducir planes intermedios tipo *Estándar* y *Pro* para mitigar el *churn* y capturar mayor ARPU).

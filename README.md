Abstract
Este proyecto analiza un dataset de clientes de un banco, incluyendo información sociodemográfica, de productos contratados, actividad, digitalización y comportamiento de uso.
El objetivo es explorar patrones de comportamiento, segmentación, identificar relaciones entre productos y características de clientes, y proponer insights que puedan ayudar a la institución
a mejorar su estrategia comercial y de retención.
A través de visualizaciones interactivas en Python se buscan responder preguntas sobre la distribución de clientes por provincia, edad y género, la adopción de productos financieros, la relación entre actividad digital y cantidad de productos, y el impacto del saldo deudor 
y del último uso de productos sobre la cartera total de clientes.
Preguntas / Hipótesis de interés
Distribución de clientes
¿Qué provincias concentran mayor cantidad de clientes?
¿Cómo se distribuye la cartera según rangos etarios y género?
¿Existen diferencias en la cantidad de productos contratados según la provincia o el segmento de cartera?
Productos bancarios
¿Qué porcentaje de clientes tiene tarjeta de crédito, caja de ahorro en pesos, dólares o caja de seguridad?
¿La tenencia de seguros o plazos fijos varía según la edad o el segmento de cartera?
¿Los clientes con mayor cantidad de productos presentan mayor saldo deudor?

 Digitalización y uso
¿Qué proporción de clientes utiliza canales digitales?
¿Los clientes digitales realizan un uso más frecuente de productos  en comparación con los no digitales?
¿La adopción digital cambia significativamente entre provincias o grupos etarios?

Riesgo y endeudamiento
¿Cómo se distribuye el saldo deudor entre los distintos segmentos de cartera?
¿Los clientes activos difieren en su nivel de deuda respecto a los inactivos?
¿Existen grupos de mayor riesgo (alto saldo deudor + baja cantidad de productos + inactividad)?

import pandas as pd

url = "https://drive.google.com/drive/folders/1Qa9KU_Evs1HDnNI582L7jlMlcaW2ZSrc?usp=sharing"
df = pd.read_csv(url)

#Cantidad de filas y columnas del dataset
df.shape
df.head(5)

#Distribución Clientes: 1 - Activos vs Inactivos
actividad = df.groupby("IND_ACTIVO").agg({"CANTIDAD_CLIENTES": "count"})

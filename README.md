---
title: "Tablero HackODS - Los .Py"
author: "Gómez Heredia Germán Saúl 
Hernández Cerna Luna 
Tovar Ramirez Alvaro Julian "
format: html
jupyter: python3
---

# ¿El calor afecta lo que respiro?

**¿Qué son los ODS?**

Los objetivos de desarrollo sostenible, son 17 metas universales de plan de acciones  por el planeta y la humanidad adoptadas por la ONU para fortalecer la paz universal y acceso a la justicia, donde los 17 objetivos poseen 169 metas que buscan abarcar el bienestar económico, social y ambiental de diversos países incluyendo a México. 

# ¿Qué es el ODS 13 (acción por el clima)?

El ODS 13 acción por el clima, es un llamado internacional a encargarnos de combatir el cambio climático y tomar acciones para reducir el daño de las actividades humanas. 

```{python}
from IPython.display import Image, display

url = "https://www.climatepartner.com/sites/default/files/2022-12/E_SDG_poster_UN_emblem_WEB%202020_0.png"
display(Image(url=url, width=400))
```

# Indicadores 13.1.1n y 13.1.1.a 

Estos dos indicadores buscan orientar la agenda 2030 a México conforme a los objetivos que el país decidió se pueden implementar correctamente en la república Mexicana. el primer indicador (13.1.1n)
 es sobre pm 2.5(Párticulas pm 2.5) y el sgundo inicador (13.1.1.a) es sobre ozono (O3).

 Una parte importante para el ODS 13 es tener en cuenta que las personas hacemos cambios muy significativos en la atmósfera, donde los GEI(Gases de efecto invernadero) hacen que el cambio climático aumente considerablemente por toda la emisión de gases.
 
## ¿Qué son las pm 2.5?

Partículas finas presentes en el aire que respiramos, estas párticulas provienen de actividades como combustión de gases, actividad industrial e incendios. Dependiendo del tamaño puedeb vivir días o semanas en la atmósfera. 

## ¿Qué es el ozono?

El arma de doble filo, un gas que existe de forma natural para impedir que lleguen los rayos directos del Sol pero que en este caso hablaremos del ozono que se genera por las actividades humanas tales como emisiones por vehiculos, solventes químicos y actividad industrial. Su tiempo de vida es de aproximadamente 12 horas. 

## Daños a la población

Afectan a nuestra salud de diferentes formas, principalmente dañan los pulmones, al torrente sanguíneo y a largo plazo pueden generar enfermedades cardiovasculare, respiratorias e infartos, dismunuir la emisión de estas partículas y gases es fundamental para mejorar la calidad del aire. 
 
# ¿Qué es la temperatura y cómo la temperatura las afecta?

La temperatura es la medida con la que sabemos que tan caliente o frío está un objeto o ambiente.

Los contaminantes como el ozono y los pm 2.5 son contaminantes de la atmósfera que con la temperatura pueden cambiar su comportamiento y el cambio climático en ambos tiene una retroalimentación negativa donde producen hasta efecto invernadero, a pesar del ozono ser una partícula con poco tiempo de ”vida” en la atmósfera. 

## Referencias:

- Objetivos de Desarrollo sostenible, (Naciones Unidas)  https://www.un.org/sustainabledevelopment/es/climate-change-2/

-PM 2.5, (Official website of the State of California), 2026 State of California https://oehha.ca.gov/calenviroscreen/indicator/pm25}

- Objetivos de desarollo sostenible(Sec. de economía, Ahenda 2030 México, INEGI) ,2025 https://agenda2030.mx/#/home

- Instituto Nacional de Ecología y Cambio Climático, https://sinaica.inecc.gob.mx/

# Explicación 

Las siguientes gráficas que se van a mostrar a continuación, las pusimos para ejemplificar con datos cómo es que desde el 2018 hasta el 2023 el cambio de temperatura está afectando al ozono y las partículas PM 2.5 , donde se recopilaron 6 estaciones de diferentes puntos de la zona metropolitana:

Nezahualcóyotl, Estado de México
Merced, Ciudad de México
Puebla, Puebla
Pachuca, Hidalgo
Cuernavaca, Morelos
Toluca, Estado de México

y se hicieron promedios anuales de excedencia de acuerdo a la norma de salud (OMS 2005) para poder mostrar las gráficas del sujeto a analizar (Pm 2.5, Ozono, Temperatura) en un intervalo de tiempo (años). 


```{python}
import pandas as pd
import matplotlib.pyplot as plt

# Gráfica de  Pm 2.5
df = pd.read_csv("pm25.csv")

#  filas 
print(df.head())

x = df["AÑO"]
y = df["PM25"]

plt.figure()
plt.plot(x, y)

# Etiquetas
plt.xlabel("AÑO")
plt.ylabel("PM 2.5(microgramos sobre metro cubico)")
plt.title("Concentración de PM 2.5")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()

# Gráfica de Ozono (O3)

df = pd.read_csv("ozono.csv")
print(df.head())

x = df["AÑO"]
y = df["OZONO"]
plt.figure()
plt.plot(x, y)

plt.xlabel("AÑO")
plt.ylabel("OZONO (ppm)")
plt.title("Concentración de Ozono")

plt.xticks(rotation=45)
plt.tight_layout()

plt.show()

# Gráfica de Temperatura 

df = pd.read_csv("temp.csv")
print(df.head())

x = df["AÑO"]
y = df["TEMP"]


plt.figure()
plt.plot(x, y)

plt.xlabel("AÑO")
plt.ylabel("Temperatura (°C)")
plt.title("Temperatura a lo largo del tiempo")

plt.xticks(rotation=45)
plt.tight_layout()

plt.show()

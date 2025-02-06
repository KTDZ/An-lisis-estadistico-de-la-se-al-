# Análisis estadistico de señales Biomédicas 
Este laboratorio tiene como objetivo analizar estadisticamente las señales biomédicas, sus estadisticas descriptivas y evaluar la relación señal-ruido (SNR) bajo diferentes tipos de ruido. El código esta implentado en Python y utiliza bibliotecas como `wfdb`, `numpy`,`matplotlib` y `scipy`.

## Tabla de Contenidos 
1.[Introducción](#introducción)
2.[Requisitos](#requisitos)
3.[Uso](#uso)
4.[Explicación del Código](#explicación-del-código)
5.[Resultados y Gráficas](#resultados-y-gráficas)
6.[Conclusión](#conclusión)

## Introducción 

Las señales biomédicas son las señales generadas por el cuerpo humano, como lo son los electrocardiogramas (ECG), electroencefalogramas (EEG) y lo que analizaremos en este laboratorio es una señal de electromiografia (EMG). Estas señales contienen información relevante, como amplitud y frecuencia, pero también están contaminadas por ruido, lo que dificulta su análisis.La SNR (Signal to Noise Ratio) es una relación entre la potencia media de la señal y la potencia media del ruido expresada en decibelios (dB). Una SNR más alta significa que la señal es más distinguible del ruido, y una SNR más baja significa que el ruido es más dominante. 
## Cálculo para la SNR
Para hallar la SNR conociendo la potencia, se calcula con la siguiente fórmula: SNR= 10*log<sub>10</sub> $\frac{Ps}{(Pn)}$  ; donde **Ps** es la potencia de la señal y **Pn** la potencia del ruido. En dado caso que la potencia sea desconocida, podemos hallar la SNR de forma estadistica haciendo uso de la varianza (σ<sup>2</sup>) la cual es una medida de dispersión y una vez que se obtiene la varianza tanto para la señal como para el ruido, estos dos resultados se dividen obteniendo asi la SNR. 

En este laboratorio se realiza lo siguiente: 

1. **Lectura de una señal fisiológica** desde archivos `.dat` y `.hea` que son descargados desde las base de datos como [PhysioNet`](https://physionet.org/).
2. **Cálculo de estadísticas descriptivas**(media,desviación estándar, coeficiente de variación, histograma y función de probabilidad).
3. **Evaluación de la relación señal-ruido (SNR)** Bajo diferentes tipos de ruido (gaussiano,impulso y artefacto).

## Requisitos 

- **Phyton** Instalado en tu sistema 
- **Spyder** (Puedes instalarlo como parte de [Anaconda](https://www.anaconda.com/)).
- **Bibliotecas de Python:** `numpy`,`matplotlib`,`scipy`,`wfdb`
- **Una señal fisiológica en formato `.dat` y `.hea` (Se puede descargala de [Physionet](https://physionet.org/))**.

## Descargar una señal fisiologica y Guardar los datos en el código 
1. Entrar a Physionet y descargar una señal en formato .dat y .hea, en este caso de una señal EMG
2. Crear un nuevo archivo en Spyder
3. Guardar los archivos descargados en la misma carpeta donde se guardo el archivo del código.
4. Verificar que todas las librerias esten instaldas: Poner en la terminal ejem:!pip install wfdb
5. Programar o en este caso copiar el codigo en spyder.

   
## Explicación del Código  

1. **Lectura de la señal**: Se utiliza la biblioteca wfdb para leer la señal fisiológica desde los archivos .dat y .hea
### ![image](https://github.com/user-attachments/assets/a6ebaa49-53fc-48ba-b1fd-f9ea67d60226)
2.**Cálculos de estadistica**:Se calculan estadísticas descriptivas y se usa la libreria numpy para permitir calcular la media,desviación estándar y coeficiente de variación. Estas se calculan de dos maneras:Programando las fórmulas desde cero y utilizando funciones predefinidas de python.
### ![image](https://github.com/user-attachments/assets/b68de891-4309-46ec-a174-4868bfe7f217)
3.**Visualización de la señal**: La señal se grafica en el dominio del tiempo para su inspección visual con ayuda de la libreria matplotlib.
### ![image](https://github.com/user-attachments/assets/b1c01518-2b65-49e8-b334-3fd0a559c2a2)
4.**Histograma y Función de Probabilidad** : Se grafica un Histograma de señal junto con su función de Probabilidad.
5.**Calculo de SNR por potencia y por forma estadistica**: Se añade diferentes tipos de ruido ( gaussiano,impulso y artefacto) a la señal y se calcula el SNR para cada caso, en este codigo se calculo el SNR tanto con la formula de potencia como con la parte estadistica.

## Resultados y Gráficas
### 1. Señal Original 
![image](https://github.com/user-attachments/assets/ca43bd6b-6698-499d-abb2-bf55fdf0ca86)
## *Figura 1: Representación de la señal en el dominio del tiempo.*
### 2. Histograma y Función de probabilidad desde cero y predefinida.
![image](https://github.com/user-attachments/assets/2ca58720-5063-41b6-9135-99094ab103c0)
El histograma y nuestra función de probabilidad corresponde a una señal de EMG(electromiografia) por lo tanto se puede analizar lo siguiente:
##
1. En el histograma la frecuencia da diferentes valores de amplitud de la señal,esto debido a que si la señal se encuentra en reposo, en este caso que la actividad musculas se baja, las amplitudes se van a concentrar al rededos de cero con algunas fluctuaciones menores debido al ruido que pueda tener la señal, mientras que las señales de EMG activas, que es cuando el músculo se contrae, los valores de las amplitudes van a aumentar, pero tienden a distribuirse de una manera simétrica refeljando la naturaleza oscilatoria de la señal. 
## *Figura 2: Histograma y Función de probabilidad.*
### 3. Señal con Ruido Gaussioano
![image](https://github.com/user-attachments/assets/e2675ac9-8e7d-4bfc-b03a-978618887038)
## *Figura 3: Señal del Ruido Gaussiano.*
El ruido Gaussiano sigue una distribución normal y se caracteriza por tener valores aleatorios que se distribuyen siguiendo la curva de Gauss que tiene forma de campana. Se evalúa este ruido con la señal con este ruido ya que es un modelo que se aproxima a lo que ocurre en sistemas reales y sus propiedades matemáticas permiten eliminarlo eficazmente. 
### 4. Señal con Ruido de impulso
![image](https://github.com/user-attachments/assets/d8c09649-65df-4f91-b2f7-a0f38d936b2f)
## *Figura 4: Señal con ruido de impulso.*
El ruido con impulso es caracterizado por tener picos de alta intensidad o valores extremos que ocurren repentinamente a lo largo de la señal. Se evalúa este ruido con la señal ya que en el mundo real pueden ocurrir perturbaciones inesperadas en el ambiente como interferencias eléctricas o descargas que generen picos extremos.
### 5. Señal con ruido de artefacto
![image](https://github.com/user-attachments/assets/c3845491-6e82-4740-b698-92d8695e9c30)
## *Figura 5: Señal de Ruido de artefacto.*
El ruido con artefacto son distorsiones o anomalías que alteran la apariencia o el comportamiento de la señal. Se evalúa este ruido con la señal ya que en el momento de adquirir o de transmitir los datos de una señal pueden existir modificaciones no deseadas en las cuales no representan información real de la fuente original.
### 6. Calculos estadisticos
![image](https://github.com/user-attachments/assets/a66b0eef-3b9e-4428-b55e-387434106013)
##
1. **Media**: Representa el valor promedio de la señal, la razón de que nos diera un valor tan bajo es que la oscilacion de la señal EMG es cercana a cero.
2. **Desviación Estandar**: Es la dispersión de los valores que tiene la señal respecto a la media, esto nos quiere decir que la mayoria de los valores estan alrededor de 0.08157..., la variabilidad va a depender de diferentes factores, como lo son la actividad muscular y el ruido que pueda tener presente en la señal.
3. **Coeficiente de variación**: Esta es una medida que va a relacionar la relación entre la desviación estandar y la media, dando un valor en porcentaje, el que nos de un valor porcentual tan alto nos dice que la media de nuestra señal es muy pequeña (cercana a cero), lo que hace que en coeficiente de variación sea tan alto, esto nos indica que la media no es representativa de la variabilidad de la señal,  lo cual puede ser normal en señales EMG.
## *Figura 6: Calculos estadisticos.*
### 7.Calculos de SNR
![image](https://github.com/user-attachments/assets/bdb2fbd4-d642-43cb-9b18-9d9900204696)
## *Figura 7: Calculos SNR.*
El SNR al medir la relación entre la potencia de la señal y la potencia del ruido en decibeles (dB). El que el SNR se positivo significa que ña señal es más fuerte que el ruido, mientras que si un SNR es negativo nos va a indicar que el ruido es mucho mas predominate sobre la señal, con esto podemos decir que: 
##
 1.**Ruido Gaussiano(-1.78 dB)**: Al ser el SNR cercano a 0 dB sugiere que la señal y el ruido puede tener potencias similares, en etse caso el ruido gaussiano está casi al mismo novel que la señal, lo que puede llegar a generar una leve degradación de la calidad.
 ##
 2.**Ruido de impulso(12.86 dB)**: El SNR positivo va indica que la señal es significativamente más fuerte que el ruido de impulso, estos ruido son comunes, aparecen como picos esporádicos en la señal, pero en general no llega a afectar demasiado la estructura de la señal original. 
 ##
 3.**Ruido de artefacto(-12.74 dB)**: El SNR es negativo en este caso y el que sea tan alto indica que el ruido es mucho mas fuerte que la señal, este tipo de ruido puede estar dominando completamente la señal,lo que puede sugerir una severa distorsión en los datos originales. 

## Conclusiones 
- Las estadísticas descriptivas permiten identificar los patrones y anomalías, el calculo del SNR nos da una medida cuantitativa del nivel de interferencia en la señalEste análisis permite comprender mejor las características de las señales EMG, su procesamiento y el impacto del ruido en su calidad. Además, el repositorio en GitHub proporciona una guía clara para la reproducción y el aprendizaje de estos métodos.



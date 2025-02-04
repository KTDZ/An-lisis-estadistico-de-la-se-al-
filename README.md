# An-lisis-estadistico-de-la-se-al-


Introducción

Este proyecto contiene el codigo para procesar la señal EMG adquirida desde PhysioNet, con el objetivo de analizar sus características estadísticas y la influencia del ruido en su procesamiento.

Procesamiento de Señales

Las señales fueron obtenidas desde PhysioNet y procesadas en Spyder (Python). Inicialmente, se graficó la señal original . Posteriormente, se calcularon estadísticos descriptivos tanto manualmente como mediante funciones predefinidas de Python.

Cálculo de Estadísticos

Se calcularon los siguientes estadísticos descriptivos:

Media

Desviación estándar

Coeficiente de variación

Histogramas

Función de probabilidad

El cálculo de estos estadísticos se realizó de dos maneras:

Programando las fórmulas desde cero.

Usando funciones predefinidas de librerías de Python 

Relación Señal-Ruido (SNR)

Se investigó la definición de SNR y se implementaron cálculos para evaluar cómo afecta la contaminación de ruido a la calidad de la señal.

Se aplicaron los siguientes tipos de ruido:

Ruido gaussiano

Ruido impulso

Ruido tipo artefacto

Tras la adición de cada tipo de ruido, se calculó el SNR para evaluar la degradación de la señal.

Instrucciones

Para ejecutar el código, asegúrese de tener los siguientes archivos y dependencias:

Descargar la señal EMG desde PhysioNet en dat. y hea.
Crear un nuevo archivo en Spyder
Crear una carpeta en la que este los achivos mencionados anteriormente y el de Spyder 
Programar el codigo haciendo uso de esos archivos

Ejecutar el código

Visualizar los resultados 

Ejemplo de carga de la señal en Python:


Conclusión

Este análisis permite comprender mejor las características de las señales EMG, su procesamiento y el impacto del ruido en su calidad. Además, el repositorio en GitHub proporciona una guía clara para la reproducción y el aprendizaje de estos métodos.

